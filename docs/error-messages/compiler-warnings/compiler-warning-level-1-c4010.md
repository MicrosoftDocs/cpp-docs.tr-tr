---
title: Derleyici Uyarısı (düzey 1) C4010
ms.date: 11/04/2016
f1_keywords:
- C4010
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
ms.openlocfilehash: 40c6724daf17c1c0b546bb7bc64bb704f732e8d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441255"
---
# <a name="compiler-warning-level-1-c4010"></a>Derleyici Uyarısı (düzey 1) C4010

tek satır açıklama satır devam ettirme karakteri içeriyor

Tarafından sunulan bir tek satır açıklama / /, ters eğik çizgi içerir (\\) satır devam ettirme karakteri olarak görev yapar. Derleyici, bir devamlılık sonraki satırını göz önünde bulundurur ve açıklama olarak değerlendirir.

Bazı sözdizimi düzenleyicileri devamlılık karakter olarak bir açıklama satırı göstermez yönelik. Sözdizimi renklendirme bu uyarıyı neden olan tüm satırları yoksay.

Aşağıdaki örnek, C4010 oluşturur:

```
// C4010.cpp
// compile with: /WX
int main() {
   // the next line is also a comment because of the backslash \
   int a = 3; // C4010
   a++;
}
```