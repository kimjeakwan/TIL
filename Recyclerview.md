## 개념
* ListView는 사용자가 스크롤 할 때마다 위에 있던 아이템은 삭제되고, 
맨 아래의 아이템은 생성 되길 반복합니다.
아이템이 100개면 100번을 삭제 생성을 해야합니다.
즉 계속 삭제와 생서을 박복하므로 성능에 좋지않습니다.
* RecyclerView는 ListView의 단점을 보완하기 위해서 나왔습니다.
사용자가 스크롤 할 때, 위에 있던 아이템은 재활용 돼서 아래로 이동하여 재사용 합니다.
즉 아이템이 100개여도 10개정도의 View만 만들고 10개를 재활용해서 사용합니다.
View를 계속 만드는 ListView의 단점을 보완한 겁니다.그리고 이를 위해 기본적으로 뷰홀더 패턴을 사용하도록 만들었놨습니다.
1. notifyDataSetChanged
아이템 변경(데이터가 업데이트 되었지만 위치는 변하지 않았을 때), 구조적 변경(아이템간에 삽입, 삭제, 이동이 일어났을 때)에 사용한다.

2. notifyItemChanged(int position, Object payload)
position 위치의 아이템이 변경되었다고 어댑터에게 알리는 역할을 합니다.
3. notifyItemInserted(int position)
position 위치에 아이템이 추가 되는것을 알리는 역할을 합니다.

4. notifyItemMoved(int fromPostion, int toPosition)
인덱스 fromPosition 아이템이 toPosition으로 이동하였을 알려주는 역할을 합니다.

5. notifyItemRangeChanged(int positionStart, int itemCount, Object payload)
positionStart부터 itemCount개까지 범위에서 변경이 일어났음을 알려주는 역할을 합니다.

## 장/단점
1. 리사이클러뷰(RecyclerView)는 아이템을 표시하기위해 뷰홀더(ViewHolder)를 필수적으로 생성하도록 되어있습니다. 이는 단순 리사이클러뷰(RecyclerView)에 포함된 요소임을 넘어 개발자가 직접 뷰홀더(ViewHolder) 패턴을 적용할 때 고민해야 했던 여러 이슈들이 구현사황에 포함하다는것 것을 의미합니다. 예 로 리스트뷰에서 화면의 나열 방향을 수직에서 수평으로 바꾸기위해 리스트뷰가 아닌 다른 뷰를 사용하거나, 리스트뷰 기능을 상당부분 재 구현 해야합니다.하지만 리사이클러뷰는 이러한 단점을 보완하여 개발자가 쉽게 구현할 수 있도록 만들어줍니다.


## 왜 사용하는지
1. 리사이클러뷰는 다양한 레이아웃을 쉽게 구현할 수 있도록 LayoutManager를 제공합니다. 수직 또는 수평 스크롤을 지원하는 LinearLayoutManager, 그리드 형식의 GridLayoutManager, 복잡한 레이아웃을 구현할 수 있는 StaggeredGridLayoutManager 등을 사용할 수 있어, 다양한 UI를 손쉽게 구현할 수 있습니다.
2.  리사이클러뷰는 항목 사이의 구분선, 여백, 또는 배경을 쉽게 추가할 수 있는 ItemDecoration 클래스를 제공합니다. 이를 통해 리스트나 그리드의 외관을 손쉽게 커스터마이징할 수 있습니다.
아이템 터치 지원: ItemTouchHelper를 사용하여 드래그 앤 드롭, 스와이프와 같은 제스처를 쉽게 구현할 수 있습니다.
3. 뷰 재활용: 리사이클러뷰는 스크롤할 때 보이지 않는 아이템 뷰를 재활용(recycle)합니다. 이로 인해 새롭게 뷰를 생성하는 비용이 줄어들고 메모리 사용량이 크게 감소합니다.
## 문제점
1. 리사이클러뷰는 뷰를 재활용하기 때문에, 잘못된 재활용으로 인해 데이터가 섞이거나 UI가 올바르게 표시되지 않는 문제가 발생할 수 있습니다.(예 데이터 갱신 문제)
2. 이미지나 동영상 같은 미디어 요소가 포함된 경우, 스크롤이 부드럽지 않거나 지연이 발생할 수 있습니다


 
