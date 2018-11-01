---
title: Derleyici Hatası C3412
ms.date: 11/04/2016
f1_keywords:
- C3412
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
ms.openlocfilehash: 7c16ffa37f4d7192956afae26c825b63add1bfdd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540259"
---
# <a name="compiler-error-c3412"></a>Derleyici Hatası C3412

'şablon': şablon geçerli kapsamda özelleştirilemiyor

Sınıf kapsamında, yalnızca genel veya ad alanı kapsamında bir şablonu özelleştirilemez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3412 oluşturur.

```
// C3412.cpp
template <class T>
struct S {
   template <>
   struct S<int> {};   // C3412 in a class
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnekte, olası bir çözüm gösterilmektedir.

```
// C3412b.cpp
// compile with: /c
template <class T>
struct S {};

template <>
struct S<int> {};
```