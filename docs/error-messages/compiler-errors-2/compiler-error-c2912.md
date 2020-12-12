---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2912'
title: Derleyici hatası C2912
ms.date: 11/04/2016
f1_keywords:
- C2912
helpviewer_keywords:
- C2912
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
ms.openlocfilehash: 405c4acb5da6aa83e4b5d45e2297f1259a0d932e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270530"
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

Bu hata, Visual Studio .NET 2003 ' de gerçekleştirilen derleyici uygunluk işinin sonucu olarak da oluşturulacaktır: her açık özelleşme için, açık özelleşmenin parametrelerini, bu şekilde birincil şablonun parametreleriyle eşleştirecek şekilde seçmeniz gerekir.

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
