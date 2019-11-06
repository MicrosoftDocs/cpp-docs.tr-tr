---
title: Derleyici Uyarısı (düzey 1) C4237
ms.date: 11/04/2016
f1_keywords:
- C4237
helpviewer_keywords:
- C4237
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
ms.openlocfilehash: e53c4632f8bfc9764f6ab1e124582bda273d945e
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624898"
---
# <a name="compiler-warning-level-1-c4237"></a>Derleyici Uyarısı (düzey 1) C4237

' anahtar sözcüğü ' anahtar sözcüğü henüz desteklenmiyor, ancak gelecekte kullanılmak üzere ayrıldı

C++ Belirtimde bir anahtar sözcük Microsoft C++ derleyicisinde uygulanmıyor, ancak anahtar sözcüğü Kullanıcı tanımlı bir sembol olarak kullanılamaz.

Aşağıdaki örnek C4237 oluşturur:

```cpp
// C4237.cpp
// compile with: /W1 /c
int export;   // C4237
```