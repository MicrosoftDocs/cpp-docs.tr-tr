---
title: Derleyici Uyarısı (düzey 2) C4307
ms.date: 11/04/2016
f1_keywords:
- C4307
helpviewer_keywords:
- C4307
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
ms.openlocfilehash: b5566bca22c328328a49e82268b96e8ec0fedc95
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052063"
---
# <a name="compiler-warning-level-2-c4307"></a>Derleyici Uyarısı (düzey 2) C4307

' operator ': tamsayı sabiti taştı

İşleci, bir tamsayı sabiti için ayrılan alanı kaplamasına neden olan bir ifadede kullanılır. Sabit için daha büyük bir tür kullanmanız gerekebilir. İmzalanan tamsayı, işareti temsil etmek için bir **bit kullandığından,** **işaretli bir int** bir `unsigned int` daha küçük bir değer tutar.

Aşağıdaki örnek C4307 oluşturur:

```cpp
// C4307.cpp
// compile with: /W2
int i = 2000000000 + 2000000000;   // C4307
int j = (unsigned)2000000000 + 2000000000;   // OK

int main()
{
}
```