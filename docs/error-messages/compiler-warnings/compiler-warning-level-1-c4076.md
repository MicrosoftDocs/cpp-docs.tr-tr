---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4076'
title: Derleyici Uyarısı (düzey 1) C4076
ms.date: 11/04/2016
f1_keywords:
- C4076
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
ms.openlocfilehash: 0bae49d3af23e499851fbf70fb24fdeb817ee03c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198264"
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
