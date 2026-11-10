# Project notes

- The venue is always spelled **WUGE** — all caps (West Union Grain Elevator). Full name: The Place at the WUGE.

## Where the WUGE files live (OneDrive, read with the Microsoft 365 connector)

Source of truth is OneDrive, not this repo. Look here first before building anything new.

| Folder (OneDrive path) | What's in it |
|---|---|
| `DBG - Clients/The WUGE, LLC/Strategic Plan/` | **Strategy hub.** Read its `CLAUDE.md` first: current model version, loan size, decisions, contacts, working rules. Subfolders: `00_Source`, `01_Due_Diligence`, `02_Financial_Model`, `03_Targets`, `04_Lender_Package`, `05_Action_Plan`, `06_Meetings` |
| `DBG - Clients/The WUGE, LLC/Strategic Plan/04_Lender_Package/` | Lender checklist, bids (`Bids/`), estimates checklist shared with Pam (SBDC), city support letter draft |
| `DBG - Clients/The WUGE, LLC/` | Property company (borrower): bookkeeping, recordings, contracts |
| `DBG - Clients/The Place at The WUGE, LLC/` | Operating company: QuickBooks setup, branding, `The_Place_3-Year_Projection.xlsx` |

Connector lookups: `sharepoint_folder_search` with name `Strategic Plan` or `The WUGE, LLC`, then `read_resource` on the returned URI.

Live Claude Docs:
- Business plan (narrative, no dollars): https://claude.ai/artifact/9YwUGZGCzyfk6rdPRe4Yc6
- SBA 504 financing request (the money piece): https://claude.ai/artifact/V95cmffuJXzyxRc8xjtEr9

**Confidentiality:** the OneDrive folders hold the owners' personal and business finances. Don't copy financial figures into this repo.

## Where to save WUGE work

Save every WUGE deliverable straight into the OneDrive `Strategic Plan` folder above, using its naming rule `YYYY-MM-DD_<document>`. Bill will not move files by hand. A cloud session can't write to OneDrive through the Microsoft 365 connector, which is read-only. Do WUGE file work where the OneDrive folder is reachable: Cowork or the Claude desktop app on Bill's computer, or a cloud session with that folder attached through Remote Control.
