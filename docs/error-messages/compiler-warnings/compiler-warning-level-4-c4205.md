---
title: Derleyici Uyarısı (düzey 4) C4205
ms.date: 11/04/2016
f1_keywords:
- C4205
helpviewer_keywords:
- C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
ms.openlocfilehash: 7b6e273de196f6708b92774ce5b436dc810ad3a5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161445"
---
# <a name="compiler-warning-level-4-c4205"></a>Derleyici Uyarısı (düzey 4) C4205

Standart olmayan uzantı kullanıldı: işlev kapsamında statik işlev bildirimi

Microsoft uzantıları (/Ze) ile, **statik** işlevler başka bir işlev içinde bildirilemez. İşleve genel kapsam verildi.

## <a name="example"></a>Örnek

```c
// C4205.c
// compile with: /W4
void func1()
{
   static int func2();  // C4205
};

int main()
{
}
```

Bu tür başlatmalar, ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) altında geçersizdir.
