---
title: Derleyici Uyarısı (düzey 1) C4077
ms.date: 11/04/2016
f1_keywords:
- C4077
helpviewer_keywords:
- C4077
ms.assetid: c2d28805-b33f-41ad-afba-33b3f788c649
ms.openlocfilehash: 90797463595cda07c5b37e1530964b23c656b027
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200306"
---
# <a name="compiler-warning-level-1-c4077"></a>Derleyici Uyarısı (düzey 1) C4077

bilinmeyen check_stack seçeneği

**Check_stack** pragma 'un eski biçimi bilinmeyen bir bağımsız değişkenle birlikte kullanılır. Bağımsız değişken `+`, `-`, `(on)`, `(off)`veya boş olmalıdır.

Derleyici pragmayı yoksayar ve yığın denetimini değiştirmeden bırakır.

## <a name="example"></a>Örnek

```cpp
// C4077.cpp
// compile with: /W1 /LD
#pragma check_stack yes // C4077
#pragma check_stack +    // Correct old form
#pragma check_stack (on) // Correct new form
```
