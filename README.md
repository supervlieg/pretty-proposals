# Pretty Proposals

**Contributors:** Willem Prinsloo
**Tags:** proposals, client management, pdf, email, admin, crm
**Requires at least:** 5.0
**Tested up to:** 6.5
**Stable tag:** 1.0.3
**Requires PHP:** 7.0
**License:** GPLv2 or later
**License URI:** https://www.gnu.org/licenses/gpl-2.0.html

Manage client proposals directly within WordPress using Pretty Proposals. Create, customize, PDF, and send proposals with ease.

## Description

Pretty Proposals allows designers, developers, and freelancers to streamline their proposal workflow directly within their WordPress dashboard.

**Core Features:**

*   **Proposal Management:** Create and manage proposals using a dedicated Custom Post Type (`pretty_proposal`).
*   **Custom Fields:** Includes fields for Client Name, Company, Email, Scope of Work (main editor), and Project Price.
*   **Status Tracking:** Track proposal status (Draft, Sent, Accepted, Rejected) via a simple dropdown.
*   **PDF Generation:** Automatically generates a basic PDF document of the proposal details using the FPDF library, including an optional company logo at the top.
*   **PDF Page Numbers:** Automatically adds page numbers ("Page X/Y") to the footer of multi-page PDFs.
*   **Direct Email Sending:** Send the generated PDF proposal directly to the client's email address from the proposal edit screen using WordPress mail functions.
*   **Configurable Sender & Content:** Customize the "From" name, email address, and the email body text (using placeholders like `{client_name}`, `{proposal_title}`, `{site_name}`) via a dedicated Settings page.
*   **Admin List Columns:** View essential details like Client Name, Project Price, and Status directly in the main Proposals list table in the admin area.
*   **Basic Styling:** Includes minimal admin CSS for improved usability.

## Installation

1.  **Download:** Download the plugin zip file or clone the repository.
2.  **Upload:** Upload the `pretty-proposals` folder (ensure the folder name is correct) to your WordPress site's `/wp-content/plugins/` directory.
3.  **FPDF Dependency:**
    *   This plugin requires the **FPDF** PHP library for PDF generation.
    *   Download the latest version (zip file) from the official website: [fpdf.org](http://www.fpdf.org/)
    *   Create a directory named `lib` inside the `pretty-proposals` plugin folder (i.e., `wp-content/plugins/pretty-proposals/lib/`).
    *   Extract the downloaded FPDF zip file.
    *   Copy the `fpdf.php` file and the `font` directory into the newly created `pretty-proposals/lib/` directory.
4.  **Activate:** Activate the "Pretty Proposals" plugin through the 'Plugins' menu in your WordPress admin area.
5.  **Usage:**
    *   A new "Proposals" menu item will appear in your admin sidebar.
    *   Go to "Proposals" -> "Add New" to create your first proposal.
    *   Fill in the details, including the client information and scope of work.
    *   Save the proposal.
    *   Use the "Send Proposal to Client" button in the sidebar meta box to generate the PDF and email it.
6.  **Configure (Optional):**
    *   Go to "Proposals" -> "Settings" to customize the "From" Name, Email address, Email Body template, and upload a Company Logo for PDFs.

## Frequently Asked Questions (FAQ)

*   **Is the FPDF library included?**
    No, due to licensing considerations and to ensure you use the latest version, you need to download FPDF separately from [fpdf.org](http://www.fpdf.org/) and place `fpdf.php` and the `font` directory inside the `pretty-proposals/lib/` folder.

*   **How can I further customize the PDF layout?**
    Currently, the PDF layout is primarily defined within the `ppr_generate_proposal_pdf` function in the main `pretty-proposals.php` file. Adding a logo is supported via Settings. More advanced customization (fonts, complex layouts) requires editing this PHP function. Future versions might explore template files.

*   **How can I change the email text?**
    The email subject is defined in the `ppr_send_proposal_email` function. The sender details (From Name/Email) and the main email body content (using placeholders) can be configured on the Settings page ("Proposals" -> "Settings").

## Changelog

### 1.0.3 (Current)

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
