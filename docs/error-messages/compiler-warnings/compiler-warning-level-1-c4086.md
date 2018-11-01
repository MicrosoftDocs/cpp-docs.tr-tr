---
title: Derleyici Uyarısı (düzey 1) C4086
ms.date: 11/04/2016
f1_keywords:
- C4086
helpviewer_keywords:
- C4086
ms.assetid: 9248831b-22bf-47af-8684-bfadb17e94fc
ms.openlocfilehash: 77a3675bed99333031131573201d4be38240f488
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451539"
---
# <a name="compiler-warning-level-1-c4086"></a>Derleyici Uyarısı (düzey 1) C4086

Beklenen pragma parametresinin '1', '2', '4', ' 8' veya ' 16' olması

Pragma parametresinin (1, 2, 4, 8 veya 16) gerekli değer yok.

## <a name="example"></a>Örnek

```
// C4086.cpp
// compile with: /W1 /LD
#pragma pack( 3 ) // C4086
```