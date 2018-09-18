---
title: Derleyici Uyarısı (düzey 1) C4138 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4138
dev_langs:
- C++
helpviewer_keywords:
- C4138
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d2e637c73482b1a59034d6a269ea2240445bdef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046920"
---
# <a name="compiler-warning-level-1-c4138"></a>Derleyici Uyarısı (düzey 1) C4138

' * /' açıklama dışında bulundu

Kapanış açıklama sınırlayıcısı bir açılış bir açıklama sınırlayıcısı gelmelidir değil. Yıldız arasında bir boşluk derleyici varsayar (<strong>\**</strong>) ve eğik çizgi (/).

## <a name="example"></a>Örnek

```
// C4138a.cpp
// compile with: /W1
int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning
int main()
{
}
```

Bu uyarı açıklamalar iç içe deneyerek neden olabilir.

Bu uyarı açıklama içeren, kod içine kod bölümlerini çıkarırsanız çözümlenebilir bir **#if / #endif** blok ve denetleme ifadesiyle sıfır olarak ayarlayın:

```
// C4138b.cpp
// compile with: /W1
#if 0
int my_variable;   /* Declaration currently not needed */
#endif
int main()
{
}
```