---
title: Derleyici Hatası C3225 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3225
dev_langs:
- C++
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8d8b1251b9c13a71faf771c85924a75681deab7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033257"
---
# <a name="compiler-error-c3225"></a>Derleyici Hatası C3225

genel tür bağımsız değişkeni 'arg' için 'type' olamaz, türü veya değer türü olması gerekir

Genel tür bağımsız değişkeni doğru türde değildi.

Daha fazla bilgi için [genel türler](../../windows/generics-cpp-component-extensions.md).

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