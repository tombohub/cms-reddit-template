<script setup lang="ts">
import { ref } from "vue";

const formData = ref({
  weekNum: "",
  startDate: "",
  stocksOvRoi: "",
  spyRoi: "",
  stocksBnhRoi: "",
  stocksPdf: "",
  etfsOvRoi: "",
  etfsBnhRoi: "",
  etfsPdf: "",
  dataSheet: "",
});

const textRef = ref<HTMLPreElement | null>(null);
</script>

<template>
  <div>
    <label>
      Week num:
      <input v-model="formData.weekNum" />
    </label>
  </div>
  <br />
  <div>
    <label>
      Start Date:
      <input v-model="formData.startDate" />
    </label>
  </div>
  <br />
  <div>
    <label
      >Stock Roi:
      <input v-model="formData.stocksOvRoi" />
    </label>
  </div>
  <br />
  <div>
    <label>
      Spy roi:
      <input v-model="formData.spyRoi" />
    </label>
  </div>
  <br />
  <div>
    <label>
      Stocks bnh roi:
      <input v-model="formData.stocksBnhRoi" />
    </label>
  </div>
  <br />
  <div>
    <label>
      Stocks pdf:
      <input v-model="formData.stocksPdf" />
    </label>
  </div>
  <br />
  <div>
    <label>
      ETFs Ov roi:
      <input v-model="formData.etfsOvRoi" />
    </label>
  </div>
  <br />
  <div>
    <label>
      ETFs bnh roi::
      <input v-model="formData.etfsBnhRoi" />
    </label>
  </div>

  <br />

  <div>
    <label>
      ETFs pdf:
      <input v-model="formData.etfsPdf" />
    </label>
  </div>

  <br />

  <div>
    <label>
      Data sheet:
      <input v-model="formData.dataSheet" />
    </label>
  </div>

  <button>Copy</button>

  <textarea cols="100" rows="3">
Overnight Strategy backtest - week {{ formData.weekNum }}, 2023
  </textarea>

  <textarea ref="textRef" cols="100" rows="60">
**NEW**: daily report website in progress: [link](https://www.crunchmystock.com/)

.

Week | {{ formData.weekNum }}
---|---
Start Date | {{ formData.startDate }}
Start Capital | 100,000.00

**Overnight strategy** means buying at Close and selling next day Open, starting Monday

**SPY benchmark** is buying Monday Close selling next Monday Open

**Buy and hold benchmark** is buying Monday Close selling next Monday Open
___________________________________________________________________

STOCKS
-----------

Average ROI:

Overnight  | SPY | Buy and Hold
---|---|----
{{ formData.stocksOvRoi }}% | {{ formData.spyRoi }}% | {{
      formData.stocksBnhRoi
    }}%


**Report PDF:**

- {{ formData.stocksPdf }}
_______________________________________________________________________



ETFS
-----


Average ROI:

Overnight  | SPY | Buy and Hold
---|---|----
{{ formData.etfsOvRoi }}% | {{ formData.spyRoi }}% | {{ formData.etfsBnhRoi }}%


**Report PDF:**

- {{ formData.etfsPdf }}
__________________________________________________________________________

**DATA SPREADSHEET:**

- {{ formData.dataSheet }}
_______________________________________________________
Ideas and requests for analytics and backtesting -> comment, PM, or post in sticky thread:

- https://www.reddit.com/r/CrunchMyStock/comments/lxm7qy/backtesting_requests_and_ideas/
  </textarea>
</template>
