---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4079'
title: Derleyici Uyarısı (düzey 1) C4079
ms.date: 11/04/2016
f1_keywords:
- C4079
helpviewer_keywords:
- C4079
ms.assetid: 549759f0-e168-47e9-8c9a-de93ac843689
ms.openlocfilehash: d666d6d1272c1a131af5aa6b4e9248398e270758
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228670"
---
# <a name="compiler-warning-level-1-c4079"></a>Derleyici Uyarısı (düzey 1) C4079

beklenmeyen belirteç ' token '

Bir pragma bağımsız değişkeni listesinde beklenmeyen bir ayırıcı belirteci oluşur. Pragma 'un geri kalanı yoksayıldı.

Aşağıdaki örnek C4079 oluşturur:

```cpp
// C4079.cpp
// compile with: /W1
#pragma warning(disable : 4081)
#pragma pack(c,16)   // C4079

int main() {
}
```
