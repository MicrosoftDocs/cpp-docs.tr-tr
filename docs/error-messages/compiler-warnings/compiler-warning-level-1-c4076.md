---
title: Derleyici Uyarısı (düzey 1) C4076
ms.date: 11/04/2016
f1_keywords:
- C4076
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
ms.openlocfilehash: 77efeae27a67ea844759fd9980801d3daf788e89
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200279"
---
# <a name="compiler-warning-level-1-c4076"></a>Derleyici Uyarısı (düzey 1) C4076

> '*tür değiştirici*': '*TypeName*' türüyle kullanılamaz

## <a name="remarks"></a>Açıklamalar

**İmzalanmış** veya **işaretsiz**bir tür değiştiricisi, tamsayı olmayan bir türle birlikte kullanılamaz. *tür değiştiricisi* yoksayıldı.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4076 oluşturur; Bunu onarmak için **imzasız** tür değiştiricisini kaldırın:

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```
