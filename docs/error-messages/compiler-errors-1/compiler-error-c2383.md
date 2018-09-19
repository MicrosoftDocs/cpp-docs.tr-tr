---
title: Derleyici Hatası C2383 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2383
dev_langs:
- C++
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c529c22636f112291fa53b852899cad78dac589
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113233"
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