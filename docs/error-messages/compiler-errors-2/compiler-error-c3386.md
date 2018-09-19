---
title: Derleyici Hatası C3386 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3386
dev_langs:
- C++
helpviewer_keywords:
- C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a68f047309d0a83bc1e0eb86f0651c3f20f310c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093785"
---
# <a name="compiler-error-c3386"></a>Derleyici Hatası C3386

'type': __declspec(dllexport) /\_yönetilen veya WinRTtype _declspec(dllimport) uygulanamaz

`dllimport` Ve [dllexport](../../cpp/dllexport-dllimport.md) `__declspec` değiştiriciler, yönetilen veya Windows çalışma zamanı geçerli olmayan türü.

Aşağıdaki örnek, C3386 oluşturur ve bu sorunun nasıl gösterir:

```
// C3386.cpp
// compile with: /clr /c
ref class __declspec(dllimport) X1 {   // C3386
// try the following line instead
// ref class X1 {
};
```