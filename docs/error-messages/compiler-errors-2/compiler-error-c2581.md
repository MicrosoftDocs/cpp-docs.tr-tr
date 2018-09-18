---
title: Derleyici Hatası C2581 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2581
dev_langs:
- C++
helpviewer_keywords:
- C2581
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0763db5d6284942ff3f8104eaabf705305f86e1f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018672"
---
# <a name="compiler-error-c2581"></a>Derleyici Hatası C2581

'type': statik ' operator =' işlevi geçersizdir

Atama (`=`) işleci olarak bildirilen yanlış `static`. Atama İşleçleri olamaz `static`. Daha fazla bilgi için [kullanıcı tanımlı işleçler (C + +/ CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2581 oluşturur.

```
// C2581.cpp
// compile with: /clr /c
ref struct Y {
   static Y ^ operator = (Y^ me, int i);   // C2581
   Y^ operator =(int i);   // OK
};
```