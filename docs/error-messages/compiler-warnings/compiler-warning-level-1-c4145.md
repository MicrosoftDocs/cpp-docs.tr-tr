---
title: Derleyici Uyarısı (düzey 1) C4145
ms.date: 11/04/2016
f1_keywords:
- C4145
helpviewer_keywords:
- C4145
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
ms.openlocfilehash: 10c0211bfda354a00e05cba3131d047fce843df8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553796"
---
# <a name="compiler-warning-level-1-c4145"></a>Derleyici Uyarısı (düzey 1) C4145

'İfade1': switch ifadesi; olarak ilişkisel ifade kullanıldı 'expression2' ile karıştırılmış

A `switch` deyim için bir Boolean değeri ile sonuçlanır, Denetim ifadesi olarak ilişkisel ifade kullanır **çalışması** deyimleri. Şunu mu demek istediniz *expression2*?

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4145 oluşturur:

```
// C4145.cpp
// compile with: /W1
int main() {
   int i = 0;
   switch(i == 1) {   // C4145, use i instead of i == 1 to resolve
      case 1:
         break;
      default:
         break;
   }
}
```