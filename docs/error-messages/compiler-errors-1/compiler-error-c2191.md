---
title: Derleyici Hatası C2191 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2191
dev_langs:
- C++
helpviewer_keywords:
- C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e739c5c9fc77c4c9658afb2f5f6d9568c6f43bb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088364"
---
# <a name="compiler-error-c2191"></a>Derleyici Hatası C2191

İkinci parametre listesi birinciden uzun

C işlevi, ikinci bir kez daha uzun bir parametre listesiyle bildirildi. C, aşırı yüklenmiş işlevler desteklemez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2191 oluşturur:

```
// C2191.c
// compile with: /Za /c
void func( int );
void func( int, float );   // C2191 different parameter list
void func2( int, float );   // OK
```