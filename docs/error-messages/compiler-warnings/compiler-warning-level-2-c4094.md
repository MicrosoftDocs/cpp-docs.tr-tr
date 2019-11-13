---
title: Derleyici Uyarısı (düzey 2) C4094
ms.date: 11/04/2016
f1_keywords:
- C4094
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
ms.openlocfilehash: c293522e5d60d0edb4cc2da289e0ece71f89329f
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052208"
---
# <a name="compiler-warning-level-2-c4094"></a>Derleyici Uyarısı (düzey 2) C4094

etiketlenmemiş ' token ' hiç sembol bildirmişti

Derleyici etiketsiz bir yapı, birleşim veya sınıf kullanarak boş bir bildirim algıladı. Bildirim yok sayılır.

## <a name="example"></a>Örnek

```cpp
// C4094.cpp
// compile with: /W2
struct
{
};   // C4094

int main()
{
}
```

Bu durum, ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) altında bir hata üretir.