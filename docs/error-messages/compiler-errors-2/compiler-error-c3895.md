---
title: Derleyici Hatası C3895 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3895
dev_langs:
- C++
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a722ac9091e47db95bcc3e2d81293bf662d0c99
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033296"
---
# <a name="compiler-error-c3895"></a>Derleyici Hatası C3895

'var': tür veri üyeleri 'volatile' olamaz

Belirli türde bir örnek için veri üye [değişmez değer](../../windows/literal-cpp-component-extensions.md) veya [initonly](../../dotnet/initonly-cpp-cli.md), olamaz [geçici](../../cpp/volatile-cpp.md).

Aşağıdaki örnek, C3895 oluşturur:

```
// C3895.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   volatile int data_var2;   // C3895
};
```