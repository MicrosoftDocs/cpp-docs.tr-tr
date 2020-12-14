---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3225'
title: Derleyici hatası C3225
ms.date: 11/04/2016
f1_keywords:
- C3225
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
ms.openlocfilehash: d186fc51917f7dfcfb44bbcd1dbf0b6de761ade6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304187"
---
# <a name="compiler-error-c3225"></a>Derleyici hatası C3225

' arg ' için genel tür bağımsız değişkeni ' Type ' olamaz; bir değer türü veya tanıtıcı türü olmalıdır

Genel tür bağımsız değişkeni doğru türde değil.

Daha fazla bilgi için bkz. [Genel türler](../../extensions/generics-cpp-component-extensions.md).

## <a name="examples"></a>Örnekler

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

Aşağıdaki örnek, C# kullanarak bir bileşen oluşturur. Kısıtlama genel türün yalnızca bir değer türüyle örneklenebilir olduğunu belirtir.

```
// C3225_b.cs
// compile with: /target:library
// a C# program
public class MyList<T> where T: struct {}
```

Bu örnek, C# yazılmış bileşenini kullanır ve MyList öğesinin yalnızca dışında bir değer türüyle örneklenebilir kısıtlamasını ihlal eder <xref:System.Nullable> . Aşağıdaki örnek C3225 oluşturur.

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
