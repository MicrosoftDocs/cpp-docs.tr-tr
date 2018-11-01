---
title: Derleyici Uyarısı (Düzey 2) C4094
ms.date: 11/04/2016
f1_keywords:
- C4094
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
ms.openlocfilehash: 73805afc897d14c6d2cc87490dfa0769a8de5193
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488406"
---
# <a name="compiler-warning-level-2-c4094"></a>Derleyici Uyarısı (Düzey 2) C4094

Etiketlenmemiş 'belirteci' hiçbir simge bildirimi yapmadı

Derleyici bir etiketlenmemiş yapı, birlik veya kullanarak boş bir bildirim algıladı. Bildirim yok sayılır.

## <a name="example"></a>Örnek

```
// C4094.cpp
// compile with: /W2
struct
{
};   // C4094

int main()
{
}
```

Bu durum, ANSI Uyumluluğu altında bir hata oluşturur ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).