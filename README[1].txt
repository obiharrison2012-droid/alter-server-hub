ALTAR SERVER HUB — GLOBAL QUIZ RESULTS UPDATE
Made by Okoro Harrison

WHAT THIS UPDATE DOES
- Keeps the “Benedicamus Domino” practice box at the top. Players type “Deo gratias” themselves and check the reply.
- Keeps the altar-server glossary, name card, and shuffled 10-question quiz.
- Uses player-chosen nicknames for quiz submissions.
- After a player finishes and the computer marks their quiz, they can click “Submit result globally”.
- The database stores nickname, score, total questions, percentage and submission time. It does not store the player's email or their individual answers.
- Results from all visitors are stored in one shared Supabase database, once configured.

IMPORTANT: THE DATABASE MUST BE CONFIGURED
The ZIP cannot connect to a database until you create a Supabase project and add its URL and browser-safe publishable/anon key to index.html. These steps are free to start, but provider plans/limits can change. Do not put a service_role/secret key in index.html.

SETUP PART 1 — CREATE THE DATABASE
1. On your Windows computer, open https://supabase.com/ and sign up or log in.
2. Create a new project. Save the database password somewhere safe; do not put it in the website.
3. In your Supabase project, open SQL Editor and create a new query.
4. Open the file supabase_setup.sql included in this ZIP, copy all its contents into the SQL Editor, and run it.
5. This creates the quiz_results table and enables Row Level Security. Anonymous visitors can INSERT valid results but cannot read the table. This protects other players' results from being publicly listed.

SETUP PART 2 — CONNECT THE WEBSITE
1. In Supabase, open Project Settings (gear icon) > API, or the project's API Keys section (the labels can vary).
2. Copy the Project URL. Copy the publishable key or legacy anon/public key. NEVER copy a service_role key or secret key.
3. Extract this ZIP. Open index.html in Notepad.
4. Press Ctrl+F and search for: YOUR_PROJECT_ID
5. Replace only the example URL https://YOUR_PROJECT_ID.supabase.co with your real Supabase Project URL.
6. Search for: YOUR_SUPABASE_PUBLISHABLE_OR_ANON_KEY
7. Replace the placeholder between the quotes with your Supabase publishable/anon key. Keep the quotes.
8. Save index.html.
9. Upload the updated index.html to your existing GitHub repository: Add file > Upload files > select index.html > Commit changes. Keep GitHub Pages set to branch main and folder /(root).
10. Open the live website, enter a nickname, complete a quiz, click “Submit to computer — mark my quiz”, then click “Submit result globally”. Check the status message for success.

SQL POLICY / PRIVACY
The supplied SQL enables Row Level Security and allows anonymous INSERT only. Public visitors cannot SELECT/read the database through the browser. The table validates nickname length and score range. Because the site is public, someone could still send spam submissions; this simple setup is suitable for a starter project, not high-stakes exams. A stronger production system would add server-side validation and abuse controls.

VIEWING RESULTS AS THE OWNER
To view collected results, log into Supabase, open Table Editor, and choose quiz_results. Only project owners/admins should access the Supabase dashboard. Do not expose database secret/service_role keys in the website or share them publicly.

TROUBLESHOOTING
- “Not connected yet”: the URL/key placeholders have not been replaced in index.html.
- HTTP 401/403: check the project URL/key and that the SQL setup ran successfully.
- HTTP 404: check that the table is named quiz_results and that the REST API is enabled for it.
- Network/CORS error: make sure the project URL is correct and you have internet access.
- After editing, commit the changed index.html to GitHub and refresh the published page. It may take a short time for GitHub Pages to update.

OTHER NOTES
- The global submit feature does not activate until you configure the database values.
- The earlier email-to-creator form is still present as a separate option, but it also needs its own receiving email setup if you want to use it.
- Avoid using full names or entering private/sensitive information. Players should use nicknames.
- The site is a learning aid; follow your parish's instructions and approved liturgical books.
