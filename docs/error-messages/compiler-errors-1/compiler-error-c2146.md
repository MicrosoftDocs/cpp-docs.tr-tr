---
title: Derleyici Hatası C2146
ms.date: 11/04/2016
f1_keywords:
- C2146
helpviewer_keywords:
- C2146
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
ms.openlocfilehash: f00de0ce491d517da11f251b89ccb9a7ae66b77d
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447271"
---
# <a name="compiler-error-c2146"></a>Derleyici Hatası C2146

sözdizimi hatası: 'tanımlayıcıdan önce 'identifier' token' eksik

Beklenen derleyici `token` ve `identifier` yerine.  Olası nedenler:

1. Yazım ve büyük/küçük harf hata oluştu.

1. Tanımlayıcının bildiriminde tür belirticisi eksik.

Bir yazım hatası Bu hataya neden. Hata [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md) genellikle bu hata önce gelir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2146 oluşturur.

```
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

Bu hata için Visual Studio .NET 2003 yapıldığı derleyici uyumluluğu iş sonucu olarak da oluşturulabilir: eksik `typename` anahtar sözcüğü.

Aşağıdaki örnek Visual Studio .NET 2002 derlenir, ancak Visual Studio .NET 2003'te başarısız olur:

```
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

Bu hata için Visual Studio .NET 2003 yapıldığı derleyici uyumluluğu iş sonucu olarak da göreceksiniz: açık uzmanlık artık birincil şablondan şablon parametreleri bulun.

Kullanımını `T` birincil şablondan açık özelleştirmede izin verilmez. Visual Studio .NET ve Visual Studio .NET 2003 geçerli olması kodu için şablon parametresi uzmanlıktaki tüm örneklerini açıkça özel türüyle değiştirin.

Aşağıdaki örnek Visual Studio. NET'te derlenir, ancak Visual Studio .NET 2003'te başarısız olur:

```
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