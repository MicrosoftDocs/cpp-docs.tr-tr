---
title: Derleyici hatası C3225
ms.date: 11/04/2016
f1_keywords:
- C3225
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
ms.openlocfilehash: 1caa1e7ce787ffc14e615c946b5d670c75e0332a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757624"
---
# <a name="compiler-error-c3225"></a>Derleyici hatası C3225

' arg ' için genel tür bağımsız değişkeni ' Type ' olamaz; bir değer türü veya tanıtıcı türü olmalıdır

Genel tür bağımsız değişkeni doğru türde değil.

Daha fazla bilgi için bkz. [Genel türler](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Yerel bir tür ile genel bir tür örnekleyemezsiniz. Aşağıdaki örnek C3225 oluşturur.

```cpp
// C3225.cpp
// compile with: /clr
class A {};

ref class B {};

generic <class T>
ref class C {};

int main() {
   C<A>^ c = gcnew C<A>;   // C3225
   C<B^>^ c2 = gcnew C<B^>;   // OK
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek kullanarak C#bir bileşen oluşturur. Kısıtlama genel türün yalnızca bir değer türüyle örneklenebilir olduğunu belirtir.

```
// C3225_b.cs
// compile with: /target:library
// a C# program
public class MyList<T> where T: struct {}
```

## <a name="example"></a>Örnek

Bu örnek, C#-yazılan bileşeni kullanır ve myList 'in yalnızca <xref:System.Nullable>dışında bir değer türüyle örneklenebilir kısıtlamasını ihlal eder. Aşağıdaki örnek C3225 oluşturur.

```cpp
// C3225_c.cpp
// compile with: /clr
#using "C3225_b.dll"
ref class A {};
value class B {};
int main() {
   MyList<A> x;   // C3225
   MyList<B> y;   // OK
}
```
