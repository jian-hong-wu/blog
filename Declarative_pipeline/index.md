

# Declarative Pipeline

a. Pipeline的頂層必須是塊，具體來說是：pipeline { }  
b. 沒有分號作爲語句分隔符。每個宣告必須在自己的一行  
c. 塊只能包含Sections, Directives, Steps或賦值語句。  
d. 屬性參照語句被視爲無參方法呼叫。所以例如，輸入被視爲input（）

#### agent

agent部分指定整個Pipeline或特定階段將在Jenkins環境中執行的位置，具體取決於該agent 部分的放置位置。該部分必須在pipeline塊內的頂層定義 ，但stage級使用是可選的。　　

爲了支援Pipeline可能擁有的各種用例，該agent部分支援幾種不同類型的參數。這些參數可以應用於pipeline塊的頂層，也可以應用在每個stage指令內。

參數

any  
　　在任何可用的agent 上執行Pipeline或stage。例如：agent any  
none  
　　當在pipeline塊的頂層使用none時，將不會爲整個Pipeline執行分配全域性agent ，每個stage部分將需要包含其自己的agent部分。  
label  
　　使用提供的label標籤，在Jenkins環境中可用的代理上執行Pipeline或stage。例如：agent { label 'my-defined-label' }  
node  
　　agent { node { label 'labelName' } }，等同於 agent { label 'labelName' }，但node允許其他選項（如customWorkspace）。  
docker
　　定義此參數時，執行Pipeline或stage時會動態供應一個docker節點去接受Docker-based的Pipelines。 docker還可以接受一個args，直接傳遞給docker run呼叫。例如：agent { docker 'maven:3-alpine' }
