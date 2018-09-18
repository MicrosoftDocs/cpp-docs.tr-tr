---
title: Derleyici Uyarısı (düzey 1) C4076 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4076
dev_langs:
- C++
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2f0a8066b8e79b75f3d5ede37f4e5ad6b61db168
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037885"
---
# <a name="compiler-warning-level-1-c4076"></a>Derleyici Uyarısı (düzey 1) C4076

> '*tür değiştiricisi*': tür ile kullanılabilir değil '*typename*'

## <a name="remarks"></a>Açıklamalar

Bir tür değiştiricisi olup **imzalı** veya **işaretsiz**, tamsayı olmayan türü ile kullanılamaz. *tür değiştiricisi* göz ardı edilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4076 oluşturur; Bunu düzeltmek için kaldırma **işaretsiz** tür değiştiricisi:

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```