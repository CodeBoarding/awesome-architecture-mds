```mermaid
graph LR
    Playwright_Web_Automation_Engine["Playwright Web Automation Engine"]
    Native_UI_Helper_Page_Source_Extraction_Layer["Native UI-Helper & Page-Source Extraction Layer"]
    Appium_Selenium_Element_Location_Geometry_Utilities["Appium/Selenium Element Location & Geometry Utilities"]
    Playwright_Web_Automation_Engine -- "shared utility-library dependency" --> Appium_Selenium_Element_Location_Geometry_Utilities
    Native_UI_Helper_Page_Source_Extraction_Layer -- "shared utility-library dependency" --> Appium_Selenium_Element_Location_Geometry_Utilities
    Appium_Selenium_Element_Location_Geometry_Utilities -- "delegated text-match fallback via shared text-comparison utility" --> Native_UI_Helper_Page_Source_Extraction_Layer
    click Playwright_Web_Automation_Engine href "./Playwright_Web_Automation_Engine.md" "Details"
    click Native_UI_Helper_Page_Source_Extraction_Layer href "./Native_UI_Helper_Page_Source_Extraction_Layer.md" "Details"
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Web platform](https://img.shields.io/badge/Open%20in-Web%20platform-2563EB?style=flat-square)](https://app.codeboarding.org)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/diagrams)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Concrete, pluggable engine implementations that interact with devices/browsers — Appium, Selenium, and Playwright drivers along with UI-helper and element/page-source extraction utilities, plus shared async and general-purpose utilities.

### Playwright Web Automation Engine [[Expand]](./Playwright_Web_Automation_Engine.md)
Encapsulates the full Playwright-based browser automation stack — driver session/app lifecycle management, DOM element location, page-source extraction, and screenshot capture — bridged into the framework's synchronous execution model via a persistent async event loop.


**Related Classes/Methods**:

- `optics_framework.common.async_utils.run_async`:40-69
- `optics_framework.common.async_utils._get_or_create_persistent_loop`:21-37
- `optics_framework.engines.drivers.playwright.Playwright`:12-443
- `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement`:12-281
- `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource`:17-1045



**Source Files:**

- `optics_framework/common/async_utils.py`
  - `optics_framework.common.async_utils._start_loop` (L16-L18) - Function
  - `optics_framework.common.async_utils._get_or_create_persistent_loop` (L21-L37) - Function
  - `optics_framework.common.async_utils.run_async` (L40-L69) - Function
- `optics_framework/engines/drivers/playwright.py`
  - `optics_framework.engines.drivers.playwright.Playwright` (L12-L443) - Class
  - `optics_framework.engines.drivers.playwright.Playwright.__init__` (L18-L27) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.launch_app` (L33-L34) - Method
  - `optics_framework.engines.drivers.playwright.Playwright._launch_app_async` (L36-L68) - Method
  - `optics_framework.engines.drivers.playwright.Playwright._launch_other_app_async` (L70-L97) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.launch_other_app` (L99-L100) - Method
  - `optics_framework.engines.drivers.playwright.Playwright._navigate_to` (L102-L125) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.get_app_version` (L127-L128) - Method
  - `optics_framework.engines.drivers.playwright.Playwright._normalize_locator` (L131-L156) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.press_element` (L162-L163) - Method
  - `optics_framework.engines.drivers.playwright.Playwright._press_element_async` (L165-L179) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.press_coordinates` (L181-L182) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.press_percentage_coordinates` (L184-L185) - Method
  - `optics_framework.engines.drivers.playwright.Playwright._press_percentage_async` (L187-L192) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.press_keycode` (L194-L219) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.enter_text` (L225-L226) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.enter_text_using_keyboard` (L228-L229) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.enter_text_element` (L231-L233) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.clear_text` (L235-L237) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.clear_text_element` (L239-L241) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.swipe` (L247-L249) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.swipe_percentage` (L251-L252) - Method
  - `optics_framework.engines.drivers.playwright.Playwright._swipe_percentage_async` (L254-L259) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.swipe_element` (L261-L283) - Method
  - `optics_framework.engines.drivers.playwright.Playwright._swipe_element_async` (L285-L307) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.scroll` (L310-L313) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.get_text_element` (L320-L322) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.force_terminate_app` (L324-L325) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.terminate` (L327-L328) - Method
  - `optics_framework.engines.drivers.playwright.Playwright._cleanup_resources` (L330-L346) - Method
  - `optics_framework.engines.drivers.playwright.Playwright._terminate_async` (L348-L399) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.get_driver_session_id` (L401-L402) - Method
  - `optics_framework.engines.drivers.playwright.Playwright.execute_script` (L404-L416) - Method
  - `optics_framework.engines.drivers.playwright.Playwright._execute_script_async` (L418-L443) - Method
- `optics_framework/engines/elementsources/playwright_find_element.py`
  - `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement` (L12-L281) - Class
  - `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement.__init__` (L15-L17) - Method
  - `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement._require_page` (L19-L26) - Method
  - `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement.capture` (L32-L41) - Method
  - `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement.get_page_source` (L43-L52) - Method
  - `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement.get_interactive_elements` (L54-L66) - Method
  - `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement._strip_prefix` (L72-L83) - Method
  - `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement._build_locator` (L85-L107) - Method
  - `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement.locate` (L109-L153) - Method
  - `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement.get_element_bboxes` (L155-L167) - Method
  - `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement.get_bbox_for_element` (L169-L185) - Method
  - `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement._check_element_found` (L191-L202) - Method
  - `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement._check_assertion_complete` (L204-L214) - Method
  - `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement.assert_elements` (L216-L265) - Method
  - `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement.assert_elements_visible` (L267-L281) - Method
- `optics_framework/engines/elementsources/playwright_page_source.py`
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource` (L17-L1045) - Class
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource.__init__` (L23-L28) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._require_page` (L34-L73) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource.capture` (L79-L85) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource.get_page_source` (L87-L114) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource.get_interactive_elements` (L116-L165) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._extract_bounds` (L171-L212) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._escape_xpath_value` (L214-L225) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._build_xpath_from_attribute` (L227-L237) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._try_unique_attributes` (L239-L250) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._build_hierarchical_path` (L252-L276) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._build_simple_xpath` (L278-L295) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._try_text_content` (L297-L311) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._try_attribute_text` (L313-L325) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._try_inner_text` (L327-L349) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._try_class_text` (L351-L363) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._extract_display_text` (L365-L407) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._check_filter_type` (L409-L425) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._should_include_element` (L427-L451) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._is_button` (L453-L473) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._is_input` (L475-L481) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._is_image` (L483-L496) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._is_text` (L498-L519) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._is_probably_interactive` (L521-L558) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._determine_xpath_uniqueness` (L560-L584) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._build_xpath_from_single_attribute` (L586-L607) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._build_xpath_from_attribute_pair` (L609-L622) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._build_xpath_from_text` (L624-L641) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._resolve_xpath` (L643-L657) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._try_unique_attributes_xpath` (L659-L679) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._try_attribute_pairs_xpath` (L681-L700) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._try_text_xpath` (L702-L714) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._try_maybe_unique_attributes_xpath` (L716-L735) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource.get_xpath` (L737-L776) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._build_hierarchical_xpath` (L778-L799) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._escape_for_xpath_literal` (L801-L818) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._build_extra_metadata` (L820-L846) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._resolve_optics_element` (L852-L875) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._build_playwright_locator` (L877-L896) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._strip_prefix_for_page_source` (L898-L909) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource.locate` (L911-L945) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._check_single_element_presence` (L951-L980) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._check_elements_batch` (L982-L1002) - Method
  - `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource.assert_elements` (L1004-L1045) - Method
