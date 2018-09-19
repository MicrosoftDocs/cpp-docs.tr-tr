---
title: Derleyici Uyarısı (düzey 4) C4032 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4032
dev_langs:
- C++
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 608c99c81fac0088a4d1d8bb8a6d3b0b61c7af50
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086049"
---
# <a name="compiler-warning-level-4-c4032"></a>Derleyici Uyarısı (düzey 4) C4032

'number' biçimsel parametresi yükseltildiğinde farklı türe sahip

Parametre türü aracılığıyla varsayılan promosyonlar, bir önceki bildirimde türüyle uyumlu değil.

Bu bir hatadır, ANSI C ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) ve Microsoft Uzatmaları (/Ze) altında bir uyarı.

## <a name="example"></a>Örnek

```
// C4032.c
// compile with: /W4
void func();
void func(char);   // C4032, char promotes to int

int main()
{
}
```