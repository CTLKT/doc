#### 柱状图
![](./img/可视化-1718108358940.png)
[bar1.json](json%2Fbar1.json)

![](./img/echarts-1718325834676.png)
[bar2.json](json%2Fbar2.json)
#### 饼图

图例左边四个 右边四个
![](./img/可视化-1718108692733.png)
[pie1.json](json%2Fpie1.json)

![](./img/可视化-1718108726788.png)
[pie2.json](json%2Fpie2.json)

![](./img/echarts-1722406172473.png)
```json
label: {
        formatter: '{b}    {d|{d}%}',
        rich: {
          d: {
            color: '#3388ff',
            fontWeight: 700
          }
        }
      },
```

![](./img/echarts-1722406722559.png)
```json
label: {
          show: true,
          formatter: function (params) {
            var name = params.data.name
            var value = params.data.value
            return (
              name + '\n' +
              (sum == 0 ? '0.00' : ((value / sum) * 100).toFixed(2)) + '%'
            )
          },
        },
```
![](./img/可视化-1718109285045.png)
[pie3.json](json%2Fpie3.json)
#### 折线图

![](./img/可视化-1718108543837.png)
[line1.json](json%2Fline1.json)


![](./img/可视化-1718153305660.png)
[line2.json](json%2Fline2.json)