- `optics_framework/engines/elementsources/playwright_screenshot.py`
  - `optics_framework.engines.elementsources.playwright_screenshot.PlaywrightScreenshot` (L11-L120) - Class
  - `optics_framework.engines.elementsources.playwright_screenshot.PlaywrightScreenshot.__init__` (L20-L22) - Method
  - `optics_framework.engines.elementsources.playwright_screenshot.PlaywrightScreenshot._require_page` (L24-L30) - Method
  - `optics_framework.engines.elementsources.playwright_screenshot.PlaywrightScreenshot.capture` (L36-L43) - Method
  - `optics_framework.engines.elementsources.playwright_screenshot.PlaywrightScreenshot.capture_screenshot_bytes` (L45-L61) - Method
  - `optics_framework.engines.elementsources.playwright_screenshot.PlaywrightScreenshot.capture_screenshot_as_numpy` (L63-L78) - Method
  - `optics_framework.engines.elementsources.playwright_screenshot.PlaywrightScreenshot.get_interactive_elements` (L84-L96) - Method
  - `optics_framework.engines.elementsources.playwright_screenshot.PlaywrightScreenshot.assert_elements` (L98-L104) - Method
  - `optics_framework.engines.elementsources.playwright_screenshot.PlaywrightScreenshot.locate` (L106-L112) - Method
  - `optics_framework.engines.elementsources.playwright_screenshot.PlaywrightScreenshot.locate_using_index` (L114-L120) - Method


### Native UI-Helper & Page-Source Extraction Layer [[Expand]](./Native_UI_Helper_Page_Source_Extraction_Layer.md)
Provides platform-specific UI-tree traversal, XPath synthesis, and page-source serialization for Appium and Selenium, plus shared text/page-source comparison and persistence utilities used to detect UI-state changes and support the self-healing locator strategies.


**Related Classes/Methods**:

- `optics_framework.engines.drivers.appium_UI_helper.UIHelper`:100-1303
- `optics_framework.engines.drivers.appium_UI_helper.XPathUniquenessIndex`:21-97
- `optics_framework.engines.drivers.selenium_UI_helper.UIHelper`:15-259
- `optics_framework.engines.elementsources.selenium_page_source.SeleniumPageSource`:9-219
- `optics_framework.common.utils.compare_text`:293-329



**Source Files:**

- `optics_framework/common/utils.py`
  - `optics_framework.common.utils.compare_text` (L293-L329) - Function
  - `optics_framework.common.utils.save_page_source` (L529-L565) - Function
  - `optics_framework.common.utils.save_page_source_html` (L568-L593) - Function
- `optics_framework/engines/drivers/appium_UI_helper.py`
  - `optics_framework.engines.drivers.appium_UI_helper.XPathUniquenessIndex` (L21-L97) - Class
  - `optics_framework.engines.drivers.appium_UI_helper.XPathUniquenessIndex.__init__` (L39-L61) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.XPathUniquenessIndex.matches` (L63-L83) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.XPathUniquenessIndex.position_of` (L85-L97) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper` (L100-L1303) - Class
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.__init__` (L101-L108) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.get_page_source` (L110-L120) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.find_xpath_from_text` (L144-L161) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.find_xpath` (L163-L228) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.find_exact` (L230-L239) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.find_relative` (L241-L255) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.make_relative` (L257-L280) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.make_partial_match` (L282-L319) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.find_partial` (L321-L335) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.fuzzy_match_prefix` (L337-L339) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.find_attribute_match` (L341-L407) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.split_element` (L409-L411) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.extract_attribute` (L413-L421) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.simplify_xpath` (L423-L452) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.extract_key_attributes` (L454-L485) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._find_exact_or_suffix_match` (L487-L515) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.get_locator_and_strategy` (L517-L569) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.get_view_locator` (L571-L652) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.get_locator_and_strategy_using_index` (L654-L764) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.parse_bounds` (L766-L783) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.get_bounding_box_for_text` (L785-L805) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.get_bounding_box_for_xpath` (L807-L863) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.get_element_attributes_by_xpath` (L865-L888) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.get_interactive_elements` (L891-L936) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._extract_bounds` (L938-L977) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._extract_bounds._to_int` (L962-L969) - Function
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._extract_display_text` (L979-L1007) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._extract_display_text.norm` (L987-L991) - Function
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._build_extra_metadata` (L1009-L1023) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._xpath_from_single_attr` (L1025-L1033) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._xpath_from_attr_pair` (L1035-L1044) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._xpath_try_attributes_for_unique` (L1046-L1073) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._xpath_try_node_name` (L1075-L1081) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._xpath_attribute_pairs_permutations` (L1083-L1086) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._xpath_try_cases_for_unique` (L1088-L1108) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._xpath_build_hierarchical` (L1110-L1125) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.get_xpath` (L1127-L1152) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._escape_for_xpath_literal` (L1154-L1171) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._build_attribute_condition` (L1173-L1192) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._build_structural_xpath` (L1194-L1213) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._should_include_element` (L1215-L1250) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._is_button` (L1252-L1257) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._is_input` (L1259-L1268) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._is_image` (L1270-L1275) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._is_text` (L1277-L1285) - Method
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper._is_probably_interactive` (L1287-L1303) - Method
- `optics_framework/engines/drivers/selenium_UI_helper.py`
  - `optics_framework.engines.drivers.selenium_UI_helper.UIHelper` (L15-L259) - Class
  - `optics_framework.engines.drivers.selenium_UI_helper.UIHelper.__init__` (L16-L20) - Method
  - `optics_framework.engines.drivers.selenium_UI_helper.UIHelper.get_page_source` (L24-L34) - Method
  - `optics_framework.engines.drivers.selenium_UI_helper.UIHelper.find_element_by_text` (L36-L71) - Method
  - `optics_framework.engines.drivers.selenium_UI_helper.UIHelper.find_html_element_by_text` (L74-L106) - Method
  - `optics_framework.engines.drivers.selenium_UI_helper.UIHelper._get_html_soup` (L109-L116) - Method
  - `optics_framework.engines.drivers.selenium_UI_helper.UIHelper._collect_matching_tags` (L119-L137) - Method
  - `optics_framework.engines.drivers.selenium_UI_helper.UIHelper._matches_visible_text` (L140-L142) - Method
  - `optics_framework.engines.drivers.selenium_UI_helper.UIHelper._match_tag_attributes` (L145-L156) - Method
  - `optics_framework.engines.drivers.selenium_UI_helper.UIHelper._build_match_result` (L159-L166) - Method
  - `optics_framework.engines.drivers.selenium_UI_helper.UIHelper.find_html_element_by_xpath` (L169-L198) - Method
  - `optics_framework.engines.drivers.selenium_UI_helper.UIHelper.convert_to_selenium_element` (L200-L240) - Method
  - `optics_framework.engines.drivers.selenium_UI_helper.UIHelper._find_element_by_text` (L243-L245) - Method
  - `optics_framework.engines.drivers.selenium_UI_helper.UIHelper._find_element_by_attribute` (L248-L259) - Method
- `optics_framework/engines/elementsources/selenium_page_source.py`
  - `optics_framework.engines.elementsources.selenium_page_source.SeleniumPageSource` (L9-L219) - Class
  - `optics_framework.engines.elementsources.selenium_page_source.SeleniumPageSource.__init__` (L23-L34) - Method
  - `optics_framework.engines.elementsources.selenium_page_source.SeleniumPageSource._require_webdriver` (L36-L42) - Method
  - `optics_framework.engines.elementsources.selenium_page_source.SeleniumPageSource.capture` (L44-L50) - Method
  - `optics_framework.engines.elementsources.selenium_page_source.SeleniumPageSource.get_page_source` (L54-L67) - Method
  - `optics_framework.engines.elementsources.selenium_page_source.SeleniumPageSource.get_interactive_elements` (L69-L72) - Method
  - `optics_framework.engines.elementsources.selenium_page_source.SeleniumPageSource.locate` (L74-L113) - Method
  - `optics_framework.engines.elementsources.selenium_page_source.SeleniumPageSource.get_element_bboxes` (L115-L126) - Method
  - `optics_framework.engines.elementsources.selenium_page_source.SeleniumPageSource.get_element_bboxes.locate_safe` (L120-L124) - Function
  - `optics_framework.engines.elementsources.selenium_page_source.SeleniumPageSource.get_bbox_for_element` (L128-L132) - Method
  - `optics_framework.engines.elementsources.selenium_page_source.SeleniumPageSource._find_element_by_any` (L134-L158) - Method
  - `optics_framework.engines.elementsources.selenium_page_source.SeleniumPageSource.locate_using_index` (L161-L164) - Method
  - `optics_framework.engines.elementsources.selenium_page_source.SeleniumPageSource.assert_elements` (L167-L198) - Method
  - `optics_framework.engines.elementsources.selenium_page_source.SeleniumPageSource._is_text_found` (L201-L209) - Method
  - `optics_framework.engines.elementsources.selenium_page_source.SeleniumPageSource._is_xpath_found` (L211-L219) - Method


### Appium/Selenium Element Location & Geometry Utilities
Implements the mobile/native (Appium) and secondary Selenium element-finding strategies together with the geometric/data-normalization utilities (bounding boxes, hashing, timestamps) that translate raw driver attributes into the framework's canonical element model.


**Related Classes/Methods**:

- `optics_framework.engines.elementsources.appium_find_element.AppiumFindElement`:14-293
- `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource`:14-324
- `optics_framework.engines.elementsources.selenium_find_element.SeleniumFindElement`:11-240
- `optics_framework.common.utils.bbox_from_appium_attribute_fallback`:833-874
- `optics_framework.common.utils.compute_hash`:277-279



**Source Files:**

- `optics_framework/common/utils.py`
  - `optics_framework.common.utils.determine_element_type` (L166-L192) - Function
  - `optics_framework.common.utils.get_timestamp` (L202-L211) - Function
  - `optics_framework.common.utils.compute_hash` (L277-L279) - Function
  - `optics_framework.common.utils.bbox_from_appium_attribute_fallback` (L833-L874) - Function
  - `optics_framework.common.utils.bbox_from_webelement_like` (L877-L910) - Function
  - `optics_framework.common.utils.bboxes_from_webelements` (L1123-L1144) - Function
- `optics_framework/engines/drivers/appium.py`
  - `optics_framework.engines.drivers.appium.Appium.appium_find_element` (L1257-L1268) - Method
- `optics_framework/engines/drivers/appium_UI_helper.py`
  - `optics_framework.engines.drivers.appium_UI_helper.UIHelper.get_distinct_page_source` (L123-L142) - Method
- `optics_framework/engines/elementsources/appium_find_element.py`
  - `optics_framework.engines.elementsources.appium_find_element.AppiumFindElement` (L14-L293) - Class
  - `optics_framework.engines.elementsources.appium_find_element.AppiumFindElement.__init__` (L24-L33) - Method
  - `optics_framework.engines.elementsources.appium_find_element.AppiumFindElement._require_driver` (L35-L41) - Method
  - `optics_framework.engines.elementsources.appium_find_element.AppiumFindElement.capture` (L43-L51) - Method
  - `optics_framework.engines.elementsources.appium_find_element.AppiumFindElement.get_page_source` (L54-L69) - Method
  - `optics_framework.engines.elementsources.appium_find_element.AppiumFindElement.get_interactive_elements` (L71-L89) - Method
  - `optics_framework.engines.elementsources.appium_find_element.AppiumFindElement.locate` (L92-L154) - Method
  - `optics_framework.engines.elementsources.appium_find_element.AppiumFindElement.get_element_bboxes` (L156-L164) - Method
  - `optics_framework.engines.elementsources.appium_find_element.AppiumFindElement.get_bbox_for_element` (L166-L177) - Method
  - `optics_framework.engines.elementsources.appium_find_element.AppiumFindElement._assert_elements_one_pass` (L179-L190) - Method
  - `optics_framework.engines.elementsources.appium_find_element.AppiumFindElement._assert_elements_common` (L192-L216) - Method
  - `optics_framework.engines.elementsources.appium_find_element.AppiumFindElement.assert_elements` (L218-L237) - Method
  - `optics_framework.engines.elementsources.appium_find_element.AppiumFindElement._is_within_screen_bounds` (L239-L256) - Method
  - `optics_framework.engines.elementsources.appium_find_element.AppiumFindElement._is_located_and_displayed` (L258-L276) - Method
  - `optics_framework.engines.elementsources.appium_find_element.AppiumFindElement.assert_elements_visible` (L278-L293) - Method
- `optics_framework/engines/elementsources/appium_page_source.py`
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource` (L14-L324) - Class
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource.__init__` (L24-L32) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource._require_webdriver` (L34-L46) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource.capture` (L48-L55) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource.get_page_source` (L57-L74) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource.get_interactive_elements` (L76-L80) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource._locate_by_text` (L82-L96) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource._locate_by_xpath` (L98-L111) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource.locate` (L113-L138) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource.get_element_bboxes` (L140-L154) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource.get_element_bboxes.locate_safe` (L148-L152) - Function
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource.get_bbox_for_element` (L156-L167) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource.locate_using_index` (L169-L187) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource.assert_elements` (L190-L235) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource._validate_rule` (L237-L239) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource.find_xpath_from_text` (L241-L262) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource.find_xpath_from_text_index` (L264-L275) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource._validate_tree` (L277-L281) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource._search_text_in_attribute` (L283-L292) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource._search_single_text` (L294-L302) - Method
  - `optics_framework.engines.elementsources.appium_page_source.AppiumPageSource.ui_text_search` (L304-L324) - Method
- `optics_framework/engines/elementsources/selenium_find_element.py`
  - `optics_framework.engines.elementsources.selenium_find_element.SeleniumFindElement` (L11-L240) - Class
  - `optics_framework.engines.elementsources.selenium_find_element.SeleniumFindElement.__init__` (L16-L24) - Method
  - `optics_framework.engines.elementsources.selenium_find_element.SeleniumFindElement.capture` (L26-L32) - Method
  - `optics_framework.engines.elementsources.selenium_find_element.SeleniumFindElement.get_page_source` (L34-L45) - Method
  - `optics_framework.engines.elementsources.selenium_find_element.SeleniumFindElement.get_interactive_elements` (L47-L50) - Method
  - `optics_framework.engines.elementsources.selenium_find_element.SeleniumFindElement.locate` (L52-L103) - Method
  - `optics_framework.engines.elementsources.selenium_find_element.SeleniumFindElement._find_element_by_any` (L105-L131) - Method
  - `optics_framework.engines.elementsources.selenium_find_element.SeleniumFindElement.get_element_bboxes` (L133-L137) - Method
  - `optics_framework.engines.elementsources.selenium_find_element.SeleniumFindElement.get_bbox_for_element` (L139-L143) - Method
  - `optics_framework.engines.elementsources.selenium_find_element.SeleniumFindElement._assert_elements_common` (L145-L175) - Method
  - `optics_framework.engines.elementsources.selenium_find_element.SeleniumFindElement.assert_elements` (L177-L193) - Method
  - `optics_framework.engines.elementsources.selenium_find_element.SeleniumFindElement._is_located_and_visible` (L195-L216) - Method
  - `optics_framework.engines.elementsources.selenium_find_element.SeleniumFindElement.assert_elements_visible` (L218-L228) - Method
  - `optics_framework.engines.elementsources.selenium_find_element.SeleniumFindElement.locate_using_index` (L237-L240) - Method




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)