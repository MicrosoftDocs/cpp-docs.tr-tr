---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4074'
title: Derleyici Uyarısı (düzey 1) C4074
ms.date: 11/04/2016
f1_keywords:
- C4074
helpviewer_keywords:
- C4074
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
ms.openlocfilehash: cb04b242415769e995a46a9cdf3e0dff827ec1db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267631"
---
# <a name="compiler-warning-level-1-c4074"></a>Derleyici Uyarısı (düzey 1) C4074

derleyici için ayrılmış başlatma alanına başlatıcılar yerleştirildi

[#Pragma init_seg](../../preprocessor/init-seg.md)tarafından belirtilen derleyici başlatma alanı Microsoft tarafından ayrılmıştır. Bu alandaki kod, C çalışma zamanı kitaplığının başlatılmasından önce yürütülebilir.

Aşağıdaki örnek C4074 oluşturur:

```cpp
// C4074.cpp
// compile with: /W1
#pragma init_seg( compiler )   // C4074

// try this line to resolve the warning
// #pragma init_seg(user)

int main() {
}
```
