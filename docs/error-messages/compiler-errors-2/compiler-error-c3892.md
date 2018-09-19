---
title: Derleyici Hatası C3892 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3892
dev_langs:
- C++
helpviewer_keywords:
- C3892
ms.assetid: 83fff42c-ea48-442f-bc2e-b33a6b99d890
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b9542f02c2ac72d9c5b4625c2b8fe6f7ba0169b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136094"
---
# <a name="compiler-error-c3892"></a>Derleyici Hatası C3892

'var': const olan bir değişkene atanamıyor

Const bir değişken bildirilir ve başlatılır sonra değiştirilemez.

Aşağıdaki örnek, C3892 oluşturur:

```
// C3892.cpp
// compile with: /clr
ref struct Y1 {
   static const int staticConst = 9;
};

int main() {
   Y1::staticConst = 0;   // C3892
}
```