---
title: Derleyici Hatası C2146 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2146
dev_langs:
- C++
helpviewer_keywords:
- C2146
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d75a9a6e2d7ad4b32f9c6ffa41287aa25399eb4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092160"
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

Kullanımını `T` birincil şablondan açık özelleştirmede izin verilmez. Visual C++ Visual Studio .NET 2003 ve Visual Studio sürümlerinde geçerli olması kodu için şablon parametresi uzmanlıktaki tüm örneklerini açıkça özel türüyle değiştirin.

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