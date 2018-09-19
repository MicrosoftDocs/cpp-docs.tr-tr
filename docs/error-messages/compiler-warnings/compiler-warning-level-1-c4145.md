---
title: Derleyici Uyarısı (düzey 1) C4145 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4145
dev_langs:
- C++
helpviewer_keywords:
- C4145
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65d041b9fdb7fb4b01abfadf5010444b0e406220
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100696"
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