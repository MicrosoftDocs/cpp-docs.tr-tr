---
title: Derleyici Hatası C3225
ms.date: 11/04/2016
f1_keywords:
- C3225
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
ms.openlocfilehash: cae0572002c849fb5aed771993d3a89ed82c726a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58778318"
---
# <a name="compiler-error-c3225"></a>Derleyici Hatası C3225

genel tür bağımsız değişkeni 'arg' için 'type' olamaz, türü veya değer türü olması gerekir

Genel tür bağımsız değişkeni doğru türde değildi.

Daha fazla bilgi için [genel türler](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Yerel bir tür ile genel tür örneği oluşturulamıyor. Aşağıdaki örnek, C3225 oluşturur.

```
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

Aşağıdaki örnek, C# kullanarak bir bileşen oluşturur. Kısıtlamanın genel tür yalnızca bir değer türü ile oluşturulmasını belirtir dikkat edin.

```
// C3225_b.cs
// compile with: /target:library
// a C# program
public class MyList<T> where T: struct {}
```

## <a name="example"></a>Örnek

Bu örnek C# kullanan-bileşen yazılan ve MyList yalnızca olabilir kısıtlamayı ihlal eden bir değer türü ile dışında örneği <xref:System.Nullable>. Aşağıdaki örnek, C3225 oluşturur.

```
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