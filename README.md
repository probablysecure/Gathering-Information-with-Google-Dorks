# Gathering Information with Google Dorks

For this lab, I used Google Dorks, advanced Google search operators, to perform targeted information gathering against a specific domain. The goal was to practice using search operators to efficiently locate specific types of publicly available content, a technique commonly used during the reconnaissance phase of a security assessment to identify what information an organization may have exposed without realizing it.

## Step 1: Using Google Dorks to search for targeted information

I started by searching for all publicly indexed PDF files hosted on a specific domain:

```
site:sans.org ext:pdf
```

<img width="1161" height="892" alt="image" src="https://github.com/user-attachments/assets/0b2273e1-b0bf-4d7b-a035-89be920421c0" />


The `site:` operator restricts results to a single domain, and `ext:` (or `filetype:`) filters results down to a specific file type. Combined, this query surfaces every PDF Google has indexed on that domain, which is useful for quickly seeing what kinds of documents an organization has made publicly accessible.

I then narrowed the search to look specifically for content related to incident response:

```
site:sans.org filetype:pdf "incident response"
```

<img width="1293" height="896" alt="image" src="https://github.com/user-attachments/assets/7561e07b-6e1d-49b3-b603-5298333f94fa" />


Adding a quoted keyword alongside `site:` and `filetype:` narrows results to documents containing that exact phrase, rather than just any PDF on the domain. This let me pull results relevant to a specific topic instead of manually filtering through everything indexed.

I repeated the same approach to look for cybersecurity reports and whitepapers:

```
site:sans.org filetype:pdf "cybersecurity report"
```

<img width="1227" height="893" alt="image" src="https://github.com/user-attachments/assets/4445c861-fcc1-4ece-92f1-b7e7c4307aaa" />

And again to locate published research papers:

```
site:sans.org filetype:pdf "research paper"
```

<img width="1169" height="882" alt="image" src="https://github.com/user-attachments/assets/399cb946-ad1d-4820-af86-c52bb3464a75" />


## Understanding the search operators used

A few operators made this kind of targeted search possible:

- **`site:`** limits results to a single specified domain
- **`filetype:`** and **`ext:`** both filter results down to a specific file extension, such as PDF
- **`intitle:`** restricts results to pages with a given term in the page's HTML title
- **`inurl:`** searches for a specified term within the page's URL
- **`intext:`** searches within the actual content of a page, similar to a standard search
- **`cache:`** displays Google's cached version of a specific page

Combining these operators, rather than using them one at a time, is what makes Google Dorking effective. A query like `site:sans.org filetype:pdf "incident response"` layers three separate filters together to return a much more precise set of results than any single operator could on its own.

## Conclusion

This lab demonstrated how Google Dorks can be used to perform efficient, targeted reconnaissance using nothing more than a standard search engine. By layering operators like `site:`, `filetype:`, and specific keywords, it's possible to quickly locate publicly available documents on a given domain without needing to browse the site manually or guess at file names. This same technique has a security implication beyond simple research: organizations can unintentionally expose sensitive documents, internal reports, or misconfigured pages that become discoverable through these same search operators, which is why understanding Google Dorking is a relevant skill on both the offensive and defensive sides of security work.
