# Privacy Policy for BrowseMemory

**Effective Date:** 03/06/2026

BrowseMemory ("we", "our", or "us") is a Chrome Extension designed to provide a semantic search engine for your personal browsing history. 

We believe that your browsing history is deeply personal. Therefore, BrowseMemory is built entirely upon an **Offline-First, Privacy-By-Design** architecture. This Privacy Policy explains what information the extension interacts with, how it processes that information, and how we protect your privacy.

## 1. Core Privacy Principle: Zero Data Collection
**We do not collect, transmit, or store your personal data on any external servers.** 
BrowseMemory operates entirely within the boundaries of your local machine and your browser. We do not have user accounts, we do not use analytics or telemetry trackers, and we have no databases in the cloud. Because we do not possess your data, it is impossible for us to sell, share, or misuse it.

## 2. Information the Extension Processes
To function as a search engine for your reading history, the extension must process the contents of the websites you visit.

When you navigate to a webpage, BrowseMemory locally extracts:
*   **Web History:** The URL and the timestamp of your visit.
*   **Website Content:** The visible text, article excerpts, titles, descriptions, and the site's favicon.

**This extraction happens strictly locally.** The text is processed directly on your computer and is never sent over the internet to us or any third party.

## 3. How Your Data is Stored
All the information extracted from your browsing sessions, as well as the mathematical vectors (embeddings) generated for semantic search, are stored securely within your browser's native **IndexedDB** and `chrome.storage.local` mechanisms. 

*   This data resides exclusively on your device's physical hard drive.
*   It is isolated to your specific browser profile.
*   It is **not** synced with your Google Account via Chrome Sync.

## 4. The Artificial Intelligence (AI) Model & Network Requests
BrowseMemory uses an advanced, open-source Machine Learning model (`Transformers.js` / BGE-Small) to understand the context of the pages you read.

*   **One-Time Model Download:** Upon your first use of the extension (or your first search), the extension will make a network request to an open-source model repository (such as Hugging Face) to download the mathematical AI weights required to run the model.
*   **No Data Transmission:** During this download, **no personal data, search queries, or browsing history is transmitted.** The request simply downloads static model files.
*   **Offline Inference:** Once the model is cached on your machine, all subsequent AI processing and text embedding occurs 100% offline using your computer's local resources.

## 5. Chrome Permissions Justification
To provide its functionality, BrowseMemory requires specific browser permissions. Here is exactly why we need them and how they respect your privacy:

*   **`<all_urls>` (Host Permission):** Required to read the text of the websites you visit so they can be saved into your local search index.
*   **`activeTab` & `scripting`:** Required to inject the local text-extraction script into the page you are currently viewing.
*   **`webNavigation`:** Required to detect when you navigate within modern Single Page Applications (like React apps or YouTube) so the extension can index the new content without a hard page reload.
*   **`offscreen`:** Required to run the heavy AI Machine Learning model in a background thread so it doesn't slow down or freeze the websites you are actively browsing.
*   **`alarms`:** Required to run local background tasks, such as periodically cleaning up old data from your database.
*   **`storage`:** Required to save your extension settings, such as your custom blocklist.

## 6. Data Retention and Your Control
You maintain absolute control over the data BrowseMemory processes.

*   **Automatic Expiration (30-Day Pruning):** To prevent the extension from consuming too much space on your hard drive, a background process automatically deletes indexed pages and memories that are older than 30 days.
*   **Manual & Browser Data Deletion:** You can permanently delete your entire semantic database instantly at any time by clicking the "Clear Database" (Trash) icon in the extension's user interface. Additionally, because the data is saved in your browser's native IndexedDB, **clearing your browser's site data/cache will also completely delete all stored semantic search data**.
*   **Blocking Website Storage (Custom Blocklists):** You have full control over what gets stored. If there are websites you never want BrowseMemory to read or store (e.g., banking sites, private documents, social media), you can explicitly block them by adding their URLs or domain names to the "Blocked Sites" list in the extension's settings. The extension will completely ignore pages matching these rules and will never extract or store their content.

## 7. Third-Party Links
The extension contains links to the original web pages you visited. Clicking these links will open the respective third-party websites, which have their own privacy policies. We are not responsible for the privacy practices of the websites you visit.

## 8. Changes to this Privacy Policy
We may update this Privacy Policy from time to time to reflect changes in our practices or changes in Chrome Web Store guidelines. If we make material changes, particularly concerning how local data is processed or permissions are utilized, we will update the "Effective Date" at the top of this document.

## 9. Contact Us
Since BrowseMemory is an open-source project, the best way to ask questions, report issues, or provide feedback regarding this Privacy Policy is to open an issue on our GitHub repository.

*   **Developer Email:** maheshshindedev@gmail.com
