this project uses javascript 
(the stuff below is what I got from gemini so I'm still working on this skill)

---

## 1. Test Strategy

We use **Jest** as our primary JavaScript testing framework. 


---

## 2. Manual Test Table

our manual testing

| Test ID | Feature / Component | Description / Steps | Expected Result |
| :--- | :--- | :--- | :--- |
| **MT-01** | UI Themes | Switch between Light and Dark mode via the settings toggle. | UI colors adapt immediately; contrast ratios remain accessible, and no text becomes invisible. |
| **MT-02** | Audio / Background Music | Allow the background music to play past its duration mark. | The background music loops seamlessly without abrupt clipping, pops, or noticeable silence. |
| **MT-03** | Responsive Design | Resize the browser window from Desktop ($1920\times1080$) down to Mobile ($375\times812$). | Elements scale gracefully; navigation collapses into a hamburger menu, and no content overlaps. |
| **MT-04** | CSS Animations | Trigger the success state or modal popup. | Animation runs smoothly at 60fps without stuttering, jank, or layout shifts. |

---

## 3. Automated Test Suite

this is our automated testing

### Function 1: Data Validation (`validateInput`)
* **File:** `src/utils/validation.js`
* **Description:** Ensures user-submitted string inputs meet formatting and length constraints.
* **Test Cases:**
    * Returns `true` for a valid, sanitized email address.
    * Returns `false` and throws a specific error for empty strings or strings exceeding maximum length.

### Function 2: State Management (`updateScore`)
* **File:** `src/game/scoreEngine.js`
* **Description:** Handles score increments and multiplier calculations based on performance.
* **Test Cases:**
    * Correctly increments the score by base points on a standard success event.
    * Applies a double multiplier ($2\times$) when a streak greater than 5 is achieved.

### Function 3: API Response Parsing (`fetchUserData`)
* **File:** `src/services/api.js`
* **Description:** Asynchronously fetches and maps raw payload data into our internal user model.
* **Test Cases:**
    * Successfully resolves with camelCase object keys when the API returns a snake_case payload.
    * Gracefully rejects and falls back to a default profile object if the network returns a 500 status code.
