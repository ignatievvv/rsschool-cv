# [rsschool-cv](https://github.com/ignatievvv/rsschool-cv/cv)

![avatar](https://cdn.rs.school/ignatievvv.png?size=192)

# **Vladimir Ignatiev**

## Junior Frontend Developer

---

- **Country:** Russian Federation
- **City:** St. Petersburg
- **Phone:** +7 999 536 1417
- **Telegram:** @ram_entreya
- **E-mail:** vladimir-ignatiev@hotmail.com
- **GitHub:** [ignatievvv](https://github.com/ignatievvv)

---

Beginner specialist in programming / IT-industry.  
Ready for fast studying and learning new skills.  
Solving tasks creatively. Finding non-standart solutions.
Extremely attentive to details.

### **Technical skills:**

---

- JavaScript
- TypeScript
- HTML/CSS
- VS Code
- Git
- Github
- Webpack
- Figma
- React (basics)
- Sony Vegas, Adobe Audition
- MathLab, MathCad
- Kompas 3D, SolidWorks

### **Education:**

---

- 2015 - **Rocket Systems and Astronautics** (Bachelor degree)  
  Omsk State Technical University

- 2017 - **Rocket Systems and Astronautics** (Master’s degree)  
  Baltic State Technical University

- 2021 - [**JAVASCRIPT/FRONT-END 2021Q1 (JAVASCRIPT)**](https://app.rs.school/certificate/ntejfkus)  
  [The Rolling Scopes School](https://rs.school/)

### **English level:**

---

Pre-Intermediate (_А2/В1_)

### **Sample of code:**

---

```javascript
import './form.css';
import React, { useState } from 'react';
import FormItemText from '../form_item_text/form_item_text';
import FormItemSort from '../form_item_sort/form_item_sort';
import { FormValues, SortType } from '../form_values/form_values';
import FormItemResults from '../form_item_results/form-item-results';
import FormItemNumber from '../form_item_number/form_item_number';

const INIT_SORT_TYPE = 'relevancy';
const INIT_RESULTS_NUMBER = '10';
const INIT_PAGE_NUMBER = '1';
const CLASS_NAME = 'form';
const SUBMIT_CLASS_NAME = `${CLASS_NAME}__submit`;
const LOADING_LABEL = 'Loading...';
const SEARCH_LABEL = 'Search';

interface IForm {
  setFormValues: (values: FormValues) => void,
  loadingStatus: boolean
}

export function Form(props: IForm): JSX.Element {

  const [text, setText] = useState('');
  const [sort, setSort] = useState<SortType>(INIT_SORT_TYPE);
  const [resultsNumber, setResultsNumber] = useState(INIT_RESULTS_NUMBER);
  const [pageNumber, setPageNumber] = useState(INIT_PAGE_NUMBER);


  const handleSubmit = (event: React.FormEvent) => {
    event.preventDefault();
    props.setFormValues({text, sort, resultsNumber, pageNumber});
  }

  return (
    <form action="" className={CLASS_NAME} onSubmit={handleSubmit}>
      <FormItemText rootClassName={CLASS_NAME} state={text} setState={setText} disabled={props.loadingStatus}/>
      <FormItemSort rootClassName={CLASS_NAME} state={sort} setState={setSort} disabled={props.loadingStatus}/>
      <FormItemResults
        rootClassName={CLASS_NAME}
        state={resultsNumber}
        setState={setResultsNumber}
        disabled={props.loadingStatus}
      />
      <FormItemNumber
        rootClassName={CLASS_NAME}
        state={pageNumber}
        setState={setPageNumber}
        disabled={props.loadingStatus}
      />
      <button className={SUBMIT_CLASS_NAME} type='submit' disabled={props.loadingStatus || !text}>
        {props.loadingStatus ? LOADING_LABEL : SEARCH_LABEL}
      </button>
    </form>
  )
}
```
