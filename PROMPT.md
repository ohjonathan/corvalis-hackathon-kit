Imagine your client: their SAP program is facing challenges, and you need to create a view and an artifact to communicate with your executive clients. What would you build?

Our client is Corvalis Medical Devices (fictional). Its SAP S/4HANA program, Project Keystone, is in trouble, and the steering committee meets on 28 Oct 2026.

Audience: the steering committee, chaired by the CFO
Artifact: a one-page steering-committee view built around one clear decision ask
File name: steerco_onepager.html

1. Read AGENTS.md, then single_source_of_now.html: the dashboard the program office uses today. All the program data is at the top of that file (window.PROGRAM); read it in full.
2. In the chat, give me five lines first: the so-what in one sentence, the decision you would ask for, and the three facts that support it, each with its record ID.
3. Then build the artifact as one self-contained HTML file in this folder, under the file name above:
   - take every number from the program data and write in the ones you use (don't copy the whole data block);
   - lead with the so-what and the decision ask, then the evidence;
   - put the record ID next to every fact, like [M2], [D-02], [R-07], [budget], [V-03], [team OTC];
   - label anything you calculate or judge as "inference" and show the arithmetic;
   - write for a busy executive: plain words, short sentences, no unexplained acronyms;
   - no external libraries, fonts or network calls. It must open by double-click.
4. When it is done, tell me the two questions this audience is most likely to push back with.
