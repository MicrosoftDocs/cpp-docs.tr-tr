---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2137'
title: Derleyici hatası C2137
ms.date: 11/04/2016
f1_keywords:
- C2137
helpviewer_keywords:
- C2137
ms.assetid: 984687ee-7766-4f6b-ae15-0c9a010e2366
ms.openlocfilehash: 053c933b3ee650d1d49c230d9bfc23c656f9a709
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323083"
---
# <a name="compiler-error-c2137"></a>Derleyici hatası C2137

boş karakter sabiti

Boş karakter sabitine (' ') izin verilmiyor.

Aşağıdaki örnek C2137 oluşturur:

```cpp
// C2137.cpp
int main() {
   char c = '';   // C2137
   char d = ' ';   // OK
}
```
