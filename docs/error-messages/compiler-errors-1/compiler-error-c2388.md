---
title: Derleyici Hatası C2388
ms.date: 11/04/2016
f1_keywords:
- C2388
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
ms.openlocfilehash: 62afcb1fafc19d3d61a86f2fbc10cb99e095afc5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393668"
---
# <a name="compiler-error-c2388"></a>Derleyici Hatası C2388

'symbol': bir simge hem __declspec(appdomain) ile bildirilemez ve \__declspec(process)

`appdomain` Ve `process` `__declspec` değiştiriciler aynı sembol sunucusunda kullanılamaz. Bir değişken için depolama, işlem veya uygulama etki alanı başına bulunmaktadır.

Daha fazla bilgi için [appdomain](../../cpp/appdomain.md) ve [işlem](../../cpp/process.md).

Aşağıdaki örnek, C2388 oluşturur:

```
// C2388.cpp
// compile with: /clr /c
__declspec(process) __declspec(appdomain) int i;   // C2388
__declspec(appdomain) int i;   // OK
```