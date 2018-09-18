---
title: Derleyici Hatası C3749 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3749
dev_langs:
- C++
helpviewer_keywords:
- C3749
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a4151d712c12cb34785c3f4ab77c76cdd78d4830
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024092"
---
# <a name="compiler-error-c3749"></a>Derleyici Hatası C3749

'attribute': özel bir öznitelik, bir işlev içinde kullanılamaz

Özel bir öznitelik, bir işlev içinde kullanılamaz. Özel öznitelikler hakkında daha fazla bilgi için Ek Yardım konusuna [özniteliği](../../windows/attribute.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3749 oluşturur:

```
// C3749a.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::All)]
public ref struct ABC : public Attribute {
   ABC() {}
};

void f1() { [ABC]; };  // C3749
```
