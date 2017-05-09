# Accessible flag of the United States

This is a quick demo of how to take a list of US states and turn it into a graphical flag with AJAX loading of additional information. Presented as featured in a technical test.

# Features

The code features two unordered lists of 50 states and 13 colonies, each with a heading level 2, and a heading level 1 all inside a section. Each state / colony is inside an anchor link and the text is clipped such that it will still be read by a screen reader. They are links as this also allows a keyboard user to tab to them.

The lists are styled into stars and stripes by means of pseudo elements, nth formulas, and calc.

Upon tabbing or hovering a star or stripe the clipping is removed and the anchor wording appears. Once clicked the JavaScript on the page finds the relevant target (the event is attached to the section so there aren't 63 click handlers in memory) and loads in a full, locally saved, wiki page based on the anchor content.

This page is loaded into a new HTMLDocument to prevent any unneccessary resources being loaded and the main table data is extracted and injected into a second section on the main page which is then focused for screen readers, keyboard users, and visual users.

By not preventing the default action of the link we preserve page history. An anchored URL will also automatically load the state data table on page refresh.

# Improvements

As this is only a quick pure HTML, CSS, and JavaScript demo of Accessibility we haven't taken progressive enhancement into account. Made correctly, the anchors would link to real URLs which the server would redirect internally to the main page. The server would load any linked state data from this URL into the initial page load rather than making the AJAX do it. This would result in fewer requests to the server and would allow the page to continue to function if JavaScript was unavailable.

The AJAX loads in a full page from the server and uses JavaScript to extract the portion it wants. This is to demonstrate data manipulation with JavaScript but is inefficient; the required snippet should be extracted and sent by the server to decrease traffic to the client.

There are no loading or error handling features in this demo code. A real product should have both where nexessary.

# Live demo

View a live demo of the [Accessible flag of the United States on WizPip.com](https://wizpip.com/demo/us-flag/)