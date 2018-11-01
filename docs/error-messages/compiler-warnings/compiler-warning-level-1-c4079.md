---
title: Derleyici Uyarısı (düzey 1) C4079
ms.date: 11/04/2016
f1_keywords:
- C4079
helpviewer_keywords:
- C4079
ms.assetid: 549759f0-e168-47e9-8c9a-de93ac843689
ms.openlocfilehash: 8f9a9e05ab2a65ad954f9928f7b9fab0e7fee9cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564573"
---
# <a name="compiler-warning-level-1-c4079"></a>Derleyici Uyarısı (düzey 1) C4079

beklenmeyen belirteç 'belirteci

Pragmasını bağımsız değişken listesinde bir beklenmeyen ayırıcısı belirteç gerçekleşir. Pragma geri kalanı göz ardı edildi.

Aşağıdaki örnek, C4079 oluşturur:

```
// C4079.cpp
// compile with: /W1
#pragma warning(disable : 4081)
#pragma pack(c,16)   // C4079

int main() {
}
```