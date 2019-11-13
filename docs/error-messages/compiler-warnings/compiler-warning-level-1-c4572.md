---
title: Derleyici Uyarısı (düzey 1) C4572
ms.date: 11/04/2016
f1_keywords:
- C4572
helpviewer_keywords:
- C4572
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
ms.openlocfilehash: 52285f391af0a8028307cbbc320af33f9cb1fca5
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965953"
---
# <a name="compiler-warning-level-1-c4572"></a>Derleyici Uyarısı (düzey 1) C4572

[ParamArray] özniteliği/clr altında kullanım dışıdır, '... ' kullanın yerine

Değişken bağımsız değişken listesinin belirtilmesine yönelik eski bir stil kullanıldı. CLR için derlerken <xref:System.ParamArrayAttribute>yerine üç nokta sözdizimi kullanın. Daha fazla bilgi için bkz. [değişken bağımsız değişken listeleri (...C++) (/CLI)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md).

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