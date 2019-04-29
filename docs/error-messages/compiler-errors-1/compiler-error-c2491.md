---
title: Derleyici Hatası C2491
ms.date: 11/04/2016
f1_keywords:
- C2491
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
ms.openlocfilehash: 3b48bebde6d7baedea73ed181cd4ea33adc44a69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62361340"
---
# <a name="compiler-error-c2491"></a>Derleyici Hatası C2491

'identifier': dllimport işlevin izin tanımı

Olarak veri, statik veri üyeleri ve işlevleri bildirilebilir `dllimport`s ancak tanımlanmamış `dllimport`s.

Bu sorunu gidermek için kaldırma `__declspec(dllimport)` işlev tanımından tanımlayıcısı.

Aşağıdaki örnek, C2491 oluşturur:

```
// C2491.cpp
// compile with: /c
// function definition
void __declspec(dllimport) funcB() {}   // C2491

// function declaration
void __declspec(dllimport) funcB();   // OK
```