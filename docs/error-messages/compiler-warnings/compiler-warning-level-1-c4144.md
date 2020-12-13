---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4144'
title: Derleyici Uyarısı (düzey 1) C4144
ms.date: 11/04/2016
f1_keywords:
- C4144
helpviewer_keywords:
- C4144
ms.assetid: a37b445d-dbc6-43b4-8d95-ffd0e4225464
ms.openlocfilehash: 11f276d4790c11654655fea7cf814dfb30a6787b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136311"
---
# <a name="compiler-warning-level-1-c4144"></a>Derleyici Uyarısı (düzey 1) C4144

' expression ': switch ifadesi olarak ilişkisel ifade

Belirtilen ilişkisel ifade bir [Switch](../../cpp/switch-statement-cpp.md) deyiminin denetim ifadesi olarak kullanıldı. İlişkili Case deyimleri, Boole değerleri olarak sunulacaktır. Aşağıdaki örnek C4144 oluşturur:

```cpp
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
