---
title: Önemli hata C1197 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1197
dev_langs:
- C++
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 58561e7bd906fc750779ef53a4f68ec27088a3b7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024768"
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