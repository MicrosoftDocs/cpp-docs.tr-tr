---
title: Derleyici Hatası C2383
ms.date: 11/04/2016
f1_keywords:
- C2383
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
ms.openlocfilehash: e9c1774fe7cd4a6883aa79f384cc64521a57ed17
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448011"
---
# <a name="compiler-error-c2383"></a>Derleyici Hatası C2383

'*sembol*': Bu Simgede varsayılan bağımsız değişkenlere izin verilmez

C++ derleyicisi işlev işaretçileri varsayılan bağımsız değişkenler görülmez.

Bu kod, Microsoft tarafından kabul edildi C++ derleyici Visual Studio 2005 öncesi sürümlerinde, ancak şimdi bir hata verir. Visual C++'ın tüm sürümlerinde çalışan kod için bir işaretçi işlevi bağımsız değişkeni için varsayılan bir değer atamayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2383 oluşturur ve olası bir çözüm gösterilmektedir:

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```