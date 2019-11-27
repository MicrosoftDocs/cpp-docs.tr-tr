---
title: Derleyici Uyarısı (düzey 4) C4207
ms.date: 11/04/2016
f1_keywords:
- C4207
helpviewer_keywords:
- C4207
ms.assetid: f4e09e3e-ac87-4489-8e3f-c8f76b82e721
ms.openlocfilehash: bd18964f8969bc75967de435e2ca3099b12213e0
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541874"
---
# <a name="compiler-warning-level-4-c4207"></a>Derleyici Uyarısı (düzey 4) C4207

Standart olmayan uzantı kullanıldı: genişletilmiş Başlatıcı formu

Microsoft uzantıları (/Ze) ile, parantez içinde bir dize kullanarak, boyutlandırılmış bir `char` dizisi başlatabilirsiniz.

## <a name="example"></a>Örnek

```c
// C4207.c
// compile with: /W4
char c[] = { 'a', 'b', "cdefg" }; // C4207

int main()
{
}
```

Bu tür başlatmalar, ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) altında geçersizdir.