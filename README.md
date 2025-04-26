# Accessibility
- Your foreground-silent color misses all contrast [accessibility checks](https://webaim.org/resources/contrastchecker/?fcolor=525252&bcolor=030608)
- Your main foreground color is fine, but you might consider making it a bit less striking to reduce dark mode burn-in and eye strain for dense text blocks like your name and the section headers
- Your about me section looks ncie with the full justification on either side but you can make the text a bit cleaner by using the `hyphens-auto` tailwind utility
- At tablet and small laptop screen sizes (lg breakpoint - 1024 up to 1280), each of the sections shrinks to the available width except for the education and experience section which is allowed to have visible x overflow. This creates some obvious horizontal scroll, but also introduces some less obvious scroll in your <aside> after scrolling to the very bottom of the page because it is set to h-screen but doesn't account for the horz scrollbar. This breaks a whole lot of things like scroll jumping when tabbing thru the footer while not scrolled all the way down ([video demo](https://www.loom.com/share/c045252ec1f94783933b8e9e3be7d0be)). Looks-wise, it breaks the clean look of the about me & experience divider lines.
- <aside> elements are usually used to indicate standalone information that is just loosely related to the main content, but you have your <nav> element directly tied to the main content nested in the aside which seems odd

# Design Thoughts
Your portfolio is clearly trying to mimic a resume, which is great. However, I think that you have a unique opportunity to go against the grain a bit with ordering here. This is the core timeline of the webpage currently: 
- About Me: Chronological
- Education & Experience: Reverse Chronological (resume standard)
- Other items: Mixed

At their core, the information you provide in the about me, project, and achievements sections are also timeline-able events. I think that you can make this feel like a very purposeful and personable scrolling experience by mixing the events together at their relevant times told in pure chronological order - opening with a short blurb about what got you into games and leading straight into your secondary education as the first timeline event. Then you'd move on to a bit more connecting exposé that gives context for your Technical Artist timeline event at Molekül. Then perhaps some exposé leading into a project or achievement timeline event. So on and so forth. As a really nice design flare (and to lean into the scroll progress trend that is common nowadays) you could make your green "I am here" dot a fixed "We are here" dot that stays with the user's scroll context. It could be very beautiful - a colleague of mine from Cognizant just implemented what I think is the most beautiful version of this I've ever seen in the desktop view, but you can check out his mobile view for a marker that would be more achievable here: https://www.braydoncoyer.dev/about

There are also some things you could do to bolster the depth of your projects info. For example, including dates worked on would add some nice insight, and if you're feeling frisky you could throw in your repo participation sparklines

[Your csp-solvers sparkline](https://github.com/yiliansource/csp-solvers/graphs/participation?h=28&type=sparkline&w=155)

![image](https://github.com/user-attachments/assets/6971ad3b-bec9-4c7c-a727-cef484a61e37)


---------------------------------------------------------------------------------
On a personal note, I was playing around with your site for about an hour while making this review and I came up with a slightly modified layout that removes the navigation items in favor of leaning into the negative space with a solo section headline as the app header. This comes with an obvious accessibility tradeoff where users can't click to jump to a section. You have a relatively short scroll context so this isn't a huge concern, but we can bake that accessibility back in by having the <nav> element be absolutely positioned and hidden unless one of its children is focused so users can still use keyboard control and forward hashlinks to your sections. Might not be to your liking but I thought it looked pretty neet other than the odd grouping of achievements and artwork; I would have made a nice divider and used trophy icons instead of traditional bullets since it didn't have a related headline anymore. Shown in images instead of video because I don't have state management to update the headline text haha.
![Screenshot 2025-04-26 001527](https://github.com/user-attachments/assets/1accb584-0fce-4cb2-aa41-55b304181b4e)
![Screenshot 2025-04-26 000429](https://github.com/user-attachments/assets/082e5229-575b-4cff-afe8-c8fee9f7ef3c)
![Screenshot 2025-04-26 001407](https://github.com/user-attachments/assets/1ed6df90-36d1-477d-a032-6b8acb93f5aa)
![Screenshot 2025-04-26 001236](https://github.com/user-attachments/assets/7d093b0b-89c9-4139-81a4-dd86c4b435dc)
