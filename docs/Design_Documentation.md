# Design Documentation

This documentation provides an overview of the repository structure and explains the purpose of the most important folders and files. Including the test concept.

---

# Overview of the Repository

```text
.
├── addons/
│   └── trmnl/
│       ├── controllers/
│       ├── models/
│       │   └── providers/
│       ├── security/
│       ├── tests/
│       ├── views/
│       ├── __init__.py
│       |── __manifest__.py
        └── trmnl_display_canvas.py
├── data/
├── docs/
├── scripts/
├── compose.yaml
├── Dockerfile
├── LICENSE
├── Makefile
├── README.md
└── requirements.txt
```

---

# General Repository Structure

## addons/

The `addons` folder contains all custom Odoo modules of the project.  
In this repository the main module is the `trmnl` module, which implements the communication between Odoo and the TRMNL e-ink displays.

---

## docs/

The `docs` folder contains technical documentation and additional project-related explanations.

---

## scripts/

The `scripts` folder contains helper scripts for development, deployment, automation, or maintenance tasks.

---

## compose.yaml

Defines the Docker Compose setup used to run the application and its services locally or in development environments.

---

## Dockerfile

Contains the instructions required to build the Docker image for the project.

---

## Makefile

Provides shortcuts for common development tasks such as starting containers, running tests, or formatting code.

---

## requirements.txt

Lists all required Python dependencies for the project.

---

# Structure of the TRMNL Module

```text
addons/trmnl/
├── controllers/
├── models/
├── security/
├── tests/
├── views/
├── __init__.py
└── __manifest__.py
```

The `trmnl` module contains the complete implementation for managing TRMNL devices inside Odoo.

---

# Content of the Folders

## controllers/

The `controllers` folder contains all HTTP API endpoints that are used by the TRMNL displays to communicate with Odoo.

The controllers process incoming requests from the devices and return the required responses.

### Main responsibilities

- Device setup and registration
- Display polling
- Log ingestion
- HTTP response handling
- API request validation

### Important files

#### `device_setup_controller.py`

Implements the `/api/setup` endpoint.

Responsible for:

- Registering new TRMNL devices
- Generating API tokens
- Returning the setup response to the device

---

#### `device_display_controller.py`

Implements the `/api/display` endpoint.

Responsible for:

- Handling display polling requests
- Validating devices and tokens
- Returning image URLs and display instructions
- Sending identify or reset commands

---

#### `device_log_controller.py`

Implements the `/api/log` endpoint.

Responsible for:

- Receiving device logs
- Validating authorization
- Storing telemetry and log data

---

### `profile_image_controller.py`

Implements the /api/profile/image/<profile_id> endpoint.

Responsible for:

- Serving generated profile preview images
- Returning rendered PNG files
- Cache-busting support
- Public image delivery for devices
- HTTP image responses

This controller allows TRMNL devices to download generated display images directly from Odoo.

---

#### `trmnl_api_base.py`

Contains shared helper methods used by all controllers.

Responsible for:

- JSON response generation
- Identifier masking for logs
- Shared API utility functions

---

## models/

The `models` folder contains the complete business logic and database models of the module.

This includes:

- Device management
- Security logic
- Device lifecycle handling
- Telemetry processing
- Display response generation
- Odoo backend functionality

---

### Core Model Files

#### `trmnl_device.py`

Core device model of the module.

Defines:

- Device database fields
- Device identity handling
- Refresh rate configuration
- Battery and telemetry fields
- Validation logic
- Helper methods

This file represents the central TRMNL device object inside Odoo.

---

#### `trmnl_device_security.py`

Contains all API token and security-related functionality.

Responsible for:

- Token generation
- PBKDF2 hashing
- Token verification
- Token promotion and adoption
- Secure token storage

---

#### `trmnl_device_lifecycle.py`

Contains device registration and lifecycle logic.

Responsible for:

- Device registration via `/api/setup`
- Unknown device handling
- Token mismatch handling
- Auto-accept logic
- Factory reset policy
- Manual device acceptance

---

#### `trmnl_device_display.py`

Contains logic for handling display requests and generating display responses.

Responsible for:

- Display payload generation
- Display request resolution
- Identify command handling
- Error response handling
- Display policy execution

---

#### `trmnl_device_telemetry.py`

Handles telemetry processing and log ingestion.

Responsible for:

- Parsing telemetry headers
- Updating device telemetry values
- Processing `/api/log` payloads
- Creating log entries
- Updating device activity statistics

---

#### `trmnl_device_log.py`

Defines the database model for stored device log entries.

Responsible for:

- Storing device logs
- Log metadata
- Readable log labels
- Log relationships to devices

---

#### `trmnl_device_ui.py`

Contains Odoo backend UI extensions and actions.

Responsible for:

- Backend-only helper fields
- Device ordering
- Button visibility logic
- Identify actions
- Opening wizards and forms

---

#### `trmnl_device_wizard.py`

Contains transient models for backend confirmation dialogs and management wizards.

Responsible for:

- Accept device wizard
- Remove device wizard
- Reset device wizard
- Display policy wizard

---

### `trmnl_profile.py`

Defines the TRMNL profile model used for configuring dynamic display content.

A profile represents the configuration for rendering Odoo application data on a TRMNL e-ink display.

Responsible for:

- Profile configuration
- Odoo model selection
- Layout selection
- Dynamic view handling
- Record filtering
- Sorting configuration
- Graph configuration
- Calendar configuration
- ORM data loading

Profiles allow administrators to configure which Odoo data should be displayed on a specific TRMNL device

---

### `trmnl_profile_render.py`

Contains the rendering orchestration and preview generation pipeline.

Responsible for:

- Automatic render timing
- Preview generation
- Renderer dispatching
- Calendar data preparation
- Display image finalization
- Footer compositing
- PNG persistence
- Device image generation

This file coordinates the complete rendering workflow between Odoo ORM data and the low-level PNG renderers.

---

## security/

The `security` folder contains access control and permission configuration for Odoo.

### Important files

#### `ir.model.access.csv`

Defines which users and groups are allowed to:

- Read records
- Create records
- Modify records
- Delete records

---

## static/

The static folder contains frontend assets and bundled resources.

### Important folders

### `fonts/`

Contains bundled TrueType fonts used for e-ink rendering.

The rendering system uses custom fonts to improve readability on TRMNL displays

---

### `src/js/

Contains custom frontend JavaScript extensions for the Odoo web client.

---

### `trmnl_layout_select_widget.js`

Defines a custom OWL widget for dynamic layout selection inside the Odoo backend.

Responsible for:

- Dynamic layout filtering
- Reactive UI updates
- Layout availability handling
- Frontend validation

The widget ensures that users can only select layouts supported by the currently selected Odoo model.

---

## tests/

The `tests` folder contains automated test cases for the TRMNL module.

The tests verify:

- API behavior
- Device registration
- Display communication
- Log handling
- Refresh rate logic
- Security functionality
- Rendering correctness
- PNG generation
- Dynamic layouts
- Graph rendering
- Calendar rendering
- Filter domains

---

### Important test files

#### `test_api_setup.py`

Tests the `/api/setup` endpoint.

---

#### `test_api_display.py`

Tests the `/api/display` endpoint and all display policies.

---

#### `test_api_log.py`

Tests the `/api/log` endpoint and log storage.

---

#### `test_device_refresh_rate.py`

Tests refresh rate calculations, validation, and UI conversion logic.

---

#### `test_api_common.py`

Contains shared utilities and helper functions used by all API tests.

---

### `test_profile_dashboard_layout.py`

Tests list and kanban rendering behavior.

---

### `test_graph_data_loading.py`

Tests graph aggregation and graph rendering logic.

---

### `test_profile_filter_domain.py`

Tests filter domain handling and validation.

---

### `test_available_view_types.py`

Tests dynamic layout availability.

---

### `test_render_preview_button.py`

Tests preview rendering and cache refreshing.

---

### `test_display_image_quality.py`

Tests image quality and e-ink rendering behavior.

---

## views/

The `views` folder contains all XML definitions for the Odoo backend user interface.

This includes:

- Form views
- List views
- Menu entries
- Wizard dialogs
- Action definitions
- Profile configuration views

### Important files

#### `trmnl_device_views.xml`

Defines the main device views inside Odoo.

---

#### `trmnl_device_wizard_views.xml`

Defines the wizard dialog views.

---

### `trmnl_profile_views.xml`

Defines the backend UI for configuring TRMNL display profiles.

---

#### `trmnl_menu.xml`

Defines the navigation menu entries for the module.

---

## Additional Rendering Utilities

### `trmnl_display_canvas.py`

Contains shared low-level rendering utilities and display configuration.

Responsible for:

- Shared display dimensions
- E-ink rendering configuration
- Font loading
- PNG compositing
- Text truncation
- Shared rendering helpers
- Black/white optimization
- Grayscale handling

This file acts as the rendering foundation for all display layouts.

---

## Module Configuration Files

### `__manifest__.py`

Defines the Odoo module configuration.

Contains:

- Module metadata
- Dependencies
- Loaded XML files
- External Python dependencies
- Version information

---

### `__init__.py`

Initializes Python packages and imports submodules so they are loaded by Odoo.

---

# Summary

The repository is structured around a modular Odoo architecture.

The TRMNL module itself is separated into multiple layers:

- `controllers/` → HTTP API endpoints
- `models/` → business logic and database models
- `views/` → Odoo backend interface
- `security/` → access permissions
- `tests/` → automated validation and API testing
- `static/` → frontend assets and fonts
- `rendering/` → dynamic e-ink PNG generation

This separation improves maintainability, readability, and scalability of the project.

# Testresults

In the testing concept we planned to do manual testing, golden image tests and automated test in the form of unit tests.

The manual testing included checking that the content of an Odoo module is displayed correctly.

The golden image tests were not done, because the rendering is being tested in automated test cases. 

The automated tests test the logic of the model as described above. They cover the test cases described in the testing concept V2. 