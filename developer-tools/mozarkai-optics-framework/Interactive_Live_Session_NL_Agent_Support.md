```mermaid
graph LR
    Live_Session_Controller_NL_Bridge["Live Session Controller & NL Bridge"]
    Live_Terminal_UI_Session_Runtime["Live Terminal UI & Session Runtime"]
    Live_Session_Controller_NL_Bridge -- "Result DTO return for step/NL/save outcomes" --> Live_Terminal_UI_Session_Runtime
    Live_Terminal_UI_Session_Runtime -- "Process bootstrap / lifecycle ownership" --> Live_Session_Controller_NL_Bridge
```

[![CodeBoarding](https://img.shields.io/badge/Generated%20by-CodeBoarding-9cf?style=flat-square)](https://github.com/CodeBoarding/CodeBoarding)[![Web platform](https://img.shields.io/badge/Open%20in-Web%20platform-2563EB?style=flat-square)](https://app.codeboarding.org)[![Demo](https://img.shields.io/badge/Try%20our-Demo-blue?style=flat-square)](https://www.codeboarding.org/diagrams)[![Contact](https://img.shields.io/badge/Contact%20us%20-%20contact@codeboarding.org-lightgrey?style=flat-square)](mailto:contact@codeboarding.org)

## Details

Supports interactive/human-in-the-loop execution — an in-process live controller that runs keyword steps derived from natural-language instructions, tracks step/session results for the TUI, and buffers logs for live display, bridging the NL-agent's keyword specifications to the runtime.

### Live Session Controller & NL Bridge
Owns the persistent Optics session/driver/registry and domain model for interactive execution. Parses and dispatches keyword calls with ${element} fallback expansion and multi-candidate retry, buffers/commits recorded steps to CSV on /save, lazily builds and drives the NaturalLanguageAgent translating NL instructions into KeywordSpec-cataloged keyword calls via ReAct loop, and captures per-call execution logs to surface winning locator strategy or silent failures.


**Related Classes/Methods**:

- `optics_framework.helper.live.LiveController`:288-1277
- `optics_framework.common.nl_agent.KeywordSpec`:28-32
- `optics_framework.common.logging_config.LogCaptureBuffer`:140-155
- `optics_framework.helper.live.NLStep`:129-134
- `optics_framework.helper.live_tui.LiveCompleter`:117-165



**Source Files:**

- `optics_framework/common/logging_config.py`
  - `optics_framework.common.logging_config.LogCaptureBuffer` (L140-L155) - Class
  - `optics_framework.common.logging_config.LogCaptureBuffer.__init__` (L144-L146) - Method
  - `optics_framework.common.logging_config.LogCaptureBuffer.emit` (L148-L149) - Method
  - `optics_framework.common.logging_config.LogCaptureBuffer.clear` (L151-L152) - Method
  - `optics_framework.common.logging_config.LogCaptureBuffer.get_records` (L154-L155) - Method
- `optics_framework/common/nl_agent.py`
  - `optics_framework.common.nl_agent.KeywordSpec` (L28-L32) - Class
- `optics_framework/common/utils.py`
  - `optics_framework.common.utils.escape_csv_value` (L152-L163) - Function
- `optics_framework/helper/live.py`
  - `optics_framework.helper.live.ActionStatus` (L75-L81) - Class
  - `optics_framework.helper.live.NLRunStatus` (L84-L90) - Class
  - `optics_framework.helper.live.NLStepKind` (L93-L98) - Class
  - `optics_framework.helper.live.NLStep` (L129-L134) - Class
  - `optics_framework.helper.live.NLSummary` (L138-L145) - Class
  - `optics_framework.helper.live.keyword_to_title` (L148-L153) - Function
  - `optics_framework.helper.live.SaveConflictError` (L156-L168) - Class
  - `optics_framework.helper.live.SaveConflictError.__init__` (L165-L168) - Method
  - `optics_framework.helper.live.SaveResult` (L172-L183) - Class
  - `optics_framework.helper.live.LiveController` (L288-L1277) - Class
  - `optics_framework.helper.live.LiveController.keyword_names` (L437-L439) - Method
  - `optics_framework.helper.live.LiveController.keyword_signature` (L441-L467) - Method
  - `optics_framework.helper.live.LiveController._iter_element_files` (L471-L477) - Method
  - `optics_framework.helper.live.LiveController._merge_elements` (L480-L486) - Method
  - `optics_framework.helper.live.LiveController.ensure_elements_loaded` (L488-L504) - Method
  - `optics_framework.helper.live.LiveController.element_names` (L506-L511) - Method
  - `optics_framework.helper.live.LiveController.element_first_locator` (L513-L517) - Method
  - `optics_framework.helper.live.LiveController.run_keyword` (L521-L529) - Method
  - `optics_framework.helper.live.LiveController._execute_line` (L531-L601) - Method
  - `optics_framework.helper.live.LiveController._is_fallback_error` (L604-L610) - Method
  - `optics_framework.helper.live.LiveController._run_single_combo` (L612-L635) - Method
  - `optics_framework.helper.live.LiveController._attempt_combos` (L637-L674) - Method
  - `optics_framework.helper.live.LiveController._build_candidates` (L676-L691) - Method
  - `optics_framework.helper.live.LiveController._find_error_log` (L720-L734) - Method
  - `optics_framework.helper.live.LiveController._winning_strategy` (L737-L748) - Method
  - `optics_framework.helper.live.LiveController._format_error` (L751-L759) - Method
  - `optics_framework.helper.live.LiveController.save` (L763-L839) - Method
  - `optics_framework.helper.live.LiveController._sanitize_name` (L842-L844) - Method
  - `optics_framework.helper.live.LiveController._read_rows` (L847-L852) - Method
  - `optics_framework.helper.live.LiveController._existing_names` (L854-L860) - Method
  - `optics_framework.helper.live.LiveController._write_rows` (L863-L869) - Method
  - `optics_framework.helper.live.LiveController._append_module_csv` (L871-L895) - Method
  - `optics_framework.helper.live.LiveController._append_test_case_csv` (L897-L906) - Method
  - `optics_framework.helper.live.LiveController._ensure_elements_stub` (L909-L914) - Method
  - `optics_framework.helper.live.LiveController._enabled_driver_caps` (L918-L924) - Method
  - `optics_framework.helper.live.LiveController._get_target_id_from_config` (L935-L953) - Method
  - `optics_framework.helper.live.LiveController.supports_adb_hotplug` (L974-L983) - Method
  - `optics_framework.helper.live.LiveController.list_android_devices` (L986-L1003) - Method
  - `optics_framework.helper.live.LiveController.list_ios_devices` (L1006-L1028) - Method
  - `optics_framework.helper.live.LiveController.list_devices` (L1031-L1041) - Method
  - `optics_framework.helper.live.LiveController.screenshot_png_bytes` (L1099-L1108) - Method
  - `optics_framework.helper.live.LiveController._nl_catalog` (L1122-L1126) - Method
  - `optics_framework.helper.live.LiveController.page_source` (L1128-L1145) - Method
  - `optics_framework.helper.live.LiveController._nl_execute` (L1147-L1155) - Method
  - `optics_framework.helper.live.LiveController._get_nl_agent` (L1157-L1176) - Method
  - `optics_framework.helper.live.LiveController._nl_action_result` (L1179-L1197) - Method
  - `optics_framework.helper.live.LiveController._emit_nl_step` (L1199-L1208) - Method
  - `optics_framework.helper.live.LiveController.run_natural_language` (L1210-L1255) - Method
- `optics_framework/helper/live_tui.py`
  - `optics_framework.helper.live_tui.LiveCompleter` (L117-L165) - Class
  - `optics_framework.helper.live_tui.LiveCompleter.__init__` (L120-L122) - Method
  - `optics_framework.helper.live_tui.LiveCompleter._element_completions` (L124-L134) - Method
  - `optics_framework.helper.live_tui.LiveCompleter._keyword_completions` (L136-L153) - Method
  - `optics_framework.helper.live_tui.LiveCompleter.get_completions` (L155-L165) - Method
  - `optics_framework.helper.live_tui.LiveTUI.open_popup` (L324-L328) - Method
  - `optics_framework.helper.live_tui.LiveTUI._cmd_elements` (L759-L774) - Method
  - `optics_framework.helper.live_tui.LiveTUI._cmd_help` (L801-L803) - Method
  - `optics_framework.helper.live_tui.LiveTUI._start_device_monitor._poll_devices` (L854-L858) - Function


### Live Terminal UI & Session Runtime
The prompt_toolkit-based full-screen interactive shell that renders step/session history and status, forwards typed keywords or NL instructions to the controller asynchronously off the UI thread, manages overlays/popups (keyword browser, device picker, help), and drives the process entry point plus session bootstrap/teardown including console-log silencing, screenshot capture, and device targeting/teardown at exit.


**Related Classes/Methods**:

- `optics_framework.helper.live_tui.LiveTUI`:168-887
- `optics_framework.helper.live.ActionResult`:111-125
- `optics_framework.helper.live.live_main`:1411-1448
- `optics_framework.helper.live._silence_console_logging`:1295-1359
- `optics_framework.helper.live.LiveController.teardown`:1259-1277



**Source Files:**

- `optics_framework/helper/live.py`
  - `optics_framework.helper.live.ActionResult` (L111-L125) - Class
  - `optics_framework.helper.live.LiveController._teardown_live_logging` (L405-L420) - Method
  - `optics_framework.helper.live.LiveController.active_target` (L955-L963) - Method
  - `optics_framework.helper.live.LiveController.capture_screenshot` (L1081-L1097) - Method
  - `optics_framework.helper.live.LiveController.teardown` (L1259-L1277) - Method
  - `optics_framework.helper.live._silence_console_logging` (L1295-L1359) - Function
  - `optics_framework.helper.live._silence_console_logging._is_console_handler` (L1306-L1310) - Function
  - `optics_framework.helper.live._redirect_stderr_fd` (L1363-L1408) - Function
  - `optics_framework.helper.live.live_main` (L1411-L1448) - Function
- `optics_framework/helper/live_tui.py`
  - `optics_framework.helper.live_tui.LiveTUI` (L168-L887) - Class
  - `optics_framework.helper.live_tui.LiveTUI.__init__` (L171-L205) - Method
  - `optics_framework.helper.live_tui.LiveTUI._render_history` (L209-L215) - Method
  - `optics_framework.helper.live_tui.LiveTUI._render_entry` (L218-L253) - Method
  - `optics_framework.helper.live_tui.LiveTUI._history_cursor` (L255-L257) - Method
  - `optics_framework.helper.live_tui.LiveTUI._ghost_text` (L261-L277) - Method
  - `optics_framework.helper.live_tui.LiveTUI._render_status` (L281-L293) - Method
  - `optics_framework.helper.live_tui.LiveTUI._render_overlay` (L297-L306) - Method
  - `optics_framework.helper.live_tui.LiveTUI._overlay_cursor` (L308-L309) - Method
  - `optics_framework.helper.live_tui.LiveTUI.open_overlay` (L311-L317) - Method
  - `optics_framework.helper.live_tui.LiveTUI.close_overlays` (L319-L322) - Method
  - `optics_framework.helper.live_tui.LiveTUI._build_application` (L332-L421) - Method
  - `optics_framework.helper.live_tui.LiveTUI._input_prefix` (L423-L426) - Method
  - `optics_framework.helper.live_tui.LiveTUI._on_enter` (L430-L439) - Method
  - `optics_framework.helper.live_tui.LiveTUI._on_tab` (L441-L446) - Method
  - `optics_framework.helper.live_tui.LiveTUI._on_shift_tab` (L448-L451) - Method
  - `optics_framework.helper.live_tui.LiveTUI._move_overlay` (L453-L455) - Method
  - `optics_framework.helper.live_tui.LiveTUI._recall_history` (L457-L463) - Method
  - `optics_framework.helper.live_tui.LiveTUI._on_overlay_enter` (L465-L470) - Method
  - `optics_framework.helper.live_tui.LiveTUI._build_key_bindings` (L472-L531) - Method
  - `optics_framework.helper.live_tui.LiveTUI._build_key_bindings._` (L528-L529) - Function
  - `optics_framework.helper.live_tui.LiveTUI._append` (L535-L537) - Method
  - `optics_framework.helper.live_tui.LiveTUI._info` (L539-L540) - Method
  - `optics_framework.helper.live_tui.LiveTUI._submit` (L542-L554) - Method
  - `optics_framework.helper.live_tui.LiveTUI._run_keyword_async` (L556-L580) - Method
  - `optics_framework.helper.live_tui.LiveTUI._run_keyword_async.task` (L562-L577) - Function
  - `optics_framework.helper.live_tui.LiveTUI._toggle_nl_mode` (L584-L599) - Method
  - `optics_framework.helper.live_tui.LiveTUI._abort_nl` (L601-L606) - Method
  - `optics_framework.helper.live_tui.LiveTUI._nl_summary_message` (L609-L623) - Method
  - `optics_framework.helper.live_tui.LiveTUI._run_nl_async` (L625-L672) - Method
  - `optics_framework.helper.live_tui.LiveTUI._run_nl_async.on_step` (L634-L647) - Function
  - `optics_framework.helper.live_tui.LiveTUI._run_nl_async.on_step._apply` (L643-L645) - Function
  - `optics_framework.helper.live_tui.LiveTUI._run_nl_async.task` (L649-L669) - Function
  - `optics_framework.helper.live_tui.LiveTUI._handle_command` (L674-L691) - Method
  - `optics_framework.helper.live_tui.LiveTUI._cmd_save` (L693-L724) - Method
  - `optics_framework.helper.live_tui.LiveTUI._cmd_device` (L726-L748) - Method
  - `optics_framework.helper.live_tui.LiveTUI._switch_device` (L750-L757) - Method
  - `optics_framework.helper.live_tui.LiveTUI._cmd_screenshot` (L776-L799) - Method
  - `optics_framework.helper.live_tui.LiveTUI._cmd_screenshot.task` (L785-L796) - Function
  - `optics_framework.helper.live_tui.LiveTUI._cmd_quit` (L805-L806) - Method
  - `optics_framework.helper.live_tui.LiveTUI._request_quit` (L808-L817) - Method
  - `optics_framework.helper.live_tui.LiveTUI._open_keyword_browser` (L821-L824) - Method
  - `optics_framework.helper.live_tui.LiveTUI._pick_keyword` (L826-L828) - Method
  - `optics_framework.helper.live_tui.LiveTUI._auto_init_device` (L832-L848) - Method
  - `optics_framework.helper.live_tui.LiveTUI._start_device_monitor` (L850-L873) - Method
  - `optics_framework.helper.live_tui.LiveTUI._start_device_monitor._monitor` (L860-L871) - Function
  - `optics_framework.helper.live_tui.LiveTUI._on_startup` (L875-L884) - Method
  - `optics_framework.helper.live_tui.LiveTUI.run` (L886-L887) - Method




### [FAQ](https://github.com/CodeBoarding/GeneratedOnBoardings/tree/main?tab=readme-ov-file#faq)