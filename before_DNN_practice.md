# torchvision.datasets

# torchvision.transforms

## transforms.Compose()



## FashionMNIST



### 多data益善 : 모델이 이 데이터를 학습하면서 더욱 견고해짐
but GD 각 데이터마다 cost를 구해야 하는데 데이터가 넘나 많으면 넘나 느림
한번에 학습하는 것은 불가능함.
일부분의 데이터로만 학습

데이터를 균일하게 나누어 학습
Minibatch GD effects : 업데이트를 좀 더 빨리 할 수 있다.
전체 데이터를 쓰지 않아서 잘못된 방향으로 업데이트를 할 수 있기에 기존 GD 처럼 매끄럽게 줄어들지 않고 거칠게 줄어듬.

datasest을 mini-batch 로 쪼개는데 쓰는 module
-> Dataset, DataLoader
dataset을 만든 후 datalodader


# Dataset

torch.utils.data.Dataset 상속을 하여 새로운 클래스를 만듬
-> 원하는 데이터 셋을 지정하여 customized dataset을 만들어 쓴다.

### __len__()
- dataset의 총 데이터 갯수 
### __getitem__()
- 어떤 index를 받았을 때 그에 상응하는 입출력 데이터 반환.



# DataLoader

torch.utils.data.DataLoader의 instance를 만들어줌

- instance 만드려면 2개 지정해줘야함.
- dataset
- mini-batch 크기: 2의 제곱수
- shuffle=True : 매번 데이터가 학습되는 순서를 바꾸어줌. 모델이 데이터 셋의 순서를 외우지 못하도록 True로 권장.


