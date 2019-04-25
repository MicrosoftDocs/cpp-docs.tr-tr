---
title: Derleyici Hatası C2157
ms.date: 11/04/2016
f1_keywords:
- C2157
helpviewer_keywords:
- C2157
ms.assetid: babbca24-16dc-4b69-be14-a675029249c1
ms.openlocfilehash: 1338a0f0ceb1a42ed84fe74e4ed9a2d774979075
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174867"
---
# <a name="compiler-error-c2157"></a>Derleyici Hatası C2157

'function': pragma listesinde kullanılmadan önce bildirilmelidir

İşlev adı için işlevleri listesinde başvurulan önce bildirilmedi bir [alloc_text](../../preprocessor/alloc-text.md) pragması.

Aşağıdaki örnek, C2157 oluşturur:

```
// C2157.cpp
// compile with: /c
#pragma alloc_text( "func", func)   // C2157

// OK
extern "C" void func();
#pragma alloc_text( "func", func)
```