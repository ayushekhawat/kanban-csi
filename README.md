<h1>Taskfiy - Inteligent task planner </h1>

---

<h2>LIVE:</h2>

- https://taskify-work-planner.vercel.app/

---

# ABOUT PROJECT :bulb: :

- <h3>:hammer: Why did we build this project ?</h3> Our motivation we found in the problem while planing our tasks. We needed something that would plan and calculate stages of our tasks for us.
- <h3>:technologist: How we found the solution ? </h3> So, we thought that is possible create a function which based on chooised by user <strong> start date</strong> and <strong> end date</strong> with help <strong> current date</strong>, will be calculate all needed informations and show data on charts. To sum up, the most important thing in all this are calculations based on <strong>3 dates</strong> and after all calculations our application show user his <strong> progress, finished days, future days and how much he must to do </strong> in chooised task.

---

### :raising_hand_man:

| AUTORS                                                     | FRONTEND                              | BACKEND                               |
|:----------------------------------------------------------:|:-------------------------------------:|:-------------------------------------:|
| **GabrielJuniorDev** ([Gabrli](https://github.com/Gabrli)) | ![100%](https://progress-bar.dev/100) | ![0%](https://progress-bar.dev/0)     |
| **gental-py** ([gental-py](https://github.com/gental-py/)) | ![0%](https://progress-bar.dev/0)     | ![100%](https://progress-bar.dev/100) |

---

## :hammer_and_wrench: Tech stack

<h1>Frontend</h1>

- <img src="https://github.com/devicons/devicon/blob/master/icons/react/react-original-wordmark.svg" title="React" alt="React" width="20" height="20"/>&nbsp; React + Vite
- <img src="https://github.com/devicons/devicon/blob/master/icons/typescript/typescript-original.svg" title="TypeScript" alt="TypeScript" width="20" height="20"/>&nbsp; TypeScript
- <img src="https://github.com/devicons/devicon/blob/master/icons/tailwindcss/tailwindcss-plain.svg"  title="CSS3" alt="CSS" width="20" height="20"/>&nbsp; Tailwindcss
- <img src="https://github.com/devicons/devicon/blob/master/icons/html5/html5-plain-wordmark.svg"  title="HTML" alt="HTML5" width="20" height="20"/>&nbsp; HTML5

<h1>Backend</h1>

- <img src="https://github.com/devicons/devicon/blob/master/icons/python/python-original-wordmark.svg"  title="Python3" alt="Python3" width="20" height="20"/>&nbsp; Python3
- <img src="https://github.com/devicons/devicon/blob/master/icons/fastapi/fastapi-original-wordmark.svg"  title="FastAPI" alt="FastAPI" width="20" height="20"/>&nbsp; FastAPI

---

### Other tools

- <img src="https://github.com/devicons/devicon/blob/master/icons/git/git-plain-wordmark.svg"  title="GIT" alt="GIT" width="20" height="20"/>  Git - version control system

---

<h2>SCREENS:</h2>
<h3>1.Landing page: </h3>
- Dark mode: 
<img src="https://github.com/Gabrli/Taskify/assets/110058841/030b5434-2656-4214-8fdc-e40a8c4c2e90"/>

- Light mode:
  
  <img src="https://github.com/Gabrli/Taskify/assets/110058841/fe667f16-3698-4486-a772-eb673f67c4d8"/>

<h3>2.Dashboard:</h3>
- Dark mode:
<img src="https://github.com/Gabrli/Taskify/assets/110058841/5dcce7b0-5bd4-42d8-a649-566996649ad3"/>

- With Notifications:
  
  <img src="https://github.com/Gabrli/Taskify/assets/110058841/9f81a1d5-6ec0-42a6-b923-6ea9d2d46fed"/>

---

### API Server

##### Response:

Every response is in `JSON` format and has a `"status"` key with a boolean value.

When the value is `True`, the action succeeded,

  and additional data may be passed by response

  (check the DATA ON SUCCESS column for details).

When the value is `False`, the required action failed,

  and the response will contain `"err_msg"` with

  an error message in a displayable form.

**All endpoints are POST methods**

(except `/accounts/getAllNames` which is **GET**)

| **ENDPOINT**               | **INPUT DATA**                                                                 | **DATA ON SUCCESS**                                                                                 |
| -------------------------- | ------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------- |
| `/accounts/login`          | `username`, `password`                                                         | uid: `str`                                                                                          |
| `/accounts/register`       | `username`, `password`, `email`                                                | uid: `str`                                                                                          |
| `/accounts/delete`         | `uid`                                                                          | -                                                                                                   |
| `/accounts/changePassword` | `uid`, `new`                                                                   | -                                                                                                   |
| `/accounts/getAllNames`    |                                                                                | names: `List[string]`                                                                               |
| `/tasks/create`            | `uid`, `name`, `description`, `date_start`, `date_end`, `Optional: folder_key` | task_id: `str`                                                                                      |
| `/tasks/edit`              | `uid`, `task_id` `name`, `description`, `date_start`, `date_end`               | -                                                                                                   |
| `/tasks/remove`            | `uid`, `task_id`                                                               | -                                                                                                   |
| `/tasks/getAll`            | `uid`                                                                          | tasks: `List[object]`<br/>[{`name`, `description`, `date_start`, `date_end`, `task_id`}, {...},...] |
| `/tasks/getTask`           | `uid`, `task_id`                                                               | task: `object`<br/>{`name`, `description`, `date_start`, `date_end`, `task_id`}                     |
| `/folders/create`          | `uid`, `name`, `color`                                                         | folder_key: `str`                                                                                   |
| `/folders/get_folder`      | `uid`, `folder_key`                                                            | folder: `object`<br/>{`author: str`, `name: str`, `color: str`, `task_ids: List[str]`}              |
| `/folders/update`          | `uid`, `folder_key`, `new_name`, `new_color`                                   | -                                                                                                   |
| `/folders/remove`          | `uid`, `folder_key`                                                            | -                                                                                                   |
| `/folders/add_task`        | `uid`, `folder_key`, `task_id`                                                 | -                                                                                                   |
| `/folders/remove_task`     | `uid`, `folder_key`, `task_id`                                                 | -                                                                                                   |

##### Run server:

1. Make sure You have `Python` and `pip` installed.

2. Install all requirements: `pip3 install -r requirements.txt` 

3. Run API locally:
   
   `python3 -m uvicorn api:api`

4. Deploy API:
   
   `python3 -m uvicorn api:api --host 0.0.0.0 --port YOUR_PORT`
