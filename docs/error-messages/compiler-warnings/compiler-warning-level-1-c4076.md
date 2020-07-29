---
title: Derleyici Uyarısı (düzey 1) C4076
ms.date: 11/04/2016
f1_keywords:
- C4076
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
ms.openlocfilehash: 1958aec4d6642188af1467ab4cab1ecf55c29165
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223323"
---
# <a name="compiler-warning-level-1-c4076"></a>Derleyici Uyarısı (düzey 1) C4076

> '*tür değiştirici*': '*TypeName*' türüyle kullanılamaz

## <a name="remarks"></a>Açıklamalar

Bir tür değiştiricisi, veya olup olmadığı **`signed`** , **`unsigned`** tamsayı olmayan bir türle birlikte kullanılamaz. *tür değiştiricisi* yoksayıldı.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4076 oluşturur; Bu çözümü onarmak için **`unsigned`** tür değiştiricisini kaldırın:

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```
