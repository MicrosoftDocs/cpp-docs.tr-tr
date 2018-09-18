---
title: Derleyici Hatası C3094 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3094
dev_langs:
- C++
helpviewer_keywords:
- C3094
ms.assetid: 10da9b7c-e72d-4013-9925-c83e1bb142db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6c114a81904962a6986b33b3c634ed6611d79179
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016696"
---
# <a name="compiler-error-c3094"></a>Derleyici Hatası C3094

'attribute': anonim kullanım izin verilmiyor

Bir özniteliğin doğru kapsama.  Daha fazla bilgi için [kullanıcı tanımlı öznitelikler](../../windows/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3094 oluşturur.

```
// C3094.cpp
// compile with: /clr /c
using namespace System;
[AttributeUsage(AttributeTargets::Class)]
public ref class AAttribute : Attribute {};

[A];   // C3094

// OK
[A]
ref class x{};
```