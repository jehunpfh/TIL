## Distribution이란?
- 스택뷰의 축을 따라서 정렬된 뷰들의 position과 size를 정의하는 레이아웃입니다.

## 속성
- 속성은 fill, fillEqaully, fillProportionally, eqaulSpacing, eqaulCentering이 있습니다.

#### fill

![Pasted image 20230314201049](https://user-images.githubusercontent.com/121538666/224994931-c35d9f86-d5bb-4e5f-b7fb-8db877f53d83.png)

- 스택뷰의 축을 따라서 스택뷰에 포함된 뷰들을 가용한 공간을 채우도록 조절합니다.
- 만약 뷰가 너무 커서 스택뷰에 맞지않는 경우 뷰는 compression resistance priority에 따라 줄어듭니다.
- 또한 뷰가 작아서 스택뷰를 채우지 못하는 경우 뷰는 hugging priority에 따라서 늘어납니다.
- 만약 모호함(priority가 같다면)이 있다면 스택뷰에 추가된 뷰들의 배열인 arrangedSubviews의 인덱스에 기반하여 사이즈가 조정됩니다.

#### fillEqually

![Pasted image 20230314201547](https://user-images.githubusercontent.com/121538666/224994935-088fe0d3-66c1-432a-9ff8-04187bcdfc41.png)

- 스택뷰의 축을 따라서 스택뷰에 포함된 뷰들을 가용한 공간을 채우도록 조절합니다.
- 스택뷰에 포함된 뷰들을 스택뷰에 축에따라 똑같은 사이즈를 가지도록 조절합니다.
> fill과의 차이점이라면 모든 뷰가 스택뷰의 축방향으로 동일한 사이즈를 갖는다는 것입니다. fill은 우선순위에 따라 가용한 공간을 채워줍니다. 따라서 모두 동일한 사이즈는 아니죠.

#### fillProportionally

![Pasted image 20230314201831](https://user-images.githubusercontent.com/121538666/224994938-39e22864-60fb-4281-b89d-ca88c2be54c1.png)

- 스택뷰의 축을 따라서 스택뷰에 포함된 뷰들을 가용한 공간을 채우도록 조절합니다.
- 스택뷰에 축을 따라서 각각의 뷰에 들어있는 내용에 따라서 비율적으로 사이즈를 조절합니다.

#### equalSpacing

![Pasted image 20230314202518](https://user-images.githubusercontent.com/121538666/224994941-dbe5dde8-c873-4fe0-a568-0f30c249f7e7.png)

- 스택뷰의 축을 따라서 스택뷰에 포함된 뷰들을 가용한 공간을 채우도록 조절합니다.
- 뷰들이 작아서 스택뷰를 채우지 못할 때, 뷰들 사이에 균일하게 spacing을 추가합니다.
- 만약 뷰들이 너무 커서 스택뷰에 맞지 않을 때, 뷰들을 compression resistance priority에 따라 줄입니다.
- 만약 모호함이 있는 경우, arrangedSubviews 배열의 인덱스에 따라 뷰를 줄입니다.

#### equalCentering

![Pasted image 20230314203634](https://user-images.githubusercontent.com/121538666/224994945-0e1e907f-7a2d-4859-a139-ffc6474a7d01.png)

- 뷰 사이의 spacing property's distance를 유지하면서, 스택뷰의 축을 따라서 스택뷰에 포함된 뷰들의 중심에서 중심의 spacing을 조절합니다.
- 만약 뷰들이 커서 스택뷰에 맞지 않는다면, spacing을 스택뷰의 spacing property에 설정된 최소크기까지 줄입니다.
- 만약 최소크기까지 줄였음에도 아직도 맞지 않는다면, 뷰들을 compression resistance priority에 따라서 줄입니다.
- 만약 모호하다면, arrangedSubViews 배열의 인덱스에 따라 줄입니다.
- 스택뷰는 뷰들의 중심에서 중심의 spcaing을 조절할 때, 뷰 내부의 내용의 사이즈를 유지합니다. 
- 이와 비슷하게 스택뷰는 뷰의 내부 내용의 사이즈를 조절할 때, 뷰와 뷰 사이에 최소의 spacing을 유지합니다.
