---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4032'
title: Derleyici Uyarısı (düzey 4) C4032
ms.date: 11/04/2016
f1_keywords:
- C4032
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
ms.openlocfilehash: 1c150bff398bbd2d6e5f1a8d21211f4c6b4cb6bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262106"
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
