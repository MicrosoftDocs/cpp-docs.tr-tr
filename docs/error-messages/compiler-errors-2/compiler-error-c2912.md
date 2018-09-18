---
title: Derleyici Hatası C2912 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2912
dev_langs:
- C++
helpviewer_keywords:
- C2912
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1eb3a1aef43033c57f50cadda79bae3035aea978
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091926"
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