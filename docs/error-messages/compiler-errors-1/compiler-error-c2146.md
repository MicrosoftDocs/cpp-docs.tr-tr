---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2146'
title: Derleyici hatası C2146
ms.date: 11/04/2016
f1_keywords:
- C2146
helpviewer_keywords:
- C2146
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
ms.openlocfilehash: ccca0099401838a918ad5443ce8194df853184bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223509"
---
# <a name="compiler-error-c2146"></a>Derleyici hatası C2146

sözdizimi hatası: ' identifier ' tanımlayıcıdan önce ' token ' eksik

`token`Bunun yerine derleyicinin beklenen ve bulduğu `identifier` .  Olası nedenler:

1. Yazım veya büyük harf hatası.

1. Tanımlayıcının bildiriminde eksik tür belirleyicisi.

Bu hatanın nedeni bir yazım hatası olabilir. Hata [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md) genellikle bu hatadan önce gelir.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C2146 oluşturur.

```cpp
// C2146.cpp
class CDeclaredClass {};

class CMyClass {
   CUndeclared m_myClass;   // C2146
   CDeclaredClass m_myClass2;   // OK
};

int main() {
   int x;
   int t x;   // C2146 : missing semicolon before 'x'
}
```

Bu hata, Visual Studio .NET 2003: eksik anahtar sözcüğü için yapılan derleyici uygunluk işinin sonucu olarak da oluşturulabilir **`typename`** .

Aşağıdaki örnek Visual Studio .NET 2002 ' de derlenir ancak Visual Studio .NET 2003 ' de başarısız olur:

```cpp
// C2146b.cpp
// compile with: /c
template <typename T>
struct X {
   struct Y {
      int i;
   };
   Y memFunc();
};

template <typename T>
X<T>::Y func() { }   // C2146

// OK
template <typename T>
typename X<T>::Y func() { }
```

Ayrıca, bu hatayı Visual Studio .NET 2003 için yapılan derleyici uygunluk işinin bir sonucu olarak görürsünüz: açık uzmanlık, artık birincil şablondan şablon parametreleri bulamamıştı.

`T`Açık özelleştirmede birincil şablondan kullanılmasına izin verilmiyor. Kodun Visual Studio .NET 2003 ve Visual Studio .NET içinde geçerli olması için, özelleşmenin içindeki şablon parametresinin tüm örneklerini açıkça özelleştirilmiş tür ile değiştirin.

Aşağıdaki örnek Visual Studio .NET içinde derlenir ancak Visual Studio .NET 2003 'de başarısız olur:

```cpp
// C2146_c.cpp
// compile with: /c
template <class T>
struct S;

template <>
struct S<int> {
   T m_t;   // C2146
   int m_t2;   // OK
};
```
