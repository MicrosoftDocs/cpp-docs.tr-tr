---
title: Derleyici hatası C2388
ms.date: 11/04/2016
f1_keywords:
- C2388
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
ms.openlocfilehash: 21658a659468a6e2a0d911af70eefdaed320446c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745063"
---
# <a name="compiler-error-c2388"></a>Derleyici hatası C2388

' symbol ': bir simge hem __declspec (AppDomain) hem de \__declspec (işlem) ile bildirilemez

`appdomain` ve `process` `__declspec` değiştiriciler aynı sembolde kullanılamaz. Bir değişken için depolama, işlem veya uygulama etki alanı başına mevcuttur.

Daha fazla bilgi için bkz. [AppDomain](../../cpp/appdomain.md) ve [Process](../../cpp/process.md).

Aşağıdaki örnek C2388 oluşturur:

```cpp
// C2388.cpp
// compile with: /clr /c
__declspec(process) __declspec(appdomain) int i;   // C2388
__declspec(appdomain) int i;   // OK
```
