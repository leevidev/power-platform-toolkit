# Open Connections (Power Automate bookmarklet)

A one-click bookmarklet that jumps to the **Connections** page of the Power Automate environment you are working in.

## Behavior

- If you are on `make.powerautomate.com` and the URL contains an environment ID, it opens the Connections page of **that same environment** in the current tab.
- Otherwise it opens the Connections page of the **default environment ID** you set in the code.
- If no environment ID is found and the placeholder has not been replaced, it shows an alert instead of navigating.

## Setup

1. Find your environment ID: open `make.powerautomate.com`, pick your environment, and copy the GUID from the URL (`/environments/<ENV-ID>/...`).
2. Replace `ADD_YOUR_ENV_ID_HERE` (it appears twice) in the code below with your ID.
3. Create a new browser bookmark and paste the whole line into its URL field.

## Bookmarklet

```javascript
javascript:(function(){var P='ADD_YOUR_ENV_ID_HERE';var m=location.hostname==='make.powerautomate.com'&&location.pathname.match(/\/environments\/([^\/]+)/);var id=m?m[1]:P;if(id==='ADD_YOUR_ENV_ID_HERE'){alert('Set your environment ID in the bookmarklet first.');return;}location.href='https://make.powerautomate.com/environments/'+id+'/connections';})();
```

## Notes

Do not commit your real environment ID to a public repository. Keep it only in your own browser bookmark.
