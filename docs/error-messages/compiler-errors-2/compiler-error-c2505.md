---
title: Derleyici Hatası C2505 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2505
dev_langs:
- C++
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6bd22d7a25311b14ed599c6693bfa0c7913b304
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109177"
---
# <a name="compiler-error-c2505"></a>Derleyici Hatası C2505

'symbol': '__declspec(modifer)', yalnızca bildirimlerine veya tanımlarına genel nesnelerin veya statik veri üyeleri uygulanabilir

A `__declspec` yalnızca genel kapsamda kullanılmak üzere tasarlanmış değiştiricisi, bir işlevde kullanıldı.

Daha fazla bilgi için [appdomain](../../cpp/appdomain.md) ve [işlem](../../cpp/process.md).

Aşağıdaki örnek, C2505 oluşturur:

```
// C2505.cpp
// compile with: /clr

// OK
__declspec(process) int ii;
__declspec(appdomain) int jj;

int main() {
   __declspec(process) int i;   // C2505
   __declspec(appdomain) int j;   // C2505
}
```