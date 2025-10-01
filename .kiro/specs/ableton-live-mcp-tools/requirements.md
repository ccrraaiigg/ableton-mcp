# Requirements Document

## Introduction

This project generates comprehensive JSON tool specifications for an Ableton Live MCP (Model Context Protocol) server. The system provides complete coverage of the Ableton Live 12.3 API through the Live Object Model (LOM), enabling AI assistants to programmatically control Ableton Live through Max for Live's NodeJS server. The generated specifications serve as blueprints for actual MCP tool implementations that bridge Ableton Live's API with modern AI tooling.

## Requirements

### Requirement 1

**User Story:** As an AI assistant developer, I want comprehensive JSON schema definitions for all Live Object Model classes, so that I can build MCP tools that provide complete API coverage for Ableton Live.

#### Acceptance Criteria

1. WHEN generating tool specifications THEN the system SHALL create one JSON file per LOM class in the tools directory
2. WHEN organizing tools within JSON files THEN the system SHALL follow the strict order: children getters, property getters, property setters, functions
3. WHEN naming tools THEN the system SHALL use the format `<class>_<category>_<action>_<name>` with underscores only for namespace delineation
4. WHEN defining tool descriptions THEN the system SHALL use complete sentences with capitalization and periods
5. WHEN defining property/return descriptions THEN the system SHALL use lowercase phrases without periods

### Requirement 2

**User Story:** As a developer integrating with Ableton Live, I want structured access to children, properties, and functions of LOM classes, so that I can programmatically control all aspects of Live sessions.

#### Acceptance Criteria

1. WHEN accessing LOM class children THEN the system SHALL provide getter tools with format `<class>_children_get_<childName>`
2. WHEN accessing LOM class properties THEN the system SHALL provide getter tools with format `<class>_properties_get_<propertyName>`
3. WHEN modifying LOM class properties THEN the system SHALL provide setter tools with format `<class>_properties_set_<propertyName>` for writable properties
4. WHEN calling LOM class functions THEN the system SHALL provide function tools with format `<class>_functions_<functionName>`
5. WHEN defining tool parameters THEN the system SHALL include proper JSON schema validation for all inputs

### Requirement 3

**User Story:** As a project maintainer, I want to track implementation progress across all Live Object Model classes, so that I can ensure complete API coverage and identify missing implementations.

#### Acceptance Criteria

1. WHEN tracking LOM class implementations THEN the system SHALL maintain a progress tracker in LOM-Classes.md
2. WHEN adding new LOM class implementations THEN the system SHALL update the progress tracker to reflect completion status
3. WHEN reviewing project status THEN the system SHALL provide clear visibility into which classes are implemented and which are pending
4. WHEN validating completeness THEN the system SHALL ensure all documented LOM classes have corresponding JSON tool specifications

### Requirement 4

**User Story:** As an MCP server developer, I want JSON specifications that follow MCP protocol standards, so that I can easily implement actual MCP tools from these blueprints.

#### Acceptance Criteria

1. WHEN generating JSON specifications THEN the system SHALL conform to Model Context Protocol tool definition standards
2. WHEN defining tool schemas THEN the system SHALL include proper parameter validation and type definitions
3. WHEN structuring tool definitions THEN the system SHALL ensure compatibility with MCP server implementations
4. WHEN organizing tools THEN the system SHALL group related functionality logically within each LOM class file
5. IF a tool requires specific Live Object Model context THEN the system SHALL document the required object references in the tool description

### Requirement 5

**User Story:** As a developer working with Ableton Live automation, I want consistent naming conventions and code style across all generated specifications, so that the tools are predictable and easy to use.

#### Acceptance Criteria

1. WHEN naming variables and functions THEN the system SHALL use camelCase for all names except namespace separators
2. WHEN structuring code examples THEN the system SHALL declare all variables at the beginning of each function
3. WHEN writing conditional statements THEN the system SHALL omit curly braces for single-line if statements
4. WHEN generating JavaScript code THEN the system SHALL use vanilla JavaScript without TypeScript or bundlers
5. WHEN referencing external APIs THEN the system SHALL use the Live Object Model documentation exclusively from https://docs.cycling74.com/apiref/lom/ or its subdirectories

### Requirement 6

**User Story:** As a developer implementing LOM class hierarchies, I want inheritance to be properly handled in JSON schemas, so that subclasses don't duplicate functionality already defined in their parent classes.

#### Acceptance Criteria

1. WHEN a Live Object Model class inherits from another class THEN the system SHALL NOT repeat children getters from the superclass in the subclass JSON schema
2. WHEN a Live Object Model class inherits from another class THEN the system SHALL NOT repeat property getters from the superclass in the subclass JSON schema
3. WHEN a Live Object Model class inherits from another class THEN the system SHALL NOT repeat property setters from the superclass in the subclass JSON schema
4. WHEN a Live Object Model class inherits from another class THEN the system SHALL NOT repeat functions from the superclass in the subclass JSON schema
5. WHEN implementing inheritance THEN the system SHALL only include tools that are specific to the subclass and not already available through inheritance
