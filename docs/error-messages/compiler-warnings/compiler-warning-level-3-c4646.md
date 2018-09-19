---
title: Derleyici Uyarısı (Düzey 3) C4646 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4646
dev_langs:
- C++
helpviewer_keywords:
- C4646
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ad9a96aaf15294a1404de54f276eb5309a09357
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086791"
---
# <a name="compiler-warning-level-3-c4646"></a>Derleyici Uyarısı (Düzey 3) C4646

__declspec(noreturn) ile bildirilen işlevde void olmayan dönüş türüne sahip.

Bir işlev ile işaretlenen [noreturn](../../cpp/noreturn.md) `__declspec` değiştiricisi olmalıdır bir [void](../../cpp/void-cpp.md) dönüş türü.

Aşağıdaki örnek, C4646 oluşturur:

```
// C4646.cpp
// compile with: /W3 /WX
int __declspec(noreturn) TestFunction()
{   // C4646  make return type void
}
```