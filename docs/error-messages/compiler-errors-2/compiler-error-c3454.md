---
title: Derleyici Hatası C3454 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3454
dev_langs:
- C++
helpviewer_keywords:
- C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f85ff8c33cc43bdc1af9a3bf02d9240a0fd5e09c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098777"
---
# <a name="compiler-error-c3454"></a>Derleyici Hatası C3454

[attribute] sınıf bildiriminde kullanılamaz

Bir öznitelik için bir sınıf tanımlanmalıdır.

Daha fazla bilgi için [özniteliği](../../windows/attribute.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3454 oluşturur.

```
// C3454.cpp
// compile with: /clr /c
using namespace System;

[attribute]   // C3454
ref class Attr1;

[attribute]   // OK
ref class Attr2 {};
```