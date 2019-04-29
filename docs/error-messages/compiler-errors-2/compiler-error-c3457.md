---
title: Derleyici Hatası C3457
ms.date: 11/04/2016
f1_keywords:
- C3457
helpviewer_keywords:
- C3457
ms.assetid: 5c1e366a-fa75-4cca-b9a3-86d4ebe4090e
ms.openlocfilehash: 813b1c085cb0464880cb400b6200f9574220bd71
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363732"
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