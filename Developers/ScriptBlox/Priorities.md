# Priorities
The Fluxus Android ScriptBlox Search Integration adds some additional priorities ontop of the ones in ScriptBlox's built in search.
This prioritization is done using points; the more points, the higher up the script, the more users will find it.

The priority system uses the following factors to prioritize a script:

1. Developer marks as supporting a Mobile UI
   We check if the script has any of the following in either the title, or the source code (we do NOT check loadstringed assets for this; if you use a loadstring, put it above/below the loadstring line), and mark it as "compatible" if it has them (case-insensitive):
   - `mobile`
   - `android`
   - `fluxus android`
   - `flux android`
   - `fluxusandroid`
   - `-- @supports-fluxus-android`
   - `-- @supports-mobile-ui`
    Only put these in your scripts **if you have tested them with a mobile UI on a phone**. Your UI may not be user-friendly on a small device.
    
    This prioritizes the script by 5 points
2. Game ID Matches
   We check if the Game ID matches the current Game ID. Simple.
    This prioritizes the script by 2 points
3. Universal Script
   We check if the script is marked as a universal script or not.
    This prioritizes the script by 1 point
4. Verified Script
   We check if the script is marked as "verified" (by the scriptblox team, not us!)
    This prioritizes the script by 1 point
5. Patched Script
   We check if the script is marked as "Pached" (by the scriptblox team, not us!)
    This **de**-prioritizes the script by 50 points; guaranteeing it will be at the very bottom of the search rankings.