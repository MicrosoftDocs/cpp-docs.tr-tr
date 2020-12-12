---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3457'
title: Derleyici hatası C3457
ms.date: 11/04/2016
f1_keywords:
- C3457
helpviewer_keywords:
- C3457
ms.assetid: 5c1e366a-fa75-4cca-b9a3-86d4ebe4090e
ms.openlocfilehash: 42e30946c57da585ed1339e49b6081372b141a2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113603"
---
# <a name="compiler-error-c3457"></a>Derleyici hatası C3457

' Attribute ': öznitelik adlandırılmamış bağımsız değişkenleri desteklemiyor

Kaynak ek açıklama öznitelikleri, CLR özel özniteliği veya derleyici özniteliklerinin aksine, yalnızca adlandırılmış bağımsız değişkenleri destekler.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3457 oluşturur.

```
#include "SourceAnnotations.h"
[vc_attributes::Post( 1 )] int f();   // C3457
[vc_attributes::Post( Valid=vc_attributes::Yes )] int f2();   // OK
```
