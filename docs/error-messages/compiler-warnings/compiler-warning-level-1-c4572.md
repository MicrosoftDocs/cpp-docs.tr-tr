---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4572'
title: Derleyici Uyarısı (düzey 1) C4572
ms.date: 11/04/2016
f1_keywords:
- C4572
helpviewer_keywords:
- C4572
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
ms.openlocfilehash: ab447bc7ef5d702599b1583ae94ac0fa94d29a14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332229"
---
# <a name="compiler-warning-level-1-c4572"></a>Derleyici Uyarısı (düzey 1) C4572

[ParamArray] özniteliği/clr altında kullanım dışıdır, '... ' kullanın yerine

Değişken bağımsız değişken listesinin belirtilmesine yönelik eski bir stil kullanıldı. CLR için derlerken yerine üç nokta söz dizimini kullanın <xref:System.ParamArrayAttribute> . Daha fazla bilgi için bkz. [değişken bağımsız değişken listeleri (...) (C++/CLI)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4572 oluşturur.

```cpp
// C4572.cpp
// compile with: /clr /W1
void Func([System::ParamArray] array<int> ^);   // C4572
void Func2(... array<int> ^){}   // OK

int main() {
   Func2(1, 2, 3);
}
```
