# Custom Interactive Filters for ServiceNow Dashboards  

This project provides a **reusable, configurable implementation of custom interactive filters** for ServiceNow dashboards — built to overcome the limitations of out-of-the-box filters.  

More details [here](https://www.linkedin.com/pulse/custom-interactive-filters-slightly-less-awful-new-world-dominik-kiss-pi1xf).

## Why?  
ServiceNow’s native Interactive Filters don’t always cut it. Common requirements that aren’t supported include:  
- Filtering by tags (`sys_tags`)  
- Applying custom filter logic (e.g., `AND` vs `OR` for multi-selects)  
- Excluding instead of including values  
- Applying filters across multiple tables  
- Handling string fields and other edge cases  

Historically, such solutions required **Dynamic Content Blocks with JellyScript** — messy, poorly documented, and difficult to maintain. This project replaces that pain with a **cleaner, reusable approach**.  

## What it Does  
- Provides a **configurable filter widget** (via a custom table + widget + UI Macro)  
- Supports **multi-select filtering** with:  
  - Include / Exclude toggle  
  - AND / OR relationship toggle  
- Works across multiple tables at once  
- Can be easily reused by adding new configuration records (no code changes needed)  
- Plays nicely with ServiceNow dashboards via the `DashboardMessageHandler` API  

## How it Works  
1. **Configuration Table** – Define which tables and filter conditions apply to each filter.  
2. **Widget** – Reads configuration and passes values to the UI Macro.  
3. **UI Macro** – Renders the filter UI (tags dropdown, toggles, reset button).  
4. **Client Script Logic** – Publishes interactive filter messages back to the dashboard, applying conditions dynamically.  

## Demo Features  
- Multi-select tag dropdown (powered by Select2)  
- Excluding toggle (`= / EXCLUDING`)  
- AND/OR toggle for combining multiple conditions  
- Reset button to clear filters  
- Supports multiple instances on the same dashboard without conflict  

## When to Use  
- When standard ServiceNow Interactive Filters don’t meet requirements  
- When you need **tag-based filtering** or other advanced conditions  
- When you want a **reusable solution** instead of one-off Jelly hacks  
