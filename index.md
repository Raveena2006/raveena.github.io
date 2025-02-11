---
layout: default
---

_I was never meant to follow the rules — I was meant to understand them._

<!-- Contact Button -->
<button onclick="openPopup()" class="px-4 py-2 bg-green-600 hover:bg-green-500 text-white rounded-lg shadow-lg text-lg font-semibold transition duration-300 flex items-center gap-2">
    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
        <path stroke-linecap="round" stroke-linejoin="round" d="M21 10V3a2 2 0 00-2-2H5a2 2 0 00-2 2v7m18 0h-6m6 0l-9 9-9-9m18 0v4m-18 0v-4" />
    </svg>
    Contact Me
</button>

[Link to another page](./another-page.html).

## About Me

> I am a cybersecurity enthusiast and a second-year electrical engineering student with a strong interest in `defensive security, threat detection, and incident  response`. I enjoy analyzing security risks, mitigating threats, and enhancing system defenses to protect digital environments.
> 
> I am open to internships, apprenticeship roles, and weekend jobs in cybersecurity defense to gain hands-on experience and contribute to security operations.
> 
> _Let’s connect and work towards a more secure digital future._

## Skills and Technologies

## Projects

## Certificates and Courses

## Write-ups Section

### 🚀 Languages Known:
<p align="left">
  <img src="https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white" />
  <img src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white" />
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" />
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" />
</p>

<!-- Popup Container -->
<div id="popup" class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-50 hidden">
    <div id="popup-box" class="popup-enter bg-gray-800 p-6 rounded-2xl shadow-2xl w-96 text-center relative">
        <button onclick="closePopup()" class="absolute top-2 right-2 text-white text-xl">&times;</button>
        <h2 class="text-2xl font-bold mb-4">Get in Touch</h2>
        <p class="text-lg">📧 Email: <a href="mailto:your.email@example.com" class="text-blue-400">your.email@example.com</a></p>
        <p class="text-lg">🔗 LinkedIn: <a href="https://www.linkedin.com/in/yourprofile" target="_blank" class="text-blue-400">linkedin.com/in/yourprofile</a></p>
    </div>
</div>

<script>
    function openPopup() {
        const popup = document.getElementById("popup");
        const popupBox = document.getElementById("popup-box");
        popup.classList.remove("hidden");
        setTimeout(() => popupBox.classList.add("popup-enter-active"), 10);
    }
    
    function closePopup() {
        const popup = document.getElementById("popup");
        const popupBox = document.getElementById("popup-box");
        popupBox.classList.remove("popup-enter-active");
        setTimeout(() => popup.classList.add("hidden"), 200);
    }
</script>

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)

### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
