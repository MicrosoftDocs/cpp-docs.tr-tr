---
title: Derleyici Uyarısı (düzey 1) C4612 | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4612
dev_langs:
- C++
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10a0a5640386f5e5673f39d6c2c76ee18fcc7ba7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210736"
---
# <a name="compiler-warning-level-1-c4612"></a>Derleyici Uyarısı (düzey 1) C4612

> hataya dahil etmek, dosya adı

## <a name="remarks"></a>Açıklamalar

Bu uyarı oluşur **#pragma include_alias** ne zaman bir dosya adı yanlış veya eksik.

Bağımsız değişkenleri **#pragma include_alias** deyimi, teklif formu kullanabilir ("*filename*") veya açılı ayraç biçimi (\<*filename*>), ancak her ikisi gerekir aynı formu kullanın.

## <a name="example"></a>Örnek

```cpp
// C4612.cpp
// compile with: /W1 /LD
#pragma include_alias("StandardIO", <stdio.h>) // C4612
```