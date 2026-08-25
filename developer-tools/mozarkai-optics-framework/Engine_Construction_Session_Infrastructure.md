```mermaid
graph LR
    Session_Bound_Builder_Configuration_Facade["Session-Bound Builder & Configuration Facade"]
    Generic_Engine_Factory_Fallback_Registry["Generic Engine Factory & Fallback Registry"]
    Session_Bound_Builder_Configuration_Facade -- "delegates engine instantiation via classmethod dispatch" --> Generic_Engine_Factory_Fallback_Registry
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Web platform](https://img.shields.io/badge/Open%20in-Web%20platform-2563EB?style=flat-square)](https://app.codeboarding.org)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/diagrams)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

The builder, factory, and session layer that assembles and configures concrete engines the API and strategy layers depend on. Reads config.yaml-driven configuration to construct and bind concrete driver/element-source/vision/text/LLM engine instances per test session via factories and OpticsBuilder, manages session lifecycle state, and provides text-based error/state detection utilities consumed by the Verifier.

### Session-Bound Builder & Configuration Facade
Owns the per-session lifecycle and fluent configuration/instantiation API that translates config.yaml-derived settings into concrete engine instances handed to API-layer consumers (ActionKeyword, AppManagement, Verifier), and provides text-based state/error detection utilities used during verification.


**Related Classes/Methods**:

- `optics_framework.common.optics_builder.OpticsBuilder`:31-201
- `optics_framework.common.session_manager.Session`:100-146
- `optics_framework.common.error_detection.detect_errors_in_text`:80-119
- `optics_framework.common.factories.DeviceFactory.get_driver`:15-28



**Source Files:**

- `optics_framework/api/app_management.py`
  - `optics_framework.api.app_management.AppManagement.__init__` (L18-L21) - Method
- `optics_framework/api/verifier.py`
  - `optics_framework.api.verifier.Verifier.__init__` (L16-L27) - Method
- `optics_framework/common/error_detection.py`
  - `optics_framework.common.error_detection.extract_visible_text` (L35-L77) - Function
  - `optics_framework.common.error_detection.detect_errors_in_text` (L80-L119) - Function
- `optics_framework/common/factories.py`
  - `optics_framework.common.factories.DeviceFactory` (L11-L28) - Class
  - `optics_framework.common.factories.DeviceFactory.get_driver` (L15-L28) - Method
- `optics_framework/common/optics_builder.py`
  - `optics_framework.common.optics_builder.OpticsConfig` (L21-L28) - Class
  - `optics_framework.common.optics_builder.OpticsBuilder` (L31-L201) - Class
  - `optics_framework.common.optics_builder.OpticsBuilder.__init__` (L36-L42) - Method
  - `optics_framework.common.optics_builder.OpticsBuilder.normalise_config` (L44-L67) - Method
  - `optics_framework.common.optics_builder.OpticsBuilder.add_driver` (L70-L72) - Method
  - `optics_framework.common.optics_builder.OpticsBuilder.add_element_source` (L74-L78) - Method
  - `optics_framework.common.optics_builder.OpticsBuilder.add_image_detection` (L80-L94) - Method
  - `optics_framework.common.optics_builder.OpticsBuilder.add_text_detection` (L96-L106) - Method
  - `optics_framework.common.optics_builder.OpticsBuilder.add_llm` (L108-L112) - Method
  - `optics_framework.common.optics_builder.OpticsBuilder.instantiate_driver` (L115-L124) - Method
  - `optics_framework.common.optics_builder.OpticsBuilder.instantiate_element_source` (L126-L136) - Method
  - `optics_framework.common.optics_builder.OpticsBuilder.instantiate_image_detection` (L138-L146) - Method
  - `optics_framework.common.optics_builder.OpticsBuilder.instantiate_text_detection` (L148-L156) - Method
  - `optics_framework.common.optics_builder.OpticsBuilder.instantiate_llm` (L158-L164) - Method
  - `optics_framework.common.optics_builder.OpticsBuilder.get_driver` (L167-L170) - Method
  - `optics_framework.common.optics_builder.OpticsBuilder.get_element_source` (L172-L175) - Method
  - `optics_framework.common.optics_builder.OpticsBuilder.get_image_detection` (L177-L180) - Method
  - `optics_framework.common.optics_builder.OpticsBuilder.get_text_detection` (L182-L185) - Method
  - `optics_framework.common.optics_builder.OpticsBuilder.get_llm` (L187-L190) - Method
- `optics_framework/common/session_manager.py`
  - `optics_framework.common.session_manager._to_dict_list` (L18-L26) - Function
  - `optics_framework.common.session_manager._get_enabled_config_list` (L29-L37) - Function
  - `optics_framework.common.session_manager.Session` (L100-L146) - Class
  - `optics_framework.common.session_manager.Session.__init__` (L103-L146) - Method
- `optics_framework/optics.py`
  - `optics_framework.optics.Optics.capture_and_detect` (L566-L613) - Method


### Generic Engine Factory & Fallback Registry
Provides the reusable, config-driven mechanism for dynamically discovering, loading, and caching concrete engine implementations from plugin packages, and composes multiple configured engines into a resilient fallback chain consumed by the builder.


**Related Classes/Methods**:

- `optics_framework.common.base_factory.GenericFactory`:14-204
- `optics_framework.common.base_factory.InstanceFallback`:207-252
- `optics_framework.common.factories.ElementSourceFactory`:31-79
- `optics_framework.common.factories.ImageFactory`:82-88
- `optics_framework.common.factories.LLMFactory`:100-106



**Source Files:**

- `optics_framework/common/base_factory.py`
  - `optics_framework.common.base_factory.GenericFactory` (L14-L204) - Class
  - `optics_framework.common.base_factory.GenericFactory.ModuleRegistry` (L15-L21) - Class
  - `optics_framework.common.base_factory.GenericFactory.ModuleRegistry.Config` (L20-L21) - Class
  - `optics_framework.common.base_factory.GenericFactory.register_package` (L26-L31) - Method
  - `optics_framework.common.base_factory.GenericFactory._load_package` (L34-L41) - Method
  - `optics_framework.common.base_factory.GenericFactory._register_submodules` (L44-L51) - Method
  - `optics_framework.common.base_factory.GenericFactory._register_subpackage` (L54-L61) - Method
  - `optics_framework.common.base_factory.GenericFactory._locate_implementation` (L64-L69) - Method
  - `optics_framework.common.base_factory.GenericFactory.create_instance_dynamic` (L72-L112) - Method
  - `optics_framework.common.base_factory.GenericFactory.create_instance` (L115-L119) - Method
  - `optics_framework.common.base_factory.GenericFactory._create_or_retrieve` (L122-L158) - Method
  - `optics_framework.common.base_factory.GenericFactory._load_module` (L161-L171) - Method
  - `optics_framework.common.base_factory.GenericFactory._extract_names` (L174-L188) - Method
  - `optics_framework.common.base_factory.GenericFactory._create_fallback` (L191-L198) - Method
  - `optics_framework.common.base_factory.GenericFactory.clear_instances` (L201-L204) - Method
  - `optics_framework.common.base_factory.InstanceFallback` (L207-L252) - Class
  - `optics_framework.common.base_factory.InstanceFallback.Config` (L212-L213) - Class
  - `optics_framework.common.base_factory.InstanceFallback.__init__` (L215-L217) - Method
  - `optics_framework.common.base_factory.InstanceFallback.active_instance` (L220-L229) - Method
  - `optics_framework.common.base_factory.InstanceFallback.__getattr__` (L231-L252) - Method
  - `optics_framework.common.base_factory.InstanceFallback.__getattr__.fallback_method` (L232-L251) - Function
- `optics_framework/common/factories.py`
  - `optics_framework.common.factories.ElementSourceFactory` (L31-L79) - Class
  - `optics_framework.common.factories.ElementSourceFactory.get_driver` (L35-L49) - Method
  - `optics_framework.common.factories.ElementSourceFactory._load_element_source_implementation` (L52-L58) - Method
  - `optics_framework.common.factories.ElementSourceFactory._find_matching_driver` (L61-L71) - Method
  - `optics_framework.common.factories.ElementSourceFactory._build_driver_kwargs` (L74-L79) - Method
  - `optics_framework.common.factories.ImageFactory` (L82-L88) - Class
  - `optics_framework.common.factories.ImageFactory.get_driver` (L86-L88) - Method
  - `optics_framework.common.factories.TextFactory` (L91-L97) - Class
  - `optics_framework.common.factories.TextFactory.get_driver` (L95-L97) - Method
  - `optics_framework.common.factories.LLMFactory` (L100-L106) - Class
  - `optics_framework.common.factories.LLMFactory.get_driver` (L104-L106) - Method




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)