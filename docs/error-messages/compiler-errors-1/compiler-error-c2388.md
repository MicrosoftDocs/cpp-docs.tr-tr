---
title: Derleyici hatası C2388
ms.date: 11/04/2016
f1_keywords:
- C2388
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
ms.openlocfilehash: 50148f4fb5c3af33d8de8b005f75f491b0540271
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225507"
---
# <a name="compiler-error-c2388"></a>Derleyici hatası C2388

' symbol ': bir simge hem __declspec (AppDomain) hem de \_ _declspec (işlem) ile bildirilemez

`appdomain`Ve `process` **`__declspec`** değiştiricileri aynı sembol üzerinde kullanılamaz. Bir değişken için depolama, işlem veya uygulama etki alanı başına mevcuttur.

Daha fazla bilgi için bkz. [AppDomain](../../cpp/appdomain.md) ve [Process](../../cpp/process.md).

Aşağıdaki örnek C2388 oluşturur:

```cpp
// C2388.cpp
// compile with: /clr /c
__declspec(process) __declspec(appdomain) int i;   // C2388
__declspec(appdomain) int i;   // OK
```
