# SwiftUIWithKxCoding
https://kxcoding.com/course/mastering-swiftui

## System Views

### Stack
SwiftUI에는 세 축이 있다
- H: X Axis(X축)
  - 왼쪽부터 뷰 추가
- V: Y Axis(Y축)
  - 상단부터 뷰 추가
- Z: Z Axis(Z축)
  - 화면을 보는 방향으로 추가
  - 먼저 추가한 뷰는 시선이 가는 방향에서 아래쪽에 배치 됨
  - 나중에 추가한 뷰가 가장 위쪽에 배치 됨

```swift
import SwiftUI

struct View_HStack: View {
  var body: some View {
    HStack {
      Image(systemName: "suit.heart.fill")
        .resizable()
        .frame(width: 50, height: 50)
        .foregroundColor(.red)    

      Image(systemName: "suit.club.fill")
        .resizable()
        .frame(width: 50, height: 50)
        .foregroundColor(.red)    
        
      Image(systemName: "suit.spade.fill")
        .resizable()
        .frame(width: 50, height: 50)
        .foregroundColor(.red)        
        
      Image(systemName: "suit.diamond.fill")
        .resizable()
        .frame(width: 50, height: 50)
        .foregroundColor(.red)    
    }
  }
}

* 여백을 별도로 추가하지 않으면 기본 여백이 적용된다

struct View_HStack_Previews: PreviewProvider {
  static var previews: some View {
    View_HStack()
  }
}
```


```swift
```


```swift
```


```swift
```


```swift
```


```swift
```


```swift
```


```swift
```


```swift
```

## Text and Font

## Color and Image

## Animation

## List

## Navigation

## State and Binding

## Gestures

## Core Data
