---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3412'
title: Derleyici hatası C3412
ms.date: 11/04/2016
f1_keywords:
- C3412
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
ms.openlocfilehash: aa0dc6cfeac193afc99d003cd821663bcfc139c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313196"
---
# <a name="compiler-error-c3412"></a>Derleyici hatası C3412

' Template ': şablon geçerli kapsamda özelleştirilemiyor

Şablon sınıf kapsamında, yalnızca genel veya ad alanı kapsamında özelleştirilemez.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C3412 oluşturur.

```cpp
// C3412.cpp
template <class T>
struct S {
   template <>
   struct S<int> {};   // C3412 in a class
};
```

Aşağıdaki örnekte olası bir çözüm gösterilmektedir.

```cpp
// C3412b.cpp
// compile with: /c
template <class T>
struct S {};

template <>
struct S<int> {};
```
