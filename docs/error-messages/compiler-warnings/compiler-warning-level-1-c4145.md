---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4145'
title: Derleyici Uyarısı (düzey 1) C4145
ms.date: 11/04/2016
f1_keywords:
- C4145
helpviewer_keywords:
- C4145
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
ms.openlocfilehash: 2eaafd131e7dcfba7b94fbc84e5c2b9da2dfa89e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136259"
---
# <a name="compiler-warning-level-1-c4145"></a>Derleyici Uyarısı (düzey 1) C4145

' İfade1 ': switch ifadesi olarak ilişkisel ifade; ' İfade2 ' ile olası karışıklık

Deyim, bir **`switch`** ilişkisel ifadeyi denetim ifadesi olarak kullanır, bu da deyimler için bir Boolean değer ile sonuçlanır **`case`** . *İfade2*' i mi demek istediniz?

## <a name="example"></a>Örnek

Aşağıdaki örnek C4145 oluşturur:

```cpp
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
