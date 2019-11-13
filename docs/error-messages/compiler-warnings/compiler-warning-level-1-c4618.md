---
title: Derleyici Uyarısı (düzey 1) C4618
ms.date: 11/04/2016
f1_keywords:
- C4618
helpviewer_keywords:
- C4618
ms.assetid: 6ff10d0a-6d5b-4373-8196-1d57bb6b1611
ms.openlocfilehash: fa9fc7d4a86ee686a9cd5d8d21412bd3346bcd80
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052575"
---
# <a name="compiler-warning-level-1-c4618"></a>Derleyici Uyarısı (düzey 1) C4618

pragma parametreleri boş bir dize içeriyordu; pragma yoksayıldı

Bir **#pragma**bağımsız değişken olarak null bir dize verildi.

Pragma bağımsız değişken olmadan işlendi.

Aşağıdaki örnek C4618 oluşturur:

```cpp
// C4618.cpp
// compile with: /W1 /LD
#pragma code_seg("")   // C4618
```