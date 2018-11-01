---
title: Derleyici Uyarısı (düzey 4) C4207
ms.date: 11/04/2016
f1_keywords:
- C4207
helpviewer_keywords:
- C4207
ms.assetid: f4e09e3e-ac87-4489-8e3f-c8f76b82e721
ms.openlocfilehash: 44f49705bf197d7a42b80e50983e47a4c0ce7bed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541134"
---
# <a name="compiler-warning-level-4-c4207"></a>Derleyici Uyarısı (düzey 4) C4207

Standart olmayan uzantı kullanıldı: uzatılmış Başlatıcı biçimi

Boyutsuz bir dizi Microsoft Uzatmaları (/Ze) ile başlatabilir `char` kullanarak küme ayraçları içinde bir dize.

## <a name="example"></a>Örnek

```
// C4207.c
// compile with: /W4
char c[] = { 'a', 'b', "cdefg" }; // C4207

int main()
{
}
```

Bu tür başlatmalar ANSI Uyumluluğu altında geçersiz ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).