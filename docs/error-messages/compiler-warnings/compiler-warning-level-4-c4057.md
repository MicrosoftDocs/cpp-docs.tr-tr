---
title: Derleyici Uyarısı (düzey 4) C4057
ms.date: 11/04/2016
f1_keywords:
- C4057
helpviewer_keywords:
- C4057
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
ms.openlocfilehash: d0bae91af3c2bfed97e252a74232e2a1bd778347
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225299"
---
# <a name="compiler-warning-level-4-c4057"></a>Derleyici Uyarısı (düzey 4) C4057

' operator ': ' Identifier1 ', ' identifier2 ' öğesinden biraz farklı temel türlere yöneltme

İki işaretçi ifadesi farklı temel türlere başvurur. İfadeler dönüştürme olmadan kullanılır.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. İmzalanmış ve imzasız türleri karıştırın.

1. Karıştırma **`short`** ve **`long`** türler.
