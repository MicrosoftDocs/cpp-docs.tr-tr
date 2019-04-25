---
title: Derleyici Uyarısı (düzey 1) C4076
ms.date: 11/04/2016
f1_keywords:
- C4076
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
ms.openlocfilehash: 3a56e58d9bec1034a55f4e588dbddd0dba03f348
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208033"
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