# Ghana Invoice Generator ✨

A **free, open-source, single-page web application** for creating professional invoices. Perfect for small businesses in Ghana and beyond.

## 🎯 Features

### ✅ Core Functionality
- **Business Information** – Name, address, phone, email, optional logo
- **Client Details** – Name and address
- **Invoice Details** – Invoice number and date (auto-sets to today)
- **Line Items** – Add/remove rows with description, quantity, unit price
- **Real-Time Calculations** – Instant updates for subtotal, VAT, discount, and grand total
- **Live Preview** – See invoice as you type
- **Multi-Currency Support** – GHS (₵), USD ($), EUR (€)
- **Payment Terms & Notes** – Free text for terms, bank details, etc.

### 📊 Calculations
- ✅ **Subtotal** – Auto-calculated from line items
- ✅ **VAT** – Optional 15% Ghana VAT (toggle on/off)
- ✅ **Discount** – Optional flat discount
- ✅ **Grand Total** – Automatically computed (subtotal + VAT - discount)
- ✅ **No Rounding Errors** – Proper decimal precision throughout

### 💾 Export Options
- **Download as PDF** – Client-side generation (no server calls)
- **Print** – Browser native print with print-specific CSS
- **Responsive Design** – Works perfectly on desktop, tablet, and mobile

### 🔒 Privacy & Offline
- ✅ **100% Client-Side** – No backend, no database, no data collection
- ✅ **Works Offline** – After first load, works completely offline
- ✅ **No Login Required** – Zero authentication friction
- ✅ **No Invoice History** – Fresh start each session (by design)

## 🚀 Getting Started

### Online (Recommended)
1. Visit the live app: `https://yourusername.github.io/invoice-generator/`
2. Fill in your business and invoice details
3. Add line items
4. Download as PDF or print

### Offline
1. Download or clone this repository
2. Open `index.html` in any modern web browser
3. Works instantly—no dependencies to install

## 📱 Browser Support
- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## 🎨 Design
- Clean, professional aesthetic inspired by Ghanaian colors (forest green + gold)
- Fully responsive – optimized for all screen sizes
- Print-friendly layout
- XSS-protected HTML escaping on all inputs

## 📝 Usage Examples

### Example Workflow
1. Enter your business name: "Accra Tech Solutions"
2. Add your phone and email
3. Enter client name: "John Mensah"
4. Set invoice number: "INV-001"
5. Add line items:
   - Web Design Service | 1 × ₵5,000
   - Logo Design | 1 × ₵2,500
6. Toggle VAT on (15% automatically applied)
7. Add optional discount if applicable
8. Include payment terms: "Payment due in 7 days"
9. Click "Download as PDF" or "Print"

## ⚙️ Technical Details

### Architecture
- **Single HTML file** – No build process, no dependencies to install
- **Embedded CSS** – All styling included
- **Vanilla JavaScript** – No frameworks (easier to customize)
- **External CDN Libraries** – jsPDF and html2canvas for PDF generation

### Libraries Used
- [jsPDF](https://github.com/parallax/jsPDF) – PDF generation (client-side)
- [html2canvas](https://html2canvas.hertzen.com/) – HTML to canvas conversion

### Key Functions
- `updatePreview()` – Live preview updates
- `addLineItem()` / `deleteLineItem()` – Manage line items
- `calculateTotals()` – Compute subtotal, VAT, discount, total
- `downloadPDF()` – Generate and save PDF
- `formatCurrency()` – Currency formatting with proper symbols

## 🛠️ Customization

### Adding More Currencies
Edit the `getCurrencySymbol()` function:
```javascript
const symbols = {
    'GHS': '₵',
    'USD': '$',
    'EUR': '€',
    'GBP': '£'  // Add new currency here
};
```

### Changing VAT Rate
Modify the VAT calculation in `calculateTotals()`:
```javascript
const vat = vatApplied ? subtotal * 0.18 : 0;  // Change 0.15 to your rate
```

### Color Scheme
Update CSS variables in `:root` section:
```css
--primary: #1a472a;      /* Primary color */
--accent: #d4a574;       /* Accent color */
```

## 🐛 Known Limitations

1. **Logo storage** – Uploads are stored in browser memory (refresh loses data)
2. **No history** – Each session starts fresh (by design for privacy)
3. **Max 50 line items** – Prevents performance issues
4. **PDF size** – Large logos may increase file size

## ✨ Quality Assurance

- ✅ All calculations tested for accuracy
- ✅ Handles edge cases (empty fields, zero quantities, max items)
- ✅ No console errors in production
- ✅ XSS-protected against malicious input
- ✅ Fully responsive (tested on mobile, tablet, desktop)
- ✅ Works 100% offline after first load

## 📄 License

Open source. Use, modify, and distribute freely.

## 🤝 Contributing

Found a bug or have a feature request? Open an issue or submit a pull request.

## 📞 Support

For issues or questions:
1. Check the browser console for error messages
2. Ensure you're using a modern browser (Chrome, Firefox, Safari, Edge)
3. Try clearing browser cache if something looks off
4. Open an issue on GitHub

## 🎉 Next Steps

Potential future enhancements (out of scope for v1):
- Recurring invoice templates
- Invoice numbering sequences
- Client saved defaults
- Multiple language support
- Tax customization per line item
- Payment reminders via email
- Invoice signing/digital signature
- Multi-page PDF support

---

**Built with ❤️ for small businesses in Ghana and beyond.**

*Currently v1.0 – Fully functional, production-ready.*
