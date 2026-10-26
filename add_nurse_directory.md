# Feature Spec — Preferred Nurse Selection (Booking Step 3)

## 1. Summary

Add a **third step** to the service booking flow that lets the user pick their **preferred nurse**.

Nurse options are filtered from `assets/nurse_details.json` using the **service type** and **shift type** the user selected in **Step 1**. Each nurse is shown as a premium card. Selecting a nurse is required before the user can confirm the booking.

---

## 2. Goals

- Insert a new Step 3 ("Choose your nurse") between the current Step 2 and booking confirmation.
- Show a **live-filtered** list of nurses based on Step 1 selections.
- Display the **price** for the selected service + shift at the top of Step 3.
- Allow exactly **one** nurse to be selected at a time, with a clear selected state.
- Move the **Confirm Booking** action from Step 2 to Step 3.

## 3. Non-goals

- Do not edit `nurse_details.json` or change its schema.
- Do not add search, sort, or filter controls to Step 3 (filtering is automatic).
- Do not change Step 1 or Step 2 UI beyond removing the Confirm Booking button from Step 2.
- Do not build a nurse profile/detail page in this iteration.

---

## 4. Booking flow (before → after)

**Before**

```
Step 1: Select service + shift  →  Step 2: Details + Confirm Booking
```

**After**

```
Step 1: Select service + shift
   ↓
Step 2: Booking details (Confirm Booking button REMOVED)
   ↓
Step 3: Choose your nurse  ← NEW
   ↓
Confirm Booking
```

- The step indicator must show **3 steps**.
- Back navigation from Step 3 → Step 2 must preserve all Step 2 form input.
- If the user changes **service type** or **shift type** after visiting Step 3, the nurse list and the previously selected nurse must be **re-validated**: if the selected nurse no longer matches the new filters, clear the selection.

---

## 5. Data source

| Item | Value |
|---|---|
| File | `assets/nurse_details.json` |
| Shape | Flat JSON array of nurse objects |
| Access | Fetch once, cache in memory for the session |

### Nurse object

```ts
interface Nurse {
  name: string;
  certifications: string[];     // e.g. ["B.Sc", "MSN"]
  experienceYears: number;
  languages: string[];          // e.g. ["English", "Hindi"]
  rating: number;               // 0–5, one decimal
  reviewCount: number;
  specialties: string[];        // matches Step 1 service type
  shift?: string[];             // "12-Hour Duty" | "24-Hour Duty" — MAY BE MISSING
  photo: string;                // e.g. "assets/photos/Muskan.jpg"
}
```

> ⚠️ Some entries (e.g. `Gitartha`, `Raajeev`, `Rekha`, `Rishika`, `Srijan`, `Vanshika`, `Vikram`, `Yatika`) have **no `shift` field**. Handle this explicitly — see §7.

---

# important note
- use json file (assets/nurse_details.json) to fetch nurse details.
and display nurse details in a card view. based on the (service type) and (shift type) user choosed in step 1.
- currently (confirm booking) is in step 2 but it will be in step 2 after user selecting a nurse in step 3.
- price will also be displayed at the top of the screen based on the (service type) and (shift type) user choosed in step 1.


# card view look
- look modern and premium
- adjust the photo of nurse in a rounded rectangle shape and make it borderd with light gray 
- certifications and specialties will be in badge form ( a tranparent white pill shaped)
- when user click on (select) button then it will be selected and show selected state with green tick and border