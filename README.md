Weekly Printer

A lightweight Windows utility that periodically prints a test page to help prevent inkjet printers from drying out and keep them ready for the next print job.
Designed for both monochrome and color printers, particularly inkjet models that may remain unused for extended periods.
Purpose

Weekly Printer reduces the need to remember to print a maintenance page manually. It can support extended periods with minimal supervision—including several months—provided the PC is regularly signed into and the printer remains connected, powered on, and supplied with paper and ink.
Periodic printing helps reduce the risk of dried ink, but results depend on the printer, ink, and environment. It does not replace manufacturer-recommended maintenance.
Features
- Configurable printing interval: 1–30 days, default 7 days.
- Automatic checks one minute after Windows sign-in.
- Manual test printing.
- Temporary pause with automatic expiry.
- Status showing elapsed time, the next due date, and time remaining.
- Printer, queue, and startup diagnostics.
- Protection against simultaneous checks and duplicate retries.
- Complete removal option.
No continuously running background process is required.
Color Printer Support

The test page contains black text, lines, and cyan, magenta, yellow, black, red, green, and blue blocks.
Color printing is requested automatically when supported by the printer and its driver. On monochrome printers, the page prints in grayscale.
Requirements
- Windows 10 or 11.
- Windows PowerShell 5.1 and Task Scheduler.
- An installed Windows printer driver.
No additional libraries or internet connection are required.
Installation
1. Download and extract the entire archive.
2. Connect your printer and load paper.
3. Run INSTALL.cmd and select your printer.
4. Open START.cmd to access the menu.
To update, run the new INSTALL.cmd and select the same printer. Existing settings and submission history are preserved.

| Action | Behavior |
- Status - Shows timing, pause status, startup information, and recent logs.
- Check now - Prints only when the interval has elapsed and printing is not paused.
- Print one test page now - Ignores the interval and pause to submit one test page.
- Settings - Changes the interval, pauses or resumes printing, selects a printer, or removes the program.
- Diagnostics - Checks printing components without submitting a page.

Both printing actions require an available printer and an empty queue. A successful submission restarts the interval. A manual test does not cancel an active pause.
Automatic Checks

Checks run only after Windows sign-in. Unlocking the screen, waking the PC, or connecting the printer does not trigger another check.
Regular sign-ins are required: leaving the PC continuously signed in does not produce periodic checks. If the printer becomes available later, use Check now.
Data and Logs

Installed files and settings are stored in:

%LOCALAPPDATA%\WeeklyUsbPrinter

- config.json — printer, interval, and pause settings.
- state.json — submission history and recovery information.
- activity.log — current activity log.
- activity.log.old — previous rotated log.

Uninstall
- Run UNINSTALL.cmd to remove automatic startup while preserving data.
- Run REMOVE_ALL.cmd to remove the installed program, scheduled task, settings, history, and logs.
Complete removal is also available through Settings → Remove completely.
Downloaded archives and extracted installer files remain untouched.

Important Notes
The utility records submission to Windows, not confirmed physical printing. Documents printed by other applications are not tracked.
If an interrupted attempt has an UNKNOWN outcome, automatic retries stop to avoid duplicate pages. Check the print queue, then use TEST.cmd to deliberately retry.
The test page is not a manufacturer-specific nozzle check or printhead cleaning procedure.
