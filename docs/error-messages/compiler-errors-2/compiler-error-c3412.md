---
title: Derleyici hatası C3412
ms.date: 11/04/2016
f1_keywords:
- C3412
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
ms.openlocfilehash: ad241b656464746333760cfcbc134c91e49bf44e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761422"
---
# <a name="compiler-error-c3412"></a>Derleyici hatası C3412

' Template ': şablon geçerli kapsamda özelleştirilemiyor

Şablon sınıf kapsamında, yalnızca genel veya ad alanı kapsamında özelleştirilemez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3412 oluşturur.

```cpp
// C3412.cpp
template <class T>
struct S {
   template <>
   struct S<int> {};   // C3412 in a class
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnekte olası bir çözüm gösterilmektedir.

```cpp
// C3412b.cpp
// compile with: /c
template <class T>
struct S {};

template <>
struct S<int> {};
```
