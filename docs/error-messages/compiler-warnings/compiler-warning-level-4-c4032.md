---
title: Derleyici Uyarısı (düzey 4) C4032
ms.date: 11/04/2016
f1_keywords:
- C4032
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
ms.openlocfilehash: 84bfef28de2899a216616a6a5d9fb15422f2afec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185418"
---
# <a name="compiler-warning-level-4-c4032"></a>Derleyici Uyarısı (düzey 4) C4032

' number ' biçimsel parametresi yükseltildiğinde farklı türe sahip

Parametre türü, bir önceki bildirimde bulunan türü olan varsayılan yükseltmeler aracılığıyla uyumlu değildir.

Bu, ANSI C 'de ([/za](../../build/reference/za-ze-disable-language-extensions.md)) oluşan bir hatadır ve Microsoft uzantıları (/Ze) altında bir uyarıdır.

## <a name="example"></a>Örnek

```c
// C4032.c
// compile with: /W4
void func();
void func(char);   // C4032, char promotes to int

int main()
{
}
```
