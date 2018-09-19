---
title: Derleyici Uyarısı (düzey 1) C4581 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4581
dev_langs:
- C++
helpviewer_keywords:
- C4581
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 586283e41fb38baae828bf5a4380ec2afe323ecb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116054"
---
# <a name="compiler-warning-level-1-c4581"></a>Derleyici Uyarısı (düzey 1) C4581

kullanımdan kalkan davranış: '"string1" ' yerine 'dize2' özniteliği işlemek için

Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucu olarak oluşturulan: Visual C++ öznitelikleri için parametre.

Önceki sürümlerde, öznitelik değerleri tırnak işaretleri içine alınmış olup olmadığını kabul edildi. Değeri bir sabit listesi varsa, onu tırnak içine alınmalıdır değil.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4581 oluşturur.

```
// C4581.cpp
// compile with: /c /W1
#include "unknwn.h"
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI : IUnknown {};

[coclass, uuid(12345678-1111-2222-3333-123456789012), threading("free")]   // C4581
// try the following line instead
// [coclass, uuid(12345678-1111-2222-3333-123456789012), threading(free)]
class CSample : public IMyI {};
```