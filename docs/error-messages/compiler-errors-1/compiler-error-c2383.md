---
title: Derleyici Hatası C2383
ms.date: 11/04/2016
f1_keywords:
- C2383
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
ms.openlocfilehash: 06d4c19208bd242169e1cd07a71e8a568f46f7b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466098"
---
# <a name="compiler-error-c2383"></a>Derleyici Hatası C2383

'*sembol*': Bu Simgede varsayılan bağımsız değişkenlere izin verilmez

C++ derleyicisi işlev işaretçileri varsayılan bağımsız değişkenler görülmez.

Bu kod, Visual Studio 2005 öncesi sürümlerinde Visual C++ Derleyici tarafından kabul edildi, ancak şimdi bir hata verir. Visual C++'ın tüm sürümlerinde çalışan kod için bir işaretçi işlevi bağımsız değişkeni için varsayılan bir değer atamayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2383 oluşturur ve olası bir çözüm gösterilmektedir:

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```