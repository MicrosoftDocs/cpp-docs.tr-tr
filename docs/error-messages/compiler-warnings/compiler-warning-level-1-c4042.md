---
title: Derleyici Uyarısı (düzey 1) C4042 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4042
dev_langs:
- C++
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5bef2071cf31123b5b172df2651c0d6a6d87d4fc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067485"
---
# <a name="compiler-warning-level-1-c4042"></a>Derleyici Uyarısı (düzey 1) C4042

'identifier': hatalı depolama sınıfına sahip

Belirtilen depolama sınıfı, şu tanımlayıcıyla bu bağlamda kullanılamaz. Bunun yerine, derleyici varsayılan depolama sınıfı kullanır:

- `extern`, varsa *tanımlayıcı* bir işlevdir.

- **Otomatik**, *tanımlayıcı* biçimsel parametre veya yerel değişken.

- Hiçbir depolama sınıfı, *tanımlayıcı* genel bir değişkendir.

Bu uyarı bir depolama sınıfı dışındaki belirterek kaynaklanabilir **kaydetme** parametre bildirimi.

Aşağıdaki örnek C4042 oluşturur

```
// C4042.cpp
// compile with: /W1 /LD
int func2( __declspec( thread ) int tls_i )    // C4042
// try the following line instead
// int func2( int tls_i )
{
   return tls_i;
}
```