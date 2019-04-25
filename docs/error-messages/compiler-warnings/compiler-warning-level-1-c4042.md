---
title: Derleyici Uyarısı (düzey 1) C4042
ms.date: 11/04/2016
f1_keywords:
- C4042
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
ms.openlocfilehash: 99f4f45aad82aa9898dad4cffb60b8e3311ddc9f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152149"
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