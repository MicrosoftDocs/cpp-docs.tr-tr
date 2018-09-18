---
title: Derleyici Uyarısı (düzey 1) C4144 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4144
dev_langs:
- C++
helpviewer_keywords:
- C4144
ms.assetid: a37b445d-dbc6-43b4-8d95-ffd0e4225464
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba9c1210247ad537f8fa1224c30b1c88d9c6b721
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109671"
---
# <a name="compiler-warning-level-1-c4144"></a>Derleyici Uyarısı (düzey 1) C4144

'expression': switch ifadesi olarak ilişkisel ifade kullanıldı

Belirtilen ilişkisel ifade denetim ifadesi kullanılan bir [geçiş](../../cpp/switch-statement-cpp.md) deyimi. Boole değerleri ilişkili case deyimleri sunulacaktır. Aşağıdaki örnek, C4144 oluşturur:

```
// C4144.cpp
// compile with: /W1
int main()
{
   int i = 0;
   switch(!i) {   // C4144, remove the ! to resolve
      case 1:
         break;
      default:
         break;
   }
}
```