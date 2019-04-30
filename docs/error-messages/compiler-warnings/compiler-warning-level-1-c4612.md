---
title: Derleyici Uyarısı (düzey 1) C4612
ms.date: 08/27/2018
f1_keywords:
- C4612
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
ms.openlocfilehash: ed5458fc52c1c9c9f12187095e4658204613d1a1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406372"
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