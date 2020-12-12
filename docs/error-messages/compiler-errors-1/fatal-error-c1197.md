---
description: 'Daha fazla bilgi edinin: önemli hata C1197'
title: Önemli hata C1197
ms.date: 11/04/2016
f1_keywords:
- C1197
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
ms.openlocfilehash: c61cbd71fa8f17dc787fd9ee5eabd0f073aafb39
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268177"
---
# <a name="fatal-error-c1197"></a>Önemli hata C1197

Program ' mscorlib.dll_2 ' öğesine zaten başvurulduğundan ' mscorlib.dll_1 ' öğesine başvurulamaz

Derleyici, ortak dil çalışma zamanının bir sürümüyle eşleştirilir.  Ancak, önceki bir sürümden ortak dil çalışma zamanı dosyasının bir sürümüne başvurmak için bir girişimde bulunuldu.

Bu hatayı çözmek için, yalnızca derleme yaptığınız Visual C++ sürümü ile birlikte gelen ortak dil çalışma zamanının sürümüne ait dosyaları referans.

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
