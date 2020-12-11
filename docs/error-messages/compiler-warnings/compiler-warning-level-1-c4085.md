---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4085'
title: Derleyici Uyarısı (düzey 1) C4085
ms.date: 11/04/2016
f1_keywords:
- C4085
helpviewer_keywords:
- C4085
ms.assetid: 2bc6eb25-058f-4597-b351-fd69587b5170
ms.openlocfilehash: 81a752e1497f0b65e99de53b14879220b58678ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155442"
---
# <a name="compiler-warning-level-1-c4085"></a>Derleyici Uyarısı (düzey 1) C4085

pragma parametresinin ' on ' veya ' off ' olması bekleniyor

Pragma bir **Açık** veya **kapalı** parametresi gerektirir. Pragma yoksayıldı.

Aşağıdaki örnek C4085 oluşturur:

```cpp
// C4085.cpp
// compile with: /W1 /LD
#pragma optimize( "t", maybe )  // C4085
```
