---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4619'
title: Derleyici Uyarısı (düzey 3) C4619
ms.date: 11/04/2016
f1_keywords:
- C4619
helpviewer_keywords:
- C4619
ms.assetid: 701fea21-01aa-4bea-93d4-1cb8824170b0
ms.openlocfilehash: c108e4d1a0845cc6629a36307c33fc8342cadd67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337260"
---
# <a name="compiler-warning-level-3-c4619"></a>Derleyici Uyarısı (düzey 3) C4619

\#pragma warning: uyarı numarası ' number ' yok

Varolmayan bir uyarıyı devre dışı bırakmak için bir girişimde bulunuldu.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki örnek C4619 oluşturur:

```cpp
// C4619.cpp
// compile with: /W3 /c
#pragma warning(default : 4619)
#pragma warning(disable : 4354)   // C4619, C4354 does not exist
```
