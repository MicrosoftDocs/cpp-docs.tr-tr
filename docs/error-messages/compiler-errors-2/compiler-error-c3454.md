---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3454'
title: Derleyici hatası C3454
ms.date: 11/04/2016
f1_keywords:
- C3454
helpviewer_keywords:
- C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
ms.openlocfilehash: 3d7905600a5d9502315689f9d25bd6d39dd80763
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315939"
---
# <a name="compiler-error-c3454"></a>Derleyici hatası C3454

sınıf bildiriminde [Attribute] kullanılamaz

Bir sınıfın bir öznitelik olması için tanımlanması gerekir.

Daha fazla bilgi için bkz. [özniteliği](../../windows/attributes/attribute.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3454 oluşturur.

```cpp
// C3454.cpp
// compile with: /clr /c
using namespace System;

[attribute]   // C3454
ref class Attr1;

[attribute]   // OK
ref class Attr2 {};
```
