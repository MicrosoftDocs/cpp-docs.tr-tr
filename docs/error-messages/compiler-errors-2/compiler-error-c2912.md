---
title: Derleyici hatası C2912
ms.date: 11/04/2016
f1_keywords:
- C2912
helpviewer_keywords:
- C2912
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
ms.openlocfilehash: 254252bfd21aa28c87810f1e21b4864e2775a71b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761091"
---
# <a name="compiler-error-c2912"></a>Derleyici hatası C2912

' bildirim ' açık özelleştirmesi bir işlev şablonunun özelleştirmesi değil

Şablon olmayan bir işlev özelleştirilemiyor.

Aşağıdaki örnek C2912 oluşturur:

```cpp
// C2912.cpp
// compile with: /c
void f(char);
template<> void f(char);   // C2912
template<class T> void f(T);   // OK
```

Bu hata, Visual Studio .NET 2003 ' de yapılan derleyicinin uyumluluk işinin sonucu olarak da oluşturulacaktır: her açık özelleşme için, açık özelleşmenin parametrelerini, örneğin, birincil öğesinin parametreleriyle eşleşecek şekilde seçmeniz gerekir. şablonlarını.

```cpp
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
