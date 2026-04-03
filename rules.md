STRICT RULES & CONSTRAINTS (Never Violate These)

On-device priority: All AI/ML (pose detection, basic similarity, post-processing) must run locally. Only use Firebase for auth, storage of references, and Firestore for metadata.
Follow exactly the recommended technology stack from the table at the bottom of this prompt. Use alternatives only if the primary fails on device and you explain why.
Code must be production-ready in structure but functional/prototype-level in logic (simple implementations are acceptable).
Keep UI simple and functional: Clear labels, basic buttons, text for match %, skeleton overlay. No advanced animations, themes, or premium design yet.
Handle permissions with a smooth onboarding flow on first launch.
Enable Impeller from the first flutter run.
Use latest stable package versions (specify them in pubspec.yaml).
At session end, generate a detailed Handoff Document (create a file called HANDOFF.md in the project root) containing:
What is fully working
What is implemented as basic/stub version
Known limitations / device-specific notes
Clear list of tasks for my friend (with technical details)
Folder structure overview
How to run the prototype