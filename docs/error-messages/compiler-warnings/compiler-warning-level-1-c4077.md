---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4077'
title: Derleyici Uyarısı (düzey 1) C4077
ms.date: 11/04/2016
f1_keywords:
- C4077
helpviewer_keywords:
- C4077
ms.assetid: c2d28805-b33f-41ad-afba-33b3f788c649
ms.openlocfilehash: 96e611db6d36dfa62d96561deb2f4c4d57638c72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208716"
---
# <a name="compiler-warning-level-1-c4077"></a>Derleyici Uyarısı (düzey 1) C4077

bilinmeyen check_stack seçeneği

**Check_stack** pragma 'un eski biçimi bilinmeyen bir bağımsız değişkenle birlikte kullanılır. Bağımsız değişken,, `+` , `-` `(on)` `(off)` veya boş olmalıdır.

Derleyici pragmayı yoksayar ve yığın denetimini değiştirmeden bırakır.

## <a name="example"></a>Örnek

```cpp
// C4077.cpp
// compile with: /W1 /LD
#pragma check_stack yes // C4077
#pragma check_stack +    // Correct old form
#pragma check_stack (on) // Correct new form
```
