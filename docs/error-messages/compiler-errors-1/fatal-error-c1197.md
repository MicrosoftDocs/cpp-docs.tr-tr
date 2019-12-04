---
title: Önemli hata C1197
ms.date: 11/04/2016
f1_keywords:
- C1197
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
ms.openlocfilehash: 7f698262c73f0b311a92a8940107b552430919bb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747247"
---
# <a name="fatal-error-c1197"></a>Önemli hata C1197

Program ' mscorlib. dll_2 ' öğesine zaten başvurulduğundan ' mscorlib. dll_1 ' öğesine başvurulamaz

Derleyici, ortak dil çalışma zamanının bir sürümüyle eşleştirilir.  Ancak, önceki bir sürümden ortak dil çalışma zamanı dosyasının bir sürümüne başvurmak için bir girişimde bulunuldu.

Bu hatayı çözmek için, yalnızca derleme yaptığınız görsel C++ sürümü ile birlikte gelen ortak dil çalışma zamanının sürümüne ait dosyaları referans.

## <a name="example"></a>Örnek

Aşağıdaki örnek C1197 oluşturur:

```cpp
// C1197.cpp
// compile with: /clr /c
// processor: x86
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197
// try the following line instead
// #using "mscorlib.dll"
```
