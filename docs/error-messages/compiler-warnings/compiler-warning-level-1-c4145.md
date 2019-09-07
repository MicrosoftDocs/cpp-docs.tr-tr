---
title: Derleyici Uyarısı (düzey 1) C4145
ms.date: 11/04/2016
f1_keywords:
- C4145
helpviewer_keywords:
- C4145
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
ms.openlocfilehash: 10c0211bfda354a00e05cba3131d047fce843df8
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741111"
---
# <a name="compiler-warning-level-1-c4145"></a>Derleyici Uyarısı (düzey 1) C4145

' İfade1 ': switch ifadesi olarak ilişkisel ifade; ' İfade2 ' ile olası karışıklık

Bir `switch` deyim, bir ilişkisel ifadeyi denetim ifadesi olarak kullanır, bu da **Case** deyimlerinin Boole değeriyle sonuçlanır. *İfade2*' i mi demek istediniz?

## <a name="example"></a>Örnek

Aşağıdaki örnek C4145 oluşturur:

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