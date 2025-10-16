# FLK CRI Calculator

A veterinary calculator for Fentanyl-Lidocaine-Ketamine (FLK) Constant Rate Infusion dosing for dogs and cats.

## Overview

This calculator helps veterinary professionals accurately calculate drug doses, concentrations, and pump rates for multi-modal analgesia using the FLK protocol. It supports multiple clinical workflows to accommodate different clinic setups and equipment.

## Features

### Three Calculator Modes

1. **Dual Pump (Recommended)** ⭐
   - For clinics with two fluid pumps
   - CRI runs at constant maintenance rate (typically 3 mL/kg/hr)
   - Secondary line adds plain fluids intra-operatively
   - Most flexible and safest approach
   - **Syringe Driver Option**: Toggle to use highly concentrated, low-volume infusions via syringe driver pump

2. **Single Pump**
   - For clinics with only one fluid pump
   - Manually adjust pump rate between maintenance (3 mL/kg/hr) and surgical rates (5 mL/kg/hr)
   - Drug concentrations calculated for target doses at surgical rate
   - Automatic calculation of reduced doses during pre/post-op phases

3. **Flexible Rate**
   - Original calculator mode
   - Choose container size and duration
   - Calculator determines required fluid rate
   - Useful for working backwards from specific container sizes

### Key Capabilities

- **Species-specific dosing**: Automatic adjustment for dogs vs cats (lidocaine excluded for feline patients)
- **Dose adjustment slider**: Minimum to maximum ranges with visual color gradient
- **Fentanyl in micrograms**: All fentanyl values displayed in both mg and µg for clarity
- **Auto-container selection**: Suggests appropriate container sizes based on calculated volumes
- **Volume alerts**: Warns if drug volume exceeds container capacity
- **Fentanyl vial efficiency**: Tracks vial usage and suggests dose adjustments to minimize waste
- **Premed and loading doses**: Automatic calculation of ACP, fentanyl, lidocaine, and ketamine doses
- **Social sharing**: Easy sharing via Facebook, X (Twitter), LinkedIn, Email, or direct link copy
- **Print-optimized**: Clean layout designed to fit on single A4 page

### Drug Concentrations

- Fentanyl: 0.05 mg/mL (50 µg/mL)
- Lidocaine: 20 mg/mL
- Ketamine: 100 mg/mL

### Dose Ranges

- **Fentanyl**: 0.002 - 0.006 mg/kg/hr (2 - 6 µg/kg/hr)
- **Lidocaine**: 0.6 - 3.0 mg/kg/hr (dogs only)
- **Ketamine**: 0.12 - 1.2 mg/kg/hr

## Usage

1. Select your calculator mode (Dual Pump recommended)
2. Enter patient details (name, weight, species, date)
3. Configure mode-specific settings:
   - **Dual Pump**: Set CRI rate, duration, and secondary line rate
   - **Single Pump**: Set phase durations and fluid rates
   - **Flexible Rate**: Choose container and duration
4. Adjust dose level using slider (Medium is typical starting point)
5. Review calculated drug volumes, concentrations, and pump rates
6. Check premed and loading dose recommendations
7. Print or share with colleagues

### Syringe Driver Pump

When using the Syringe Driver option in Dual Pump mode:
- Delivers highly concentrated CRI at very low rates (e.g., 1.25 mL/hr)
- Minimizes drug usage - ideal for small patients or expensive medications
- Requires separate plain fluid pump set at maintenance/surgical rates
- Common in referral centers and teaching hospitals

## Technical Details

- **Single-page application**: Pure HTML/CSS/JavaScript, no build process required
- **No backend**: All calculations performed client-side
- **No dependencies**: Uses vanilla JavaScript and inline SVG icons
- **Mobile-responsive**: Works on tablets and phones
- **Print-friendly**: Optimized CSS for A4 paper printing

## Installation & Deployment

### Local Development
Simply open `index.html` in any modern web browser.

### Production Deployment
Currently deployed on Digital Ocean App Platform. Any standard static hosting will work:
- Digital Ocean App Platform
- Netlify
- Vercel
- GitHub Pages
- AWS S3 + CloudFront

## Safety & Contraindications

The calculator includes comprehensive information on:
- Drug contraindications for fentanyl, lidocaine, and ketamine
- Monitoring requirements
- Drug interactions
- Side effects and management
- Patient selection criteria

**Important**: This calculator is a tool to assist with calculations. Always verify doses and use clinical judgment. Monitor patients continuously during CRI administration.

## Contributing

This is a professional veterinary tool. Contributions should:
- Maintain accuracy of veterinary dosing
- Follow existing code style
- Be tested thoroughly
- Include documentation updates

## License

[Add your license here]

## Version History

See [CHANGELOG.md](CHANGELOG.md) for detailed version history.

## Contact & Support

[Add your contact information or support details]

---

**Disclaimer**: This calculator is provided as a clinical aid. Users are responsible for verifying all calculations and using appropriate clinical judgment. Always follow institutional protocols and manufacturer guidelines.
