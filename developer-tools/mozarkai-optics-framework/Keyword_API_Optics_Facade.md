```mermaid
graph LR
    Verification_Session_Config_Support_Services["Verification & Session/Config Support Services"]
    Optics_Facade_Application_Lifecycle_Management["Optics Facade & Application Lifecycle Management"]
    Action_Keyword_Execution_AI_Self_Healing["Action Keyword Execution & AI Self-Healing"]
    Verification_Session_Config_Support_Services -- "Shared frame-encoding utility for seed/heal-context imagery" --> Action_Keyword_Execution_AI_Self_Healing
    Optics_Facade_Application_Lifecycle_Management -- "calls" --> Verification_Session_Config_Support_Services
    Optics_Facade_Application_Lifecycle_Management -- "calls" --> Action_Keyword_Execution_AI_Self_Healing
    Action_Keyword_Execution_AI_Self_Healing -- "Internal composition for locate-then-verify and evidence capture" --> Verification_Session_Config_Support_Services
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Web platform](https://img.shields.io/badge/Open%20in-Web%20platform-2563EB?style=flat-square)](https://app.codeboarding.org)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/diagrams)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The top-level facade and keyword implementation layer that test flows and interfaces call directly. Exposes Optics as the single entry point wiring together action, verification, and app-management keyword sets, while ActionKeyword, AppManagement, and Verifier implement concrete keyword-driven operations (tap/swipe/type, app launch/terminate, assertions/waits) that test authors invoke, including AI-based self-healing fallback for element location.

### Verification & Session/Config Support Services
Supplies resolvers, interfaces, and API-exposure helpers that ActionKeyword and Verifier depend on for their work, including session/template resolution, image/text abstraction, config extraction, workspace-data gathering, and the Verifier keyword-set for assertion and wait operations.


**Related Classes/Methods**:

- `optics_framework.api.verifier.Verifier`:11-369
- `optics_framework.common.session_manager.SessionTemplateResolver`:75-97
- `optics_framework.common.image_interface.ImageInterface`:5-71
- `optics_framework.common.text_interface.TextInterface`:5-68
- `optics_framework.common.expose_api._gather_workspace_data`:1156-1192



**Source Files:**

- `optics_framework/api/action_keyword.py`
  - `optics_framework.api.action_keyword._maybe_save_aoi_screenshot` (L43-L50) - Function
  - `optics_framework.api.action_keyword.ActionKeyword.enter_text_direct` (L964-L977) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.enter_text_using_keyboard` (L979-L999) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.press_keycode` (L1030-L1044) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._parse_script_and_args` (L1111-L1146) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.execute_script` (L1148-L1178) - Method
- `optics_framework/api/verifier.py`
  - `optics_framework.api.verifier.Verifier` (L11-L369) - Class
  - `optics_framework.api.verifier.Verifier.validate_element` (L29-L46) - Method
  - `optics_framework.api.verifier.Verifier.is_element` (L48-L103) - Method
  - `optics_framework.api.verifier.Verifier._resolve_param` (L105-L107) - Method
  - `optics_framework.api.verifier.Verifier.assert_equality` (L109-L124) - Method
  - `optics_framework.api.verifier.Verifier.assert_presence` (L127-L137) - Method
  - `optics_framework.api.verifier.Verifier.assert_visibility` (L139-L151) - Method
  - `optics_framework.api.verifier.Verifier._assert_common` (L153-L170) - Method
  - `optics_framework.api.verifier.Verifier._group_elements_by_type` (L172-L178) - Method
  - `optics_framework.api.verifier.Verifier._process_element_groups` (L180-L196) - Method
  - `optics_framework.api.verifier.Verifier._save_annotated_screenshot` (L198-L205) - Method
  - `optics_framework.api.verifier.Verifier._evaluate_rule` (L207-L209) - Method
  - `optics_framework.api.verifier.Verifier._handle_result` (L211-L217) - Method
  - `optics_framework.api.verifier.Verifier._capture_success_event` (L219-L223) - Method
  - `optics_framework.api.verifier.Verifier.validate_screen` (L226-L245) - Method
  - `optics_framework.api.verifier.Verifier.capture_screenshot` (L247-L265) - Method
  - `optics_framework.api.verifier.Verifier.capture_pagesource` (L268-L284) - Method
  - `optics_framework.api.verifier.Verifier._safe_capture_screenshot_np` (L286-L296) - Method
  - `optics_framework.api.verifier.Verifier._bounds_need_screenshot` (L298-L306) - Method
  - `optics_framework.api.verifier.Verifier._collect_interactive_elements` (L308-L329) - Method
  - `optics_framework.api.verifier.Verifier.get_interactive_elements` (L331-L346) - Method
  - `optics_framework.api.verifier.Verifier.get_screen_elements` (L348-L369) - Method
- `optics_framework/common/config_handler.py`
  - `optics_framework.common.config_handler.Config.get` (L83-L87) - Method
- `optics_framework/common/expose_api.py`
  - `optics_framework.common.expose_api.AppiumUpdateRequest` (L114-L121) - Class
  - `optics_framework.common.expose_api.TemplateUploadRequest` (L140-L144) - Class
  - `optics_framework.common.expose_api._empty_workspace_data` (L1134-L1143) - Function
  - `optics_framework.common.expose_api._capture_source_safe` (L1146-L1153) - Function
  - `optics_framework.common.expose_api._gather_workspace_data` (L1156-L1192) - Function
- `optics_framework/common/image_interface.py`
  - `optics_framework.common.image_interface.ImageInterface` (L5-L71) - Class
  - `optics_framework.common.image_interface.ImageInterface.element_exist` (L18-L35) - Method
  - `optics_framework.common.image_interface.ImageInterface.find_element` (L38-L57) - Method
  - `optics_framework.common.image_interface.ImageInterface.assert_elements` (L60-L71) - Method
- `optics_framework/common/models.py`
  - `optics_framework.common.models.TemplateData.get_template_path` (L304-L305) - Method
- `optics_framework/common/session_manager.py`
  - `optics_framework.common.session_manager.SessionTemplateResolver` (L75-L97) - Class
  - `optics_framework.common.session_manager.SessionTemplateResolver.__init__` (L82-L83) - Method
  - `optics_framework.common.session_manager.SessionTemplateResolver.get_template_path` (L85-L97) - Method
- `optics_framework/common/strategies.py`
  - `optics_framework.common.strategies.StrategyManager.capture_screenshot` (L810-L821) - Method
- `optics_framework/common/text_interface.py`
  - `optics_framework.common.text_interface.TextInterface` (L5-L68) - Class
  - `optics_framework.common.text_interface.TextInterface.element_exist` (L18-L32) - Method
  - `optics_framework.common.text_interface.TextInterface.find_element` (L35-L54) - Method
  - `optics_framework.common.text_interface.TextInterface.detect_text` (L57-L68) - Method
- `optics_framework/common/utils.py`
  - `optics_framework.common.utils.SpecialKey` (L52-L122) - Class
  - `optics_framework.common.utils.encode_numpy_to_base64` (L231-L238) - Function
  - `optics_framework.common.utils.save_screenshot` (L331-L357) - Function
  - `optics_framework.common.utils.save_interactable_elements` (L601-L615) - Function
  - `optics_framework.common.utils.parse_special_key` (L635-L652) - Function
  - `optics_framework.common.utils.scale_interactive_element_bounds` (L1073-L1120) - Function
- `optics_framework/engines/vision_models/base_methods.py`
  - `optics_framework.engines.vision_models.base_methods.load_template` (L6-L31) - Function
- `optics_framework/engines/vision_models/image_models/remote_oir.py`
  - `optics_framework.engines.vision_models.image_models.remote_oir.RemoteImageDetection` (L12-L253) - Class
  - `optics_framework.engines.vision_models.image_models.remote_oir.RemoteImageDetection.__init__` (L16-L29) - Method
  - `optics_framework.engines.vision_models.image_models.remote_oir.RemoteImageDetection.detect_images` (L31-L81) - Method
  - `optics_framework.engines.vision_models.image_models.remote_oir.RemoteImageDetection.find_element` (L83-L151) - Method
  - `optics_framework.engines.vision_models.image_models.remote_oir.RemoteImageDetection.element_exist` (L153-L165) - Method
  - `optics_framework.engines.vision_models.image_models.remote_oir.RemoteImageDetection.locate` (L167-L180) - Method
  - `optics_framework.engines.vision_models.image_models.remote_oir.RemoteImageDetection.assert_elements` (L182-L214) - Method
  - `optics_framework.engines.vision_models.image_models.remote_oir.RemoteImageDetection._prepare_encoded_templates` (L216-L229) - Method
  - `optics_framework.engines.vision_models.image_models.remote_oir.RemoteImageDetection._detect_and_match_template` (L231-L253) - Method
- `optics_framework/engines/vision_models/image_models/templatematch.py`
  - `optics_framework.engines.vision_models.image_models.templatematch.TemplateMatchingHelper` (L9-L253) - Class
  - `optics_framework.engines.vision_models.image_models.templatematch.TemplateMatchingHelper.__init__` (L17-L28) - Method
  - `optics_framework.engines.vision_models.image_models.templatematch.TemplateMatchingHelper.find_element` (L30-L112) - Method
  - `optics_framework.engines.vision_models.image_models.templatematch.TemplateMatchingHelper.assert_elements` (L114-L152) - Method
  - `optics_framework.engines.vision_models.image_models.templatematch.TemplateMatchingHelper.element_exist` (L154-L253) - Method
- `optics_framework/engines/vision_models/ocr_models/easyocr.py`
  - `optics_framework.engines.vision_models.ocr_models.easyocr.EasyOCRHelper` (L9-L133) - Class
  - `optics_framework.engines.vision_models.ocr_models.easyocr.EasyOCRHelper.__init__` (L17-L35) - Method
  - `optics_framework.engines.vision_models.ocr_models.easyocr.EasyOCRHelper.find_element` (L37-L104) - Method
  - `optics_framework.engines.vision_models.ocr_models.easyocr.EasyOCRHelper.detect_text` (L106-L130) - Method
  - `optics_framework.engines.vision_models.ocr_models.easyocr.EasyOCRHelper.element_exist` (L132-L133) - Method
- `optics_framework/engines/vision_models/ocr_models/googlevision.py`
  - `optics_framework.engines.vision_models.ocr_models.googlevision.GoogleVisionHelper` (L8-L109) - Class
  - `optics_framework.engines.vision_models.ocr_models.googlevision.GoogleVisionHelper.__init__` (L16-L25) - Method
  - `optics_framework.engines.vision_models.ocr_models.googlevision.GoogleVisionHelper.find_element` (L27-L72) - Method
  - `optics_framework.engines.vision_models.ocr_models.googlevision.GoogleVisionHelper.element_exist` (L75-L76) - Method
  - `optics_framework.engines.vision_models.ocr_models.googlevision.GoogleVisionHelper.detect_text` (L79-L109) - Method
- `optics_framework/engines/vision_models/ocr_models/pytesseract.py`
  - `optics_framework.engines.vision_models.ocr_models.pytesseract.PytesseractHelper` (L8-L105) - Class
  - `optics_framework.engines.vision_models.ocr_models.pytesseract.PytesseractHelper.__init__` (L16-L28) - Method
  - `optics_framework.engines.vision_models.ocr_models.pytesseract.PytesseractHelper.find_element` (L32-L75) - Method
  - `optics_framework.engines.vision_models.ocr_models.pytesseract.PytesseractHelper.detect_text` (L77-L101) - Method
  - `optics_framework.engines.vision_models.ocr_models.pytesseract.PytesseractHelper.element_exist` (L103-L105) - Method
- `optics_framework/engines/vision_models/ocr_models/remote_ocr.py`
  - `optics_framework.engines.vision_models.ocr_models.remote_ocr.RemoteOCR` (L13-L221) - Class
  - `optics_framework.engines.vision_models.ocr_models.remote_ocr.RemoteOCR.__init__` (L17-L39) - Method
  - `optics_framework.engines.vision_models.ocr_models.remote_ocr.RemoteOCR.detect_text` (L41-L78) - Method
  - `optics_framework.engines.vision_models.ocr_models.remote_ocr.RemoteOCR._encode_image` (L80-L92) - Method
  - `optics_framework.engines.vision_models.ocr_models.remote_ocr.RemoteOCR._parse_ocr_results` (L94-L121) - Method
  - `optics_framework.engines.vision_models.ocr_models.remote_ocr.RemoteOCR.find_element` (L123-L149) - Method
  - `optics_framework.engines.vision_models.ocr_models.remote_ocr.RemoteOCR._decode_image_for_annotation` (L151-L164) - Method
  - `optics_framework.engines.vision_models.ocr_models.remote_ocr.RemoteOCR._find_matching_elements` (L166-L178) - Method
  - `optics_framework.engines.vision_models.ocr_models.remote_ocr.RemoteOCR._select_matching_result` (L180-L191) - Method
  - `optics_framework.engines.vision_models.ocr_models.remote_ocr.RemoteOCR._annotate_and_save` (L193-L208) - Method
  - `optics_framework.engines.vision_models.ocr_models.remote_ocr.RemoteOCR.element_exist` (L210-L221) - Method


### Optics Facade & Application Lifecycle Management
The top-level entry-point facade that every interface instantiates, wiring together config parsing, dependency/session setup, and keyword decorator registry. Includes AppManagement for app-lifecycle keywords (launch/terminate/activate/switch) invoked through the facade.


**Related Classes/Methods**:

- `optics_framework.optics.Optics`:147-1307
- `optics_framework.optics.Optics._create_dependency_config`:187-203
- `optics_framework.optics.keyword`:54-63
- `optics_framework.api.app_management.AppManagement`:7-96



**Source Files:**

- `optics_framework/api/app_management.py`
  - `optics_framework.api.app_management.AppManagement` (L7-L96) - Class
  - `optics_framework.api.app_management.AppManagement.initialise_setup` (L25-L35) - Method
  - `optics_framework.api.app_management.AppManagement.launch_app` (L37-L47) - Method
  - `optics_framework.api.app_management.AppManagement.start_appium_session` (L49-L55) - Method
  - `optics_framework.api.app_management.AppManagement.get_driver_session_id` (L57-L59) - Method
  - `optics_framework.api.app_management.AppManagement.launch_other_app` (L61-L68) - Method
  - `optics_framework.api.app_management.AppManagement.close_and_terminate_app` (L70-L79) - Method
  - `optics_framework.api.app_management.AppManagement.force_terminate_app` (L81-L88) - Method
  - `optics_framework.api.app_management.AppManagement.get_app_version` (L90-L96) - Method
- `optics_framework/optics.py`
  - `optics_framework.optics.keyword` (L54-L63) - Function
  - `optics_framework.optics.keyword.decorator` (L55-L60) - Function
  - `optics_framework.optics.keyword.decorator.wrapper` (L57-L58) - Function
  - `optics_framework.optics.library` (L65-L70) - Function
  - `optics_framework.optics.library.decorator` (L66-L67) - Function
  - `optics_framework.optics.fallback_params` (L99-L143) - Function
  - `optics_framework.optics.Optics` (L147-L1307) - Class
  - `optics_framework.optics.Optics.__init__` (L155-L168) - Method
  - `optics_framework.optics.Optics._parse_config_string` (L170-L185) - Method
  - `optics_framework.optics.Optics._create_dependency_config` (L187-L203) - Method
  - `optics_framework.optics.Optics._process_config_list` (L205-L221) - Method
  - `optics_framework.optics.Optics._resolve_param` (L223-L244) - Method
  - `optics_framework.optics.Optics.setup` (L247-L270) - Method
  - `optics_framework.optics.Optics._extract_config_data` (L272-L334) - Method
  - `optics_framework.optics.Optics.setup_from_file` (L396-L433) - Method
  - `optics_framework.optics.Optics._validate_required_keys` (L435-L452) - Method
  - `optics_framework.optics.Optics.add_element` (L455-L463) - Method
  - `optics_framework.optics.Optics.get_element_value` (L466-L474) - Method
  - `optics_framework.optics.Optics.add_api` (L477-L499) - Method
  - `optics_framework.optics.Optics.add_testcase` (L502-L510) - Method
  - `optics_framework.optics.Optics.add_module` (L513-L521) - Method
  - `optics_framework.optics.Optics.launch_app` (L618-L631) - Method
  - `optics_framework.optics.Optics.launch_other_app` (L635-L639) - Method
  - `optics_framework.optics.Optics.start_appium_session` (L643-L649) - Method
  - `optics_framework.optics.Optics.get_driver_session_id` (L653-L657) - Method
  - `optics_framework.optics.Optics.close_and_terminate_app` (L660-L664) - Method
  - `optics_framework.optics.Optics.force_terminate_app` (L668-L681) - Method
  - `optics_framework.optics.Optics.get_app_version` (L684-L688) - Method
  - `optics_framework.optics.Optics.press_element` (L693-L735) - Method
  - `optics_framework.optics.Optics.press_element._parse_aoi_value` (L714-L717) - Function
  - `optics_framework.optics.Optics.press_by_percentage` (L739-L754) - Method
  - `optics_framework.optics.Optics.press_by_coordinates` (L758-L773) - Method
  - `optics_framework.optics.Optics.press_element_with_index` (L777-L786) - Method
  - `optics_framework.optics.Optics.detect_and_press` (L790-L801) - Method
  - `optics_framework.optics.Optics.swipe` (L805-L822) - Method
  - `optics_framework.optics.Optics.swipe_by_percentage` (L826-L843) - Method
  - `optics_framework.optics.Optics.swipe_until_element_appears` (L847-L862) - Method
  - `optics_framework.optics.Optics.swipe_from_element` (L866-L881) - Method
  - `optics_framework.optics.Optics.scroll` (L885-L895) - Method
  - `optics_framework.optics.Optics.scroll_until_element_appears` (L899-L914) - Method
  - `optics_framework.optics.Optics.scroll_from_element` (L918-L933) - Method
  - `optics_framework.optics.Optics.enter_text` (L937-L950) - Method
  - `optics_framework.optics.Optics.enter_text_direct` (L954-L962) - Method
  - `optics_framework.optics.Optics.enter_text_using_keyboard` (L966-L974) - Method
  - `optics_framework.optics.Optics.enter_number` (L978-L991) - Method
  - `optics_framework.optics.Optics.press_keycode` (L995-L1003) - Method
  - `optics_framework.optics.Optics.clear_element_text` (L1007-L1015) - Method
  - `optics_framework.optics.Optics.get_text` (L1019-L1023) - Method
  - `optics_framework.optics.Optics.select_dropdown_option` (L1027-L1042) - Method
  - `optics_framework.optics.Optics.sleep` (L1046-L1050) - Method
  - `optics_framework.optics.Optics.execute_script` (L1054-L1075) - Method
  - `optics_framework.optics.Optics.validate_element` (L1080-L1095) - Method
  - `optics_framework.optics.Optics.assert_presence` (L1099-L1114) - Method
  - `optics_framework.optics.Optics.assert_visibility` (L1118-L1133) - Method
  - `optics_framework.optics.Optics.validate_screen` (L1137-L1152) - Method
  - `optics_framework.optics.Optics.assert_equality` (L1156-L1169) - Method
  - `optics_framework.optics.Optics.is_element` (L1173-L1188) - Method
  - `optics_framework.optics.Optics.get_interactive_elements` (L1191-L1207) - Method
  - `optics_framework.optics.Optics.capture_screenshot` (L1210-L1214) - Method
  - `optics_framework.optics.Optics.capture_pagesource` (L1217-L1221) - Method
  - `optics_framework.optics.Optics.get_screen_elements` (L1224-L1228) - Method
  - `optics_framework.optics.Optics.invoke_api` (L1232-L1236) - Method
  - `optics_framework.optics.Optics.read_data` (L1240-L1248) - Method
  - `optics_framework.optics.Optics.run_loop` (L1251-L1255) - Method
  - `optics_framework.optics.Optics.condition` (L1258-L1262) - Method
  - `optics_framework.optics.Optics.evaluate` (L1265-L1269) - Method
  - `optics_framework.optics.Optics.date_evaluate` (L1272-L1278) - Method
  - `optics_framework.optics.Optics.quit` (L1281-L1294) - Method
  - `optics_framework.optics.Optics.__enter__` (L1296-L1298) - Method
  - `optics_framework.optics.Optics.__exit__` (L1300-L1307) - Method


### Action Keyword Execution & AI Self-Healing
Implements concrete interaction keywords (tap, swipe, type, scroll, dropdown selection, AOI capture) and embeds the AI-based self-healing fallback path that engages an LLM/heal provider when the standard locator ladder (XPath → Text → OCR → Image) fails to resolve an element.


**Related Classes/Methods**:

- `optics_framework.api.action_keyword.ActionKeyword`:182-1178
- `optics_framework.api.action_keyword._HealProviders`:154-179
- `optics_framework.common.ai_self_heal.HealContext`:72-80
- `optics_framework.common.utils._descriptor`:465-476



**Source Files:**

- `optics_framework/api/action_keyword.py`
  - `optics_framework.api.action_keyword._parse_aoi_param` (L37-L40) - Function
  - `optics_framework.api.action_keyword._bounds_area` (L102-L113) - Function
  - `optics_framework.api.action_keyword._find_dropdown_container` (L116-L135) - Function
  - `optics_framework.api.action_keyword._raise_option_not_found` (L138-L151) - Function
  - `optics_framework.api.action_keyword._HealProviders` (L154-L179) - Class
  - `optics_framework.api.action_keyword._HealProviders.__init__` (L161-L163) - Method
  - `optics_framework.api.action_keyword._HealProviders.screenshot` (L165-L172) - Method
  - `optics_framework.api.action_keyword._HealProviders.pagesource` (L174-L179) - Method
  - `optics_framework.api.action_keyword.ActionKeyword` (L182-L1178) - Class
  - `optics_framework.api.action_keyword.ActionKeyword.__init__` (L192-L228) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._record_successful_step` (L230-L231) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._ai_self_heal` (L233-L269) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._ai_self_heal_ready` (L271-L275) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._log_heal_outcome` (L277-L309) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._render_heal_step` (L312-L314) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._pop_last_heal_info` (L316-L323) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._heal_execute` (L327-L360) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._heal_catalog` (L362-L367) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._heal_keyword_signature` (L370-L387) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._capture_screenshot_safe` (L389-L395) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._save_screenshot_if_available` (L397-L400) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._locate_and_act` (L402-L440) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._act_until_success` (L442-L496) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.press_element` (L499-L531) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.press_element.act` (L517-L526) - Function
  - `optics_framework.api.action_keyword.ActionKeyword.press_by_percentage` (L533-L546) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.press_by_coordinates` (L548-L560) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.detect_and_press` (L563-L581) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.press_checkbox` (L583-L600) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.press_radio_button` (L602-L619) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.select_dropdown_option` (L621-L667) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._find_option_element` (L669-L682) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._safe_get_interactive_elements` (L684-L694) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._safe_pagesource_hash` (L696-L707) - Method
  - `optics_framework.api.action_keyword.ActionKeyword._scroll_dropdown_until_found` (L709-L748) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.swipe` (L751-L764) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.swipe_by_percentage` (L766-L779) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.swipe_seekbar_to_right_android` (L781-L795) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.swipe_until_element_appears` (L797-L823) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.swipe_from_element` (L825-L854) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.swipe_from_element.act` (L841-L849) - Function
  - `optics_framework.api.action_keyword.ActionKeyword.scroll` (L856-L866) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.scroll_until_element_appears` (L868-L897) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.scroll_from_element` (L899-L928) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.scroll_from_element.act` (L915-L923) - Function
  - `optics_framework.api.action_keyword.ActionKeyword.enter_text` (L931-L962) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.enter_text.act` (L949-L957) - Function
  - `optics_framework.api.action_keyword.ActionKeyword.enter_number` (L1001-L1028) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.enter_number.act` (L1015-L1023) - Function
  - `optics_framework.api.action_keyword.ActionKeyword.clear_element_text` (L1047-L1074) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.clear_element_text.act` (L1060-L1069) - Function
  - `optics_framework.api.action_keyword.ActionKeyword.get_text` (L1076-L1101) - Method
  - `optics_framework.api.action_keyword.ActionKeyword.get_text.act` (L1089-L1096) - Function
  - `optics_framework.api.action_keyword.ActionKeyword.sleep` (L1103-L1109) - Method
- `optics_framework/common/ai_self_heal.py`
  - `optics_framework.common.ai_self_heal.KeywordExecResult` (L35-L44) - Class
  - `optics_framework.common.ai_self_heal.HealKeywordSpec` (L53-L56) - Class
  - `optics_framework.common.ai_self_heal.HealContext` (L72-L80) - Class
- `optics_framework/common/utils.py`
  - `optics_framework.common.utils.encode_numpy_to_png_bytes` (L213-L228) - Function
  - `optics_framework.common.utils._short_class` (L407-L410) - Function
  - `optics_framework.common.utils._is_interesting` (L413-L432) - Function
  - `optics_framework.common.utils._descriptor_text` (L435-L442) - Function
  - `optics_framework.common.utils._descriptor_id` (L445-L451) - Function
  - `optics_framework.common.utils._descriptor_bounds` (L454-L462) - Function
  - `optics_framework.common.utils._descriptor` (L465-L476) - Function
  - `optics_framework.common.utils._walk` (L479-L490) - Function
  - `optics_framework.common.utils.strip_page_source` (L493-L526) - Function




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)