# 🌟 Welcome To (সহজ সরল সিম্পল) Assignment - 5

# **📅 Deadline For 60 marks:** 9th March, 2026 (11:59 pm ⏱️)  
#  📅 No Deadline For 50 marks  
# **📅 Deadline For 30 marks:** Any time after 9th March.

---

# Assignment-05: GitHub Issues Tracker


### **API Endpoints:**
###  **All Issues:** 
  - https://phi-lab-server.vercel.app/api/v1/lab/issues 


###  **Single Issue:**
   - https://phi-lab-server.vercel.app/api/v1/lab/issue/{id}

   - Example: https://phi-lab-server.vercel.app/api/v1/lab/issue/33


###  **Search Issue:** https://phi-lab-server.vercel.app/api/v1/lab/issues/search?q={searchText}

   - Example:  https://phi-lab-server.vercel.app/api/v1/lab/issues/search?q=notifications


---

## 📝 Main Requirements

## 🎨 Design Part

## Login Page
- Create a login page containing a logo, title, and sub-title
- Below that, there will be 2 inputs, a sign-in button, and a demo credential to sign in. Follow the Figma for this page 
- Styled as per Figma

## Main Page: 

### Navbar: 

- Navbar with website logo/name on the left
- Search input and button on the right

### Tab Section like Figma: 

- 3 tab ( All, Open, Closed) at the top of this section.(**All**, **Open**, **Closed**)

- Below the tab, there will be an icon, the issue count, some text on the left, and an open and closed marker on the right

- Responsiveness: The website should be responsive for mobile devices. It is totally up to you. 


--- 


## ⚙️ Functionalities
- In login page, there will be default admin credentials (username, password). You need to sign in using these credentials.

- Load all issues and display as per Figma

- On clicking on an open or closed tab, it will load the issues data of the related tab and show it in a display-like card in a 4-column layout like Figma. By default, it will show all data 

- Each card shows:
  - Title
  - Description
  - Status 
  - Author
  - Priority
  - Label
  - CreatedAt
- Clicking on an issue  card will open a modal and show all the information about that Issue. 

### 🚀 Challenges


- Show the card Top border based on their category(open, closed), open card will have Green Boder, closed card will have a purple border on top. 

- Loading spinner on data load

- Show active button on changing category names

- Implement Search Functionality and 8 meaningful github commit.  

- Create a readme file and answer this question on your own. Don’t copy-paste from Google or any AI chatbot. 

## 📚 JavaScript Concepts Explained

### 1️⃣ What is the difference between var, let, and const?

**var:**
- `var` is function-scoped and can be re-declared and re-assigned within its scope
- It's hoisted to the top of its function scope and initialized with `undefined`
- Generally considered outdated and should be avoided in modern JavaScript

**let:**
- `let` is block-scoped (limited to the nearest block like `if`, `for`, `while`)
- It can be re-assigned but cannot be re-declared in the same scope
- It's hoisted but not initialized (temporal dead zone)
- Preferred for variables that need to change

**const:**
- `const` is block-scoped like `let`
- It cannot be re-assigned or re-declared
- Must be initialized at declaration
- Preferred for values that won't change, makes code more predictable

**Example from our project:** In `app.js`, we use `const` for API endpoints and `let` for state variables like `filteredIssues` that change when filtering.

### 2️⃣ What is the spread operator (...)?

The spread operator (`...`) allows an iterable (arrays, strings, objects) to be expanded in places where zero or more elements are expected.

**Uses:**
- **Copying arrays:** `const newArr = [...oldArr]` creates a shallow copy
- **Merging arrays:** `const merged = [...arr1, ...arr2]`
- **Function arguments:** `Math.max(...numbers)`
- **Object copying/merging:** `const newObj = {...oldObj}`

**Example from our project:** We use it in `app.js` to copy arrays: `filteredIssues = [...allIssues]` to avoid mutating the original data when filtering issues.

### 3️⃣ What is the difference between map(), filter(), and forEach()?

**map():**
- Returns a new array by transforming each element with a callback function
- Doesn't modify the original array
- Use when you need to transform data

**filter():**
- Returns a new array with elements that pass the test in the callback function
- Doesn't modify the original array
- Use when you need to select specific elements based on a condition

**forEach():**
- Iterates through each element and executes a callback
- Returns `undefined`, doesn't create a new array
- Primarily for side effects (logging, DOM manipulation)
- Cannot be stopped with `break` or `return`

**Example from our project:** 
- `map()`: Could transform issues into a different format
- `filter()`: Used to filter issues by status: `allIssues.filter(issue => issue.status === 'open')`
- `forEach()`: Used to attach event listeners: `document.querySelectorAll('.tab-btn').forEach(btn => { btn.addEventListener(...) })`

### 4️⃣ What is an arrow function?

Arrow functions are a concise syntax for writing functions introduced in ES6.

**Syntax:** `const functionName = (parameters) => { body }`

**Key differences from regular functions:**
- Cannot be used as constructors (no `new` keyword)
- Don't have their own `this` - they inherit it from the parent scope
- Cannot be used as generators
- Shorter and cleaner syntax

**Example from our project:** Throughout our code:
```javascript
btn.addEventListener('click', (e) => {
    handleTabClick(e);
});

const labels = Array.isArray(issue.labels) ? issue.labels : [];

filteredIssues.forEach(issue => {
    const card = createIssueCard(issue);
});
```

Arrow functions make our event handlers and callbacks more concise and readable.

### 5️⃣ What are template literals?

Template literals are strings that allow embedding expressions using backticks (`` ` ``) instead of quotes.

**Features:**
- Use backticks instead of quotes: `` `string` ``
- Allow multi-line strings without concatenation
- Embed expressions with `${}`: `` `Hello ${name}` ``
- Much cleaner than string concatenation with `+`

**Example from our project:** In `app.js`, we extensively use template literals to build HTML:
```javascript
card.innerHTML = `
    <div class="issue-card-header">
        <div class="issue-title" title="${issue.title}">${issue.title}</div>
        <div class="issue-description">${issue.description || 'No description'}</div>
    </div>
    <div class="issue-meta">
        <span class="issue-status ${issue.status}">${issue.status.charAt(0).toUpperCase() + issue.status.slice(1)}</span>
    </div>
`;
```

Template literals make dynamic HTML generation much more readable and maintainable than string concatenation.


---

## 🛠️ Technology Stack

- **HTML**
- **CSS** (Vanilla/Tailwind/DaisyUI)
- **JavaScript** (Vanilla)

---

## 🔑 Demo Credentials

```text
Username: admin
Password: admin123
```


---

### Optional: 
 - No need to show status: Open, Closed styles On modals. 
 - No Need to show icon on labels 
 - No need to apply styles on Priority 
--- 


## 📤 What to submit

- **GitHub Repository Link:**
- **Live Site Link:**

---


# gitProject
# gitProject
