  ```
  App Setting Component Controller
    App Lifecycle - $onInit
      ✓ should init
    Non Built-in Event: handle message from content script
      ✓ should update the app enabled state and set the "hasCsResp" flag to true if the actin is "GET_ENABLED_STATE"
      ✓ should do nothing if the action is not "GET_ENABLED_STATE"
    Built-in Event: Save app setting whenever a global setting is changed
      ✓ should save state
    Build-in Event: Toggle App by sending message to content-script
      ✓ should set the enable state & tell content script to toggle app (default: enable status is false)

  App Root Component (UI/DOM)
    native: element mouseover event
      ✓ should create/cache a overlay which has the same size and offset position as the mouseover element
      ✓ should not have matched elements nor matched overlays (by default none in verbose mode)
      ✓ should set the path display text
      ✓ should set the dialog offset position relative to the mouseover element
      ✓ should have 1x dot style for popup button example (mouseover elemnt width <= 16px)
      ✓ should have animation enabled for matches` overlays
    native: window scroll event (vertical scroll scenario)
      ✓ size/offset position of overlay should be adjusted to be the same as the prev. mouseover target if it is still visible after scroll
      ✓ overlay and popup should disppear if they are no longer visible in viewport after scroll
      ✓ should set additional matched overlays (if any)
      ✓ should have animation enabled for matches` overlays
    native: window resize event (width scenario)
      ✓ size and offset position of overlay should be adjusted to be the same as the prev. mouseover target
      ✓ should have animation disabled for matches` overlays
    native: document "ESC" keyup event
      ✓ should trigger the handler & remove the events when Esc key is pressed
    ng-change: interact with path list checkbox
      ✓ should update the path text, stats and match overlays when uncheck "nth-child"
      ✓ should update the path text, stats and match overlays when check "nth-child" (after "nth-child" unchecked)
      ✓ should have animation disabled for matches` overlays
    ng-change: selector verbose mode checkbox change (for 1 match)
      ✓ should trigger the event handler and update the path display text and stats
      ✓ should have animation enabled for matches` overlays
    ng-change: selector verbose mode checkbox change (for > 1 matches)
      ✓ should uncheck the checkbox and trigger the event handler
      ✓ should update the overlays if there is > 1 matches
      ✓ should adjust the mouseover target overlay size/position
      ✓ should adjust the matches' overlays size/position
    ng-change: include filter change (for verbose mode only: default on)
      ✓ should exclude nth-child partial in the last selector, update the matches overlay and path stats
      ✓ should exclude id partial in the last selector
    ng-change: toggle selector text alignment
      ✓ should align the selector path text to top of the page (default)
      ✓ should align the selector path text to bottom of the page
    ng-click: popup button and dialog
      ✓ should trigger the event handler, show the dialog and hide the popup button when popup button (dots) is clicked
      ✓ should hide the dialog and show the popup button when close button inside the dialog is clicked
    ng-click: lock overlay
      ✓ should lock the overlays
      ✓ should maintain the overlay when window is resized or scrolled when overlay is clocked
    ng-click: set current settings as default setting
      ✓ should save the global state
    ng-click: copy selector path
      ✓ should copy the path

  App Component Controller
    App Lifecycle
      ✓ should setup the "shl-app:on" & "shl-app:off" events
      ✓ should trigger activate
      ✓ should trigger deactivate
    Global Event: activate/deactivate app
      ✓ should activate the app and run the $digest cycle
      ✓ should deactivate the app and run the $digest cycle
    Global Event: body mouseover
      ✓ should not allow mouseover target change when unallowed
      ✓ should allow mouseover target change (with setting viewport data) when allowed and viewport data hasn't been set
      ✓ should allow mouseover target change (without setting viewport data) when allowed and viewport data has been set
    Global Event: window resize and scroll (view shift)
      ✓ should not update overlay given overlay is not present
      ✓ should update overlay when resize given overlay is present
      ✓ should update overlay when scrolling window given overlay is present
      ✓ should update overlay when scrolling element given overlay is present
    Global Event: dismiss the dialog via click other than the close button
      ✓ should not dismiss dialog if it is not allowed to be closed
      ✓ should dismiss dialog if it is allowed to be closed
    Global Event: document contextmenu/righ-click and ESC key (app exit)
      ✓ should not exit if event is not contextmenu nor ESC key
      ✓ should exit if event type is keyup and keycode is 27 (ESC)
    Built-in Event: Interact with Path List
      ✓ should update the selector, matched elements/overlays and overlay stats
    Built-in Event: Handle verbose mode change
      ✓ should set matches overlay when change verbose mode
    Built-in Event: Save app setting
      ✓ should save setting when set as default
      ✓ should catch the error, warn User and deactivate the app in case there is an error
    Built-in Event: Copy selector
      ✓ should copy the selector path
    Built-in Event: Verbose Mode Change
      ✓ should change the verbose mode
    Built-in Event: Dialog
      ✓ should set dialog position when popup button is clicked
      ✓ should close dialog when close button is clicked
    Util: Get Popup button style
      ✓ should return true if mouse over element is enough width
      ✓ should return false if mouse over element is enough width
    Util: Get Transform related Css variables (string)
      ✓ should return the variables as string
    Helper Methods
      create native event config & config native event
        ✓ should create a conformed event config object
        ✓ should return an array of native event config
      consolidate app manager methods
        ✓ should set match overlays with entry animation enabled

  Form Chip Component/Controller
    ✓ should pass the data to component's controller and DOM
    ✓ should trigger parent's handler when checkbox checked state is changed
    ✓ should trigger parent's handler when calling component's handler

  Form switch Component/Controller
    ✓ should pass the data to component's controller and DOM
    ✓ should trigger parent's handler when checkbox checked state is changed
    ✓ should trigger parent's handler when calling component's handler

  Path List Component/Controller
    render
      ✓ should show all the path partial text (with no arrow for last path)
      ✓ should be all checked for all its partial include option (based on mock path list sample)
      ✓ should remove the path partial text (from Dom) if its include option is false and vice versa
    passed data and parent's handler
      ✓ should pass the data to Component scope/controller
      ✓ should trigger parent's handler when checkbox is changed
      ✓ should trigger parent's handler when calling component's handler

  Path Stats Component/Controller
    ✓ should pass the data to component's controller and DOM
    ✓ should reflect in component's controller and DOM when passed data changes

  Chrome Handle Service (Independent Service from Angular)
    Get App State from Chrome Built-in Storage
      via jQuery's Defer
        ✓ should get the app/global state
      via Angular's $q
        ✓ should get the app/global state
    save the app/global state
      ✓ should save the app/global state
    reset the state
      ✓ should reset the state
    send message to popup
      ✓ should send message to popup
    send msg to content-script
      ✓ should create/return a tab query callback function (which sends a mesage to content-script) based on the message
      ✓ should query the tabs
    message event listener
      ✓ should setup event listener for message from popup
      ✓ should remove event listener for message from popup
      ✓ should disallow specific app type without executing the callback
      ✓ should disallow specific message source without executing the callback
      ✓ should allow specific message source and execute the callback

  Dom Handle Service
    emit an "deactivate app" event & notify App Admin
      ✓ should not emit event if event emitter instance does not exist in window
      ✓ should emit event
    add/remove event
      ✓ should add the event & trigger the callback when event is triggered
      ✓ should remove the added events and not trigger the callback when disabled
    set the size/pos of an element in Dom
      ✓ should set the size/offset position of element
      ✓ should only set the offset of element
    check if the mouseover target is valid
      ✓ should be invalid if target is body
      ✓ should be invalid if target is svg
      ✓ should be invalid if target's ancestor is svg
      ✓ should be invalid if target is previous mouseover element
      ✓ should be invalid if target is within the App
      ✓ should be invalid if target tag name is "shl-app-shell"
      ✓ should be valid if target is none of the above
    get overlay data
      ✓ should get overlay data for an element
      ✓ should get overlay data for an element when its width/height is less than minimum allowed (4px)
      ✓ should get overlay data for a collection of non-hidden elements (viewport data not provided)
      ✓ should get overlay data for a collection of hidden elements (viewport data not provided)
      ✓ should get overlay data for a collection of non-hidden/hidden elements (viewport data provided)
    get updated overlay data for matched elem
      ✓ should return updated state where isVisible is true if originally hidden but now visible
      ✓ should return updated state where isVisible and inVp are false if originally visible but now hidden
      ✓ should return unchanged state if originall visible & now still visible
    set return how the element should be aligned depending on its current offset position and window viewport
      ✓ should align with top and left
      ✓ should align with top and right
      ✓ should align with bottom and left
      ✓ should align with bottom and right
    check if an element is within specified containers
      ✓ should return true if target is inside the selectors specified
      ✓ should return false if target is not inside the containers specified
    get matched elements based on selector
      ✓ should return all matched elements when not providing an excluding container (or when invalid)
      ✓ should return matched elements that are not inside the container when providing an excluding container
    filter matched elements against excluding element
      ✓ should return filtered elements if provided elements is part of matched elements
      ✓ should return false if provided elements is not part of matched elements
    should get viewport (window) data
      ✓ should get viewport data from actual window if window param is not provided (when Visualviewport API is supported)
      ✓ should get viewport data from mock window if window param is provided (when Visualviewport API is supported)
      ✓ should get viewport data from actual window if window param is not provided (when Visualviewport API is not supported)
      ✓ should get viewport data from mock window if window param is provided (when Visualviewport API is supported)
    copy text to clipboard
      ✓ should setup the copy event listener and trigger the copy event/handler
      ✓ should set the clipboard data, prevent default and remove listener when handler is run
    get the matching global event target based on specified string
      ✓ should return body if target string specified is "body"
      ✓ should return document if target string specified is "document"
      ✓ should return window if target string specified is "window"

  Native Prototype Handle
    intercept the prototype call
      for mock prototype method
        ✓ should throw error if method does not exist in prototype
        ✓ should override the original prototype
        ✓ should call both original prototype method and intercepter function when the original prototype method is called
        ✓ should restore the prototype when restore function is run
        ✓ should skip and return null/undefined if the prototype function is already restored
      for Event Prototype method - stopImmediatePropagation
        ✓ should fire the custom event in case the event is stopped
    observe Event
      ✓ should check if event is observed when provided observed event only
      ✓ should check if event is observed when provided observed event and target
      ✓ should check if event is observed when provided observed event and excluded target
    get matching global target for observed configuration
      ✓ should get document if target string is "document"
      ✓ should get body if target string is "body"
      ✓ should get window if target string is "window"
      ✓ should return the target string if target string is none of the above

  Element Selector Service
    Get Element Tag
      ✓ should return the tag name for an element
    Get Element ID
      ✓ should return string with a hash "#" prefix for a string
      ✓ should return empty string without a hash "#" prefix for an empty string
    Get Element Css Class
      ✓ should return both the css class names string and array (with dot ".") for an element which has at least one class
      ✓ should not return both the css class names string and array (with dot ".") for an element which doesnt have class
    Get Element nth-child
      ✓ should return the nth-child selector for a child element which has at least one sibling
      ✓ should not return the nth-child selector for a child element which doesn't have siblings
    Check if should proceed to get Parent 's Selector Path
      ✓ should not get parent's selector path when verbose mode is on and element tag is body
      ✓ should get parent's selector path when verbose mode is on and element tag is not body & not unique
      ✓ should get parent's selector path when verbose mode is on and element tag is not body but unique
      ✓ should not get parent's selector path when verbose mode is off and element is body
      ✓ should not get parent's selector path when verbose mode is off and element is not body but unique
      ✓ should get parent's selector path when verbose mode is off and element is not unique
    Get Element Selector Path in Verbose Mode
      ✓ should return a plain selector path for an element (not in DOM)
      ✓ should return a full selector path for an element (not in DOM)
      ✓ should return a full selector path for an element (added in DOM)
    Test Element Selector Path in Non-Verbose mode
      ✓ should return a plain selector path (tag + id) for an element when element has an id (unique)
      ✓ should return a plian selector path (tag + class) for an element when element has an unique class
      ✓ should return a plian selector path (tag with optional nth-child) for an element when element has no id or unique class
      ✓ should return a full selector path for an element
    Get Element Selector Path List
      ✓ should have multiple path objects in the list even if element is unique for verbose mode
      ✓ should have multiple path objects in the list even if element is not unique for verbose mode
      ✓ should have only one single path object in the list if element is unique for non-verbose mode
      ✓ should have multiple path object in the list if element is not unique for non-verbose mode
    Extend a plain selector path with filter option
      ✓ should extend a path object with the filter option
      ✓ getPath - should return a single selector path object with filter option for an element
      ✓ getFullPath - should return a full selector path object with filter option for an element
      ✓ getFullPathList - should return a list of selector path object with filter option for an element
    Build a custom selector string from filter option (regardless of verbose mdoe)
      ✓ should return a custom selector with default filter values
      ✓ should return a custom selector with modified filter values - example 1
      ✓ should return a custom selector with modified filter values - example 2
    Get a selector path string value via Include-option
      ✓ should not filter in the path if not provided with filter option
      ✓ should filter out id in the path
      ✓ should filter out class names in the path
      ✓ should filter out nth-child in the path
      ✓ should filter out combined options in the path
    Get a selector path filter option based via Include-option
      ✓ should not override the filter if not provided option
      ✓ should override the id filter in the path
      ✓ should override the class filter in the path
      ✓ should override the nthChild filter in the path
    check if all path filters are off
      ✓ should return true if all path filters are off
      ✓ should return false if not all path filters are off

  Viewport Handle Service
    Format/Process Element's Offset data and Viewport data
      ✓ should return formatted readable data
    Check if element partially visible in Viewport
      Format elem offset data and viewport data
        ✓ should call the elem offset data and viewport data
      Outside Viewport
        ✓ should return false when elem is not visible across both X and Y axis
        ✓ should return false when elem is visible across X axis but not Y axis or vice versa
      Inside Viewport
        ✓ should return true when elem is completely visible across both X and Y axis
        ✓ should return true when elem is partially visible across both X and Y axis
    Check if element completely visible in Viewport
      Format elem offset data and viewport data
        ✓ should call the elem offset data and viewport data
      Inside Viewport
        ✓ should return true when elem is completely visible across both X and Y axis in Viewport
      Outside Viewport
        ✓ should return false when elem is not visible across both X and Y axis
        ✓ should return false when elem is visible across one axis only
        ✓ should return false when elem is partially visible across Y axis and/or X axis

  App Manager Service
    App
      notify App Admin to deactivate the app
        ✓ should call notify App Admin
      activate/deactivate the app
        ✓ should activate the app - add app host, setup events and merge state
        ✓ should deactivate the app
      save app state
        ✓ should save app state
    Viewport
      check if viewport data has been set
        ✓ should return true if viewport data has been set
        ✓ should return false if viewport data has not been set
      set viewport Data
        ✓ should set the Viewport Data (default: size + scroll data)
        ✓ should set the Viewport Data (scroll data only)
      set viewport state for Overlays' and other Offset elements
        ✓ should set the viewport state to true if it is partially in viewport
        ✓ should set the viewport state to false if it is partially in viewport
      set viewport statistics based on number of visible/hidden Overlays in viewport
        ✓ should set the viewport statistics
      check if offset data is in viewport
        ✓ should check using mouseover element offset data when the provided offset data doesn't have width/height
        ✓ should check using offset data for check when the provided offset data has width/height
    Target/Matched Elements Overlay
      store mouseover target element
        ✓ should cache the mouseover target element
      set selector path list for an element
        ✓ should set selector path list for the target and Set the last path filter option for the target in Verbose Mode
        ✓ should set selector path list for the target and Not Set the last path filter option for the target in Non-Verbose Mode
      set target overlay - data only
        ✓ should set target overlay data
      set/construct the selector string
        ✓ should set the trimmed selector string
      set matches based on target path
        ✓ should find matches and update the model When mouseover target is part of the matched elements
        ✓ should find matches and update the model When mouseover target is not part of the matched elements
      set matches overlay - data only
        ✓ should set the matches overlay data
      set additional matched elements/overlays
        ✓ should not set additional matched elements/overlays if there are no matched elements found
        ✓ should not set additional matched elements/overlays if matched elements found only contains target element
        ✓ should not set additional matched elements/overlays if matched elements found are same as prev. matched elements
        ✓ should set additional matched elements/overlays if matched elements found are NOT same as prev. matched elements
      enable matches overlay entry animation
        ✓ should set the "isEntryTransOn" flag to true
        ✓ should set the "isEntryTransOn" flag to false
      get transform related css variables with values as string for passing to stylesheet
        ✓ should return empty string when viewport is not defiend (app deactivated)
        ✓ should return the both translate & scale variables when viewport is defined
        ✓ should return the both translate variables only if width/height is not defined when viewport is defined
      check if mouseover target can proceed
        ✓ should not be alolwed to be change if dialog is on
        ✓ should not be alolwed to be change if highlight is locked
        ✓ should not be alolwed to be change if mouseover target is invalid
        ✓ should be allowed to change if highlight is not locked, dialog is not on and mouseover target is valid
      check if at least one overlay is present
        ✓ should return true if mouseover element has been cached prior (at least one)
        ✓ should return false if mouseover element has not been cached prior
    Popup Dialog
      set dialog position relative to the popup container position
        ✓ should set align with dialog's bottom right
        ✓ should set align with dialog's bottom left
        ✓ should set align with dialog's top left
        ✓ should set align with dialog's top right
      determine the look variations (3x or 1x dots) for popup button
        ✓ should return if width is large or equal to 16px
        ✓ should return false if width is below 16px
      close dialog popup via the close button
        ✓ should close dialog popup
      check if dialog can be dismissed other than the close button
        ✓ should return false if popup is off
        ✓ should return false if the param `chromeTargetPaths` is undefined/null (i.e. not supported in chrome)
        ✓ should return false if the param `chromeTargetPaths` array is empty
        ✓ should return false if target is or in specified App elements
        ✓ should return true if target is not or not in specified App elements
    Selector text
      copy the selector
        ✓ should copy the selector path if the path is not empty
        ✓ should escape the path string for any \ symbol so it can be used in JS as selector string
        ✓ should not copy the selector path if the path is empty
    Helper Methods
      set the path filter option of last item in the past list based on the include option
        ✓ should set/override the filter option of the last path in provided path list with custom include option
        ✓ should set filter option of last path of default path list (localState) with custom include option
        ✓ should set filter option of the last path in provided path list with default include option (globalState)
      reset global OR local/domcache state back to default
        ✓ should reset global state back to default
        ✓ should reset local and domcache state back to default
      check if same selector path is same as previous mouseover element
        ✓ should return false if previous mouseover element does not exist (no comparison)
        ✓ should return true if new target path is same as existing path
        ✓ should return false if new target path is not same as existing path

  Dom Cache State Service
    ✓ should have default values

  Global State Service
    ✓ should have default values

  Local State Service
    ✓ should have default values

  App Admin Service
    init (aggregate)
      ✓ should init
    prepare the app related elements (shell, app, link)
      ✓ should prepare the app related elements
    prepare the app
      ✓ should prep the app
      ✓ should trigger the callback when event emitter receives `DISABLE_APP` from the App
    cache the app elements
      ✓ should cache the app elements
    send app enabled status to popup
      ✓ should send app enabled status to popup
    toggle the app
      ✓ should not enable if App exists in DOM
      ✓ should enable if App does not exist in DOM
      ✓ should disable if App exists in DOM
      ✓ should not disable if App does not exist in DOM
    enable/disable the app
      enable the app
        ✓ should enable the app when it is not initial run (default)
        ✓ should enable the app when it is initial run and autoEnable setting is on
        ✓ should save the default state into storage and not enable the app when chrome has no stored state
        ✓ should not enable the app when it is initial run and autoEnable setting is off
      disable the App
        ✓ should trigger the event disable app event on the App element and remove the App shell element from DOM
    check app enabled status
      ✓ should return app element (undefined) and enabled status (false) when app does not exist in DOM
      ✓ should return app element and enabled status (true) when app exists in DOM
    check validity of source states against target states
      ✓ shoud be invalid if target state does not contain property of source state
      ✓ shoud be invalid if source state does not contain any property
      ✓ shoud be valid if target state contains all properties of source state
    add/remove app
      ✓ should add the app shell element to the DOM
      ✓ should remove the added app shell element from the DOM
    observe element host `:last-child` position in body
      ✓ should set up the callback and return the observer
      ✓ should trigger the callback if child list is changed in body
    move element host to end of body
      ✓ should skip if it is not in DOM
      ✓ should skip if it is in DOM but already is last-child of body
      ✓ should move the Element host if it is in DOM but is not last-child of body

Chrome 69.0.3497 (Mac OS X 10.12.2): Executed 288 of 288 SUCCESS (3.642 secs / 3.496 secs)
TOTAL: 288 SUCCESS


=============================== Coverage summary ===============================
Statements   : 98.61% ( 920/933 )
Branches     : 97.35% ( 330/339 )
Functions    : 98.52% ( 200/203 )
Lines        : 98.87% ( 875/885 )
================================================================================
  ```