---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2130'
title: Derleyici hatası C2130
ms.date: 11/04/2016
f1_keywords:
- C2130
helpviewer_keywords:
- C2130
ms.assetid: c6fd5a7e-8f28-4f67-99d1-95a13b0dff90
ms.openlocfilehash: 78e7b756d5902562c6093e3f26f9934e87e732ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323187"
---
# <a name="compiler-error-c2130"></a>Derleyici hatası C2130

\#satır, dosya adını içeren bir dize bekliyordu, ' token ' bulundu

[#Line](../../preprocessor/hash-line-directive-c-cpp.md) aşağıdaki isteğe bağlı dosya adı belirteci `linenumber` bir dize olmalıdır.

Aşağıdaki örnek C2130 oluşturur:

```cpp
// C2130.cpp
int main() {
   #line 1000 test   // C2130
   #line 1000 "test"   // OK
}
```
