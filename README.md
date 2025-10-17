# Digit Span Task created with jsPsych

# Digit Span Task (jsPsych)

This repository contains a **Digit Span Task** implemented using **jsPsych** (de Leeuw, J. R., 2015), a library for creating behavioral experiments in a web browser. The task measures an individual's short-term working memory capacity.

---

## 🚀 Getting Started

To run the task, open the `index.html` file located in either the **`offline`** or **`online`** folder.

| Folder | Subject ID & Session | Use Case |
| :--- | :--- | :--- |
| **`offline`** | Subject and session numbers can be customized upon startup. | Local testing, lab settings. |
| **`online`** | A 15-character long random subject ID is automatically generated. | Online data collection. |

### Browser Requirements

The task is compatible with most modern browsers, with **Chrome** being recommended.

**Incompatible Browsers:** Safari and Internet Explorer.

---

## 🧠 Task Structure and Procedure

The Digit Span Task requires the user to recall a sequence of visually presented digits in the correct order of appearance.

### Stimulus Presentation

* **Digits:** Single digits (1-9) are presented one at a time on the screen.
* **Rate:** Each digit appears for **1 second (1000 ms)**.
* **Response:** After the sequence is complete, a textbox appears. The user must type their remembered sequence and submit the answer by clicking the **'Continue'** button or hitting the **'Enter'** key.

### Levels and Progression

The task consists of up to seven levels, starting with practice runs.

1.  **Practice Runs:** Two runs are presented, each with a length of **2 digits**. Immediate feedback on correctness is provided.
2.  **Task Runs:** The main task starts at a sequence length of **3 digits**.
    * **Length Progression:** The sequence length increases by one digit for each subsequent level, up to a maximum of **9 digits**.
    * **Trials per Level:** Each level consists of **four trials**.
    * **Advancement:** To proceed to the next level, the user must correctly recall the sequence in **at least three out of the four trials** (75% accuracy).
    * **Task End:** If the user fails to meet the criterion (fewer than three correct answers) for the current level, the task terminates.

---

## ⚙️ Setting Options

You can customize the task parameters by modifying the **`parameters.js`** file.

| Parameter | Description | Default Setting |
| :--- | :--- | :--- |
| **Duration of Stimulus** | The presentation time for each digit. | 1000 ms |
| **Language** | Task instructions and text. | English (`en`) |

**Available Languages:** English (`en`), Hungarian (`hu`), Spanish (`es`), French (`fr`), Portuguese (`pt`).

---

## 💾 Output File Data

The experiment generates a data file with the following key variables:

| Variable | Description |
| :--- | :--- |
| **`subject`** | 15-character random ID (online) or customized number (offline). |
| **`session`** | Customized session number (offline version only). |
| **`trial_type`** | jsPsych trial type (e.g., `survey-html-form`, `html-keyboard-response`). |
| **`trial_index`** | Cumulative number of all events (including instructions and feedback). |
| **`time_elapsed`** | Time since the script started, in milliseconds (ms). |
| **`test_part`** | The segment of the task (e.g., `instruction`, `stimulus`, `answer`, `feedback`, `debrief`). |
| **`level`** | The current length of the digit sequence (2 for practice, 3-9 for main task). |
| **`number_within_level`** | Trial count within the current level (1-2 for practice, 1-4 for main task). |
| **`correct_answer`** | The correct stimulus stream (the sequence of digits presented). |
| **`responses`** | The sequence typed by the user in the input field. |
| **`rt`** | Reaction time for submitting the answer (in ms). |
| **`is_mistake`** | Indicates incorrect response (0 = correct, 1 = incorrect). |
| **`digit_span`** | The final Digit Span score (the maximum sequence length for which the 3/4 trial criterion was met). |
| **`success`** | Indicates whether fullscreen mode successfully started/ended (`true` or `false`). |
| **`browser_event`** | Records relevant browser events (e.g., `blur`, `focus`, `fullscreenenter`). |

---

## 📝 Citation

If you use this script in your research, please include the following citation in your manuscript: Vékony, T. (2021). Digit Span Task created with jsPsych (Version 1.0.0) [Computer software]. https://doi.org/10.5281/zenodo.7096258
