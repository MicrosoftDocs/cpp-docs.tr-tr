---
title: Derleyici Uyarısı (düzey 1) C4010 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4010
dev_langs:
- C++
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52449689d329cee45cc69b63c315ce9335befbe0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073112"
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