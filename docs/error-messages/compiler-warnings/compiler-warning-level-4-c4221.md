---
title: Derleyici Uyarısı (düzey 4) C4221
ms.date: 11/04/2016
f1_keywords:
- C4221
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
ms.openlocfilehash: f552a5d76d1a778cdf72cbe079138f609350ffb1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401104"
---
# <a name="compiler-warning-level-4-c4221"></a>Derleyici Uyarısı (düzey 4) C4221

Standart olmayan uzantı kullanıldı: 'identifier': otomatik değişkeninin adresi kullanılarak başlatılamıyor

Varsayılan Microsoft Uzantıları (/Ze) ile bir toplama türünü başlatabilirsiniz (**dizi**, `struct`, veya **birleşim**) (otomatik) yerel değişkenin adresi.

## <a name="example"></a>Örnek

```
// C4221.c
// compile with: /W4
struct S
{
   int *i;
};

void func()
{
   int j;
   struct S s1 = { &j };   // C4221
}

int main()
{
}
```

Bu tür başlatmalar ANSI Uyumluluğu altında geçersiz ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).