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
   // HStack {
   // HStack(spacing: 0) { // 여백을 아예 제거하고 싶다면 별도로 spacing을 0 넣어줘야 한다
    HStack(alignment: .top, spacing: 0.0) { // alignment를 추가할 수 있다
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
    // .frame(width: 300, height: 300)
    .frame(maxWidth: .infinity, maxHeight: .infinity)
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
import SwiftUI

struct View_Stack: View {
  var body: some View {
    VStack(alignment: .center, spacing: 0.0) {
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
    .frame(maxWidth: .infinity, maxHeight: .infinity)
  }
}

struct View_VStack_Previews: PreviewProvider {
  static var previews: some View {
    View_VStack()
  }
}
```


```swift
import SwiftUI

struct View_ZStack: View {
  var body: some View {
    ZStack {
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

struct View_ZStack_Previews: PreviewProvider {
  static var previews: some View {
    View_ZStack()
  }
}
```


### Spacer


```swift
import SwiftUI

struct View_Spacer: View {
   var body: some View {
      VStack(spacing: 0) { // #6
         HStack {
            Image(systemName: "suit.heart.fill")
               .resizable()
               .frame(width: 70, height: 70)
               .foregroundColor(.white)
            
            // #3
         }
         .padding()
         .background(Color.blue)
         
         // #1
         
         VStack {
            // #5
            
            Image(systemName: "suit.spade.fill")
               .resizable()
               .frame(width: 70, height: 70)
               .foregroundColor(.white)
            
            // #4
         }
         .padding()
         .background(Color.red)
         
         // #2
      }
   }
}

struct View_Spacer_Previews: PreviewProvider {
   static var previews: some View {
      View_Spacer()
   }
}
```


### Button

```swift
import SwiftUI

struct View_Button: View {
   @State private var value = Int.random(in: 1...100)
   
   var body: some View {
      VStack {
         Spacer()
         
         Text("Random Number")
            .font(.largeTitle)
         
         Text("\(value)")
            .font(.system(size: 200))
         
         Spacer()
         
         // #1       
         Button(action: {
           self.value = Int.random(in: 1...100)
         }, label: {
           HStack {
             Image(systemName: "repeat")

             Text("Generate")

           }
           .frame(width: 200, height: 60)
           // .padding()
           .background(Color.blue) // 버튼 배경 색
           .foregroundColor(.whie) // 버튼 글씨 색
           .cornerRadius(20)
         })
      }
   }
}

struct View_Button_Previews: PreviewProvider {
   static var previews: some View {
      View_Button()
   }
}
```


### Toggle

```swift
import SwiftUI

struct View_Toggle: View {
   @State private var isOn = false
   
   var body: some View {
      VStack(alignment: .center, spacing: 30) {
         Image(systemName: isOn ? "lightbulb.fill" : "lightbulb")
            .resizable()
            .foregroundColor(isOn ? .yellow : .gray)
            .aspectRatio(contentMode: .fit)
            .frame(width: 300, height: 300)
         
         // #1
         //Toggle("Toggle Switch", isOn: $isOn)
         VStack(spacing: 30) {
            Toggle(isOn: $isOn, label: {
              EmptyView()
            })
            .labelIsHidden()
            .padding() // 이거만 써줘도 기본 여백이 양 옆에 추가된다         
         }
      }
   }
}

struct View_Toggle_Previews: PreviewProvider {
   static var previews: some View {
      View_Toggle()
   }
}
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
