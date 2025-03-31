# Pretty Proposals

**Contributors:** Willem Prinsloo
**Tags:** proposals, client management, pdf, email, admin, crm, invoice
**Requires at least:** 5.0
**Tested up to:** 6.7
**Stable tag:** 1.0.9
**Requires PHP:** 7.4
**License:** GPLv2 or later
**License URI:** https://www.gnu.org/licenses/gpl-2.0.html

Manage client proposals and basic invoicing directly within WordPress using Pretty Proposals. Create, customize, PDF, and send proposals and invoices with ease.

## Description

Pretty Proposals allows designers, developers, and freelancers to streamline their proposal and invoicing workflow directly within their WordPress dashboard.

**Core Features:**

*   **Proposal Management:** Create and manage proposals using a dedicated Custom Post Type (`pretty_proposal`).
*   **Custom Fields:** Includes fields for Client Name, Company, Email, **Client Address**, **Client VAT Number (Optional)**, Scope of Work (main editor), and line items for pricing.
*   **Status Tracking:** Track proposal status (Draft, Sent, Accepted, Rejected) via a simple dropdown.
*   **PDF Generation (Proposals & Invoices):** 
    *   Automatically generates professional PDF documents for proposals and invoices using the FPDF library.
    *   Includes optional company logo at the top.
    *   Automatically adds page numbers ("Page X/Y") to the footer.
*   **Direct Email Sending:** 
    *   Send the generated PDF proposal directly to the client's email address.
    *   Automatically send the generated PDF invoice when a proposal is accepted.
*   **Configurable Sender & Content:** Customize the "From" name, email address, proposal email body, and invoice email body (using placeholders like `{client_name}`, `{proposal_title}`, `{invoice_number}`, `{your_name}`, `{your_company_name}`, `{site_name}`) via a dedicated Settings page.
*   **Admin List Columns:** View essential details like Client Name, Status directly in the Proposals list table.
*   **Invoice Download:** Download the generated invoice PDF directly from the proposal edit screen once accepted.
*   **Invoice Due Dates:** Set a default number of "Payment Due Days" in settings to automatically calculate and display the Due Date on invoices.
*   **Public Proposal View:** Clients can view and respond (Accept/Reject with comments) to proposals via a unique, secure link.

## Installation

1.  **Download:** Download the plugin zip file.
2.  **Upload:** Upload the `pretty-proposals` folder to your WordPress site's `/wp-content/plugins/` directory.
3.  **Activate:** Activate the "Pretty Proposals" plugin through the 'Plugins' menu in your WordPress admin area.
4.  **Usage:**
    *   Go to "Proposals" -> "Add New" to create proposals. Fill in client details (including address/VAT if needed) and line items.
    *   Save and publish the proposal. Use the "Send Proposal to Client" button.
    *   Once accepted, an invoice is generated and emailed automatically.
    *   You can download the invoice PDF from the proposal edit screen using the "Download Invoice PDF" button.
5.  **Configure:**
    *   Go to "Proposals" -> "Settings" to customize Company Info, Sender details, Email Templates, Logo, Currency, Payment Terms, Banking Details, and Payment Due Days.

## Frequently Asked Questions (FAQ)

*   **How can I further customize the PDF layout?**
    Currently, the PDF layouts are defined within the `ppr_generate_proposal_pdf` and `ppr_generate_invoice_pdf` functions. Adding a logo and basic company info is supported via Settings. More advanced customization requires editing these PHP functions.

*   **How can I change the email text?**
    The default email subjects are defined in the PHP functions. The sender details (From Name/Email) and the main email body content for both proposals and invoices can be configured on the Settings page ("Proposals" -> "Settings"). Use placeholders like `{client_name}`, `{proposal_title}`, `{invoice_number}`, `{your_name}`, `{your_company_name}`, `{site_name}`, and `{proposal_link_html}` (for proposal email).

## Changelog

### 1.0.9
*   **Feature:** Added Client Address and Client VAT Number fields to Client Details meta box.
*   **Feature:** Added "Download Invoice PDF" button to the proposal edit screen (visible for accepted proposals).
*   **Feature:** Added "Payment Due Days" setting for invoices.
*   **Feature:** Display calculated Due Date on generated invoice PDFs based on the setting.
*   **Feature:** Include Client Address and VAT Number on invoice PDFs.
*   **Fix:** Resolved issues with email placeholders (`{your_name}`, `{your_company_name}`) not being replaced correctly in proposal emails.
*   **Fix:** Corrected PHP Fatal Error caused by duplicate function declaration (`ppr_generate_unique_invoice_number`).
*   **Fix:** Addressed PHP Fatal Error related to missing `PPR_PDF` class file (class is defined in main plugin file).
*   **Fix:** Resolved PHP Fatal Error caused by undefined method `PPR_PDF::NbLines()` in invoice generation.
*   **Fix:** Replaced deprecated `utf8_decode()` function calls with `mb_convert_encoding()` for better PHP 8+ compatibility.
*   **Fix:** Resolved various visual/layout inconsistencies in the generated invoice PDF table.
*   **Fix:** Corrected potential error in PDF generation download logic (`exit;` after `Output('D', ...)`).
*   **Fix:** Addressed potential undefined variable warnings during invoice PDF generation.

### 1.0.1
*   **Rename:** Plugin renamed to "Pretty Proposals" (folder, file, functions, IDs, slugs, options, meta keys, text domain) to avoid potential conflicts.
*   **Fix:** Resolved fatal PHP Parse Error on activation related to `SetFont` syntax in PDF footer.
*   **Feature:** Added page number support ("Page X/Y") to PDF footer.
*   **Feature:** Added customizable email body template setting with placeholders (`{client_name}`, `{proposal_title}`, `{site_name}`).
*   **Feature:** Added company logo upload setting and inclusion in generated PDFs.
*   **Update:** Updated Readme files to reflect changes.
*   **Note:** This version changes internal identifiers, including custom field meta keys. Proposals created with v1.0.0 will *not* retain their data after upgrading.

### 1.0.0
*   Initial release (as WP Proposals).
*   Features: CPT, Meta Fields, PDF Generation (FPDF), Email Sending, Admin Columns, Settings Page (From Name/Email). 
