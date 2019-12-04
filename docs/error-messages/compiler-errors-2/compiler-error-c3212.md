---
title: Derleyici hatası C3212
ms.date: 11/04/2016
f1_keywords:
- C3212
helpviewer_keywords:
- C3212
ms.assetid: 9e271bb6-a51f-4b96-b26b-9f4ca28fca0a
ms.openlocfilehash: 4881100cd76473f87b597989010376e8809ef7ff
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736743"
---
# <a name="compiler-error-c3212"></a>Derleyici hatası C3212

' özelleşme ': bir şablon üyesinin Açık özelleştirmesi bir açık özelleştirmenin üyesi olmalıdır

Açık bir özelleştirme hatalı biçimlendirilmiş.

Aşağıdaki örnek C3212 oluşturur:

```cpp
// C3212.cpp
// compile with: /LD
template <class T>
struct S {
   template <class T1>
   struct S1;
};

template <class T>   // C3212
template <>
struct S<T>::S1<int> {};

/*
// try the following instead
template <>
template <>
struct S<int>::S1<int> {};
*/

/*
// or, the following
template <>
struct S<int> {
   template <class T1>
   struct S1;
};

template <>
struct S<int>::S1<int> {
};
*/
```
