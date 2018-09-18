---
title: Derleyici Hatası C2157 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2157
dev_langs:
- C++
helpviewer_keywords:
- C2157
ms.assetid: babbca24-16dc-4b69-be14-a675029249c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd17b03cc48555800e3c36cc3f5512506f011372
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072081"
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