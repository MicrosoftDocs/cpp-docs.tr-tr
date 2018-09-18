---
title: Derleyici Hatası C3412 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3412
dev_langs:
- C++
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6a04de132c85cb09a960d3a0edfcb3b07127119
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054584"
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