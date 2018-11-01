---
title: Derleyici Hatası C2912
ms.date: 11/04/2016
f1_keywords:
- C2912
helpviewer_keywords:
- C2912
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
ms.openlocfilehash: b7f87ae2df5350fcfb2b7a662f517d8d7bd51ef8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540081"
---
# <a name="compiler-error-c2912"></a>Derleyici Hatası C2912

Açık özelleştirme 'bildirim' bir işlev şablonunun bir özelleştirmesi değil

Bir şablon olmayan işlev özelleştirilemiyor.

Aşağıdaki örnek, C2912 oluşturur:

```
// C2912.cpp
// compile with: /c
void f(char);
template<> void f(char);   // C2912
template<class T> void f(T);   // OK
```

Bu hata ayrıca Visual Studio .NET 2003'te yapıldığı derleyici uyumluluğu iş sonucu olarak oluşturulur: tüm açık özelleştirme için birincil parametreleriyle eşleşecek şekilde açık uzmanlığında parametrelerinin seçmeniz gerekir şablonu.

```
// C2912b.cpp
class CF {
public:
   template <class A> CF(const A& a) {}   // primary template

   // attempted explicit specialization
   template <> CF(const char* p) {}   // C2912

   // try the following line instead
   // template <> CF(const char& p) {}
};
```