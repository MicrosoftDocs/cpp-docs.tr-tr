---
title: Derleyici Hatası C2388 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2388
dev_langs:
- C++
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b6bcec4f5f218a52981a7770f5fa6e600494d9a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114156"
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