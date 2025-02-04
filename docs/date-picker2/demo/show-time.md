# 日期时间选择

- order: 6

如果需要同时选择时间，可以通过 `showTime` 属性开启，`timePanelProps` 支持传入`TimePickerPanel`的属性，例如 `format`, `defaultValue` 等。

:::lang=en-us
# With time

- order: 6

Enable `showTime` to create a DatePicker2/RangePicker with time.

:::

---

````jsx
import { DatePicker2 } from '@alifd/next';

const { RangePicker } = DatePicker2;
const onChange = (value) => console.log('onChange: ', value);
const onOk = (value) => console.log('onOK: ', value.format('YYYY-MM-DD HH:mm:ss'));
const onRangeOk = (value) => console.log('onOk: [%s, %s]', ...value);

const defaultTimeValue = '09:00:00';

ReactDOM.render(<div className="app">
  <div><DatePicker2 showTime onChange={onChange} onOk={onOk} /></div>
  <div><DatePicker2 showTime timePanelProps={{ defaultValue: defaultTimeValue, secondStep: 10 }} onChange={onChange} onOk={onOk} /></div>
  <div><RangePicker showTime onChange={onChange} onOk={onRangeOk} /></div>
  <div><RangePicker showTime timePanelProps={{ defaultValue: ['09:00', '23:59'], format: 'HH:mm', minuteStep: 15 }} onChange={onChange} onOk={onRangeOk} /></div>
</div>, mountNode);
````
```css
.app > div {
    margin-bottom: 20px;
}
```
