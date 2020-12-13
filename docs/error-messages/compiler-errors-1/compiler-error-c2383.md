---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2383'
title: Derleyici hatası C2383
ms.date: 11/04/2016
f1_keywords:
- C2383
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
ms.openlocfilehash: 862346d7f2bfe92a5d2182a7fe53f260b357ad0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185940"
---
# <a name="compiler-error-c2383"></a>Derleyici hatası C2383

'*symbol*': Bu sembolde varsayılan bağımsız değişkenlere izin verilmiyor

C++ derleyicisi işlevlere yönelik işaretçilerde varsayılan bağımsız değişkenlere izin vermez.

Bu kod, Visual Studio 2005 ' den önceki sürümlerde Microsoft C++ derleyicisi tarafından kabul edildi, ancak şimdi bir hata veriyor. Tüm Visual C++ sürümlerinde çalışır olan kod için, bir işaretçiden işleve bağımsız değişkenine varsayılan bir değer atamayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2383 oluşturur ve olası bir çözümü gösterir:

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```
