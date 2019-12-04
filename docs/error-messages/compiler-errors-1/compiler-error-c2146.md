---
title: Derleyici hatası C2146
ms.date: 11/04/2016
f1_keywords:
- C2146
helpviewer_keywords:
- C2146
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
ms.openlocfilehash: 8dc7b521243c4eafdc22fab851812b6c12b004cf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755921"
---
# <a name="compiler-error-c2146"></a>Derleyici hatası C2146

sözdizimi hatası: ' identifier ' tanımlayıcıdan önce ' token ' eksik

Derleyici `token` bekliyordu ve bunun yerine `identifier` buldu.  Olası nedenler:

1. Yazım veya büyük harf hatası.

1. Tanımlayıcının bildiriminde eksik tür belirleyicisi.

Bu hatanın nedeni bir yazım hatası olabilir. Hata [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md) genellikle bu hatadan önce gelir.

## <a name="example"></a>Örnek

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

## <a name="example"></a>Örnek

Bu hata, Visual Studio .NET 2003: eksik `typename` anahtar sözcüğü için yapılan derleyici uygunluk işinin sonucu olarak da oluşturulabilir.

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

## <a name="example"></a>Örnek

Ayrıca, bu hatayı Visual Studio .NET 2003 için yapılan derleyici uygunluk işinin bir sonucu olarak görürsünüz: açık uzmanlık, artık birincil şablondan şablon parametreleri bulamamıştı.

Birincil şablondan `T` kullanımına açık özelleştirmede izin verilmez. Kodun Visual Studio .NET 2003 ve Visual Studio .NET içinde geçerli olması için, özelleşmenin içindeki şablon parametresinin tüm örneklerini açıkça özelleştirilmiş tür ile değiştirin.

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
