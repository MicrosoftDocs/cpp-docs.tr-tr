---
title: Derleyici Hatası C3386
ms.date: 11/04/2016
f1_keywords:
- C3386
helpviewer_keywords:
- C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
ms.openlocfilehash: a9183e1f62e7ebaf5db04a35a45806ec02169e69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328815"
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