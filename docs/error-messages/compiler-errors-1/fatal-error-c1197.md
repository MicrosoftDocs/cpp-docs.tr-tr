---
title: Önemli hata C1197
ms.date: 11/04/2016
f1_keywords:
- C1197
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
ms.openlocfilehash: e1c00a001c807b0cc6a5946b61ca4e9d5dc0167a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62229130"
---
# <a name="fatal-error-c1197"></a>Önemli hata C1197

'mscorlib.dll_1' program 'mscorlib.dll_2' zaten başvurmuş gibi başvuramaz

Derleyici, bir ortak dil çalışma zamanı sürümüne eşleştirilir.  Ancak, bir ortak dil çalışma zamanı dosyası sürümü önceki bir sürümden başvurmak için girişimde bulunuldu.

Bu hatayı gidermek için yalnızca Visual C++ ile derleme sürümü ile birlikte gelen ortak dil çalışma zamanı sürümünden dosyaları başvuru.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C1197 oluşturur:

```
// C1197.cpp
// compile with: /clr /c
// processor: x86
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197
// try the following line instead
// #using "mscorlib.dll"
```