# Changelog

All notable changes to the FLK CRI Calculator will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [2.1.0] - 2025-10-16

### Added
- **Diluent Volume Calculation**: Explicit display of diluent (saline) volume required to reach total container volume
- **Total Volume Verification**: Auto-sum row showing drug volumes + diluent = container size with color-coded validation (green if match, red if mismatch)
- **Critical Safety Warning**: Prominent warning about diluent selection - Normal Saline ONLY for ketamine CRIs (calcium in Hartmann's causes crystallization)
- **Interactive Help Tooltips**: Question mark icons with hover tooltips for main calculator instructions and dose slider explanation
- **Enhanced Help Documentation**: Detailed diluent selection warning in Additional Information section with clinical rationale
- **Business Strategy Document**: Comprehensive `BUSINESS_STRATEGY.md` outlining monetization options and phased rollout plan

### Changed
- **Terminology Update**: Changed "Lidocaine" to "Lignocaine" throughout calculator (Australian/UK terminology)
  - Drug name in main table: "Lignocaine (20mg/mL)"
  - Loading dose: "Lignocaine (Lidocaine) (1 mg/kg)"
  - Single Pump table: "Lignocaine"
  - All tooltips and documentation updated
  - Contraindications and side effects sections updated
- **UI Improvements**:
  - Help tooltip icons styled with teal background (#0f536b) and drop shadow for better contrast against orange headers
  - Tooltips positioned as superscript next to headers for clean, professional appearance
  - Star icon in "Dual Pump (Recommended)" tab brightened when active for better visibility
  - Consistent tooltip styling across all instances (20px circles, 300px popups, proper z-index)
- **Calculator Mode Documentation**: Updated "Additional Information" section to clearly explain Standard Fluid Pump vs Syringe Driver Pump options

### Fixed
- Tooltip z-index issue resolved - tooltips now appear above slider elements (z-index: 100)
- Tooltip font inheritance issue fixed - explicit font-size, font-weight, and line-height prevent h2 styling from bleeding through
- Help tooltip positioning improved - now inline with headers rather than right-justified

### Security
- **Social Sharing Disabled**: Social sharing section hidden (`display: none`) pending specialist veterinary anaesthetist clinical verification
- Added note in README about pending clinical verification

### Technical
- Updated `updateDrugDisplay()` function signature to accept `containerVolume` parameter
- All function calls updated to pass container volume for diluent calculation
- Diluent calculation: `diluentVolume = containerVolume - (fentanylVolume + lignocaineVolume + ketamineVolume)`
- Volume verification with color coding based on match threshold (<0.01 mL difference)

## [2.0.0] - 2025-10-16

### Added
- **Three Calculator Modes**:
  - Dual Pump (Recommended): For clinics with two fluid pumps, CRI at maintenance rate with secondary line
  - Single Pump: For single-pump setups, manually adjust between maintenance and surgical rates
  - Flexible Rate: Original mode, calculate fluid rate from container size and duration
- **Syringe Driver Pump Support**: Toggle option in Dual Pump mode for highly concentrated, low-volume infusions
- **Enhanced Fentanyl Display**: All fentanyl values now show both mg and µg (micrograms) for clinical clarity
- **Social Media Sharing**: Share calculator via Facebook, X (Twitter), LinkedIn, Email, or copy direct link
- **Professional Share Icons**: SVG-based social media logos replacing emoji
- **Mode Documentation**: Comprehensive explanation of each calculator mode in Additional Information section
- **Visual Toggle Switch**: Clear toggle between Standard Fluid Pump and Syringe Driver Pump with color-coded labels
- **Print Optimization**: Enhanced CSS for clean A4 printing with compressed layout

### Changed
- **Reorganized Layout**: Better horizontal space utilization with 4-column table layouts
- **Tabbed Interface**: Clean tab navigation for switching between calculator modes
- **Dual Pump as Default**: Set Dual Pump mode as recommended default (was Flexible Rate)
- **Compressed Input Sections**: More compact form layouts to reduce visual clutter
- **Color-Coded Active States**: Toggle switch and labels change color based on selected mode (blue for standard, orange for syringe driver)
- **Reduced Orange Overload**: Narrower orange fluid-rate cells (90px max-width) for cleaner appearance
- **Improved Mobile Responsiveness**: Better adaptation to different screen sizes

### Fixed
- Container volume selection now properly triggers recalculation in Dual Pump and Single Pump modes
- Auto-container selection only updates when user's choice is too small (preserves manual selections)
- X (formerly Twitter) branding updated with correct logo and platform name

### Technical
- Refactored calculation logic into mode-specific functions: `calculateFlexibleMode()`, `calculateDualMode()`, `calculateSingleMode()`
- Added comprehensive event listeners for all new input fields
- Implemented `toggleSyringeDriver()` function with visual state management
- Enhanced print CSS with font-size adjustments and element hiding

## [1.0.0] - [Previous Date]

### Added
- Initial release of FLK CRI Calculator
- Single calculator mode (Flexible Rate)
- Patient details input (name, weight, species, date)
- Container size and duration configuration
- Dose adjustment slider with color gradient (minimum to maximum)
- Drug calculations for Fentanyl, Lidocaine, and Ketamine
- Species-specific dosing (automatic lidocaine exclusion for cats)
- Premed dose calculations (ACP, Fentanyl)
- Loading dose calculations (Lidocaine, Ketamine)
- Volume overflow warnings
- Fentanyl vial usage tracking and efficiency suggestions
- Comprehensive contraindications and safety information
- Additional information section with monitoring guidelines
- Print functionality

### Drug Concentrations (Unchanged)
- Fentanyl: 0.05 mg/mL (50 µg/mL)
- Lidocaine: 20 mg/mL
- Ketamine: 100 mg/mL

### Dose Ranges (Unchanged)
- Fentanyl: 0.002 - 0.006 mg/kg/hr
- Lidocaine: 0.6 - 3.0 mg/kg/hr (dogs only)
- Ketamine: 0.12 - 1.2 mg/kg/hr

---

## Version Numbering

- **Major version (X.0.0)**: Breaking changes or major new features
- **Minor version (0.X.0)**: New features, no breaking changes
- **Patch version (0.0.X)**: Bug fixes and minor improvements
