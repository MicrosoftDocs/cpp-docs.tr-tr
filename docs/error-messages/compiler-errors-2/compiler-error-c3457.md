---
title: Derleyici Hatası C3457
ms.date: 11/04/2016
f1_keywords:
- C3457
helpviewer_keywords:
- C3457
ms.assetid: 5c1e366a-fa75-4cca-b9a3-86d4ebe4090e
ms.openlocfilehash: 813b1c085cb0464880cb400b6200f9574220bd71
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566120"
---
# <a name="compiler-error-c3457"></a>Derleyici Hatası C3457

'attribute': öznitelik adsız bağımsız değişkenleri desteklemiyor

CLR özel öznitelik veya derleyici öznitelikleri farklı kaynak ek açıklama öznitelikleri yalnızca adlandırılmış bağımsız değişkenler de destekler.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3457 oluşturur.

```
#include "SourceAnnotations.h"
[vc_attributes::Post( 1 )] int f();   // C3457
[vc_attributes::Post( Valid=vc_attributes::Yes )] int f2();   // OK
```