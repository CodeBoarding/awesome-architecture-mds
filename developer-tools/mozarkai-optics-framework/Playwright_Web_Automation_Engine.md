```mermaid
graph LR
    Playwright_Driver_Sync_Async_Execution_Bridge["Playwright Driver & Sync/Async Execution Bridge"]
    Playwright_Page_Source_XPath_Reconstruction_Engine["Playwright Page-Source & XPath Reconstruction Engine"]
    Playwright_Page_Source_XPath_Reconstruction_Engine -- "delegates execution to" --> Playwright_Driver_Sync_Async_Execution_Bridge
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Web platform](https://img.shields.io/badge/Open%20in-Web%20platform-2563EB?style=flat-square)](https://app.codeboarding.org)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/diagrams)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Encapsulates the full Playwright-based browser automation stack — driver session/app lifecycle management, DOM element location, page-source extraction, and screenshot capture — bridged into the framework's synchronous execution model via a persistent async event loop.

### Playwright Driver & Sync/Async Execution Bridge
Combines the persistent event-loop bridge enabling synchronous framework code to invoke Playwright's async API, the Playwright driver class managing browser/context/page lifecycle and app/session management, element locator strategy for resolving elements by XPath/text/attributes, and screenshot capture functionality for raw page/element screenshots.


**Related Classes/Methods**:

- `optics_framework.common.async_utils.run_async`:40-69
- `optics_framework.common.async_utils._get_or_create_persistent_loop`:21-37
- `optics_framework.engines.drivers.playwright.Playwright`:12-443
- `optics_framework.engines.elementsources.playwright_find_element.PlaywrightFindElement`:12-281
- `optics_framework.engines.elementsources.playwright_screenshot.PlaywrightScreenshot`:11-120



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


### Playwright Page-Source & XPath Reconstruction Engine
Specialized ElementSourceInterface provider dedicated to extracting a structured, hierarchical representation of the DOM and synthesizing robust XPath/locator strategies for elements. Introspects the live browser DOM tree, rebuilds hierarchical path/XPath models per element, derives locators from tags/attributes/text, and attaches metadata needed by downstream matching and the self-healing fallback ladder.


**Related Classes/Methods**:

- `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource`:17-1045
- `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._build_hierarchical_path`:252-276
- `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._build_xpath_from_attribute`:227-237
- `optics_framework.engines.elementsources.playwright_page_source.PlaywrightPageSource._build_playwright_locator`:877-896



**Source Files:**

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




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)