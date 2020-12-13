---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2191'
title: Derleyici hatası C2191
ms.date: 11/04/2016
f1_keywords:
- C2191
helpviewer_keywords:
- C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
ms.openlocfilehash: b3b2133e70eeae566a972b0e5db11105b316d6f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337667"
---
# <a name="compiler-error-c2191"></a>Derleyici hatası C2191

ikinci parametre listesi birinciden uzun

Bir C işlevi, daha uzun bir parametre listesi ile ikinci kez bildirildi. C, aşırı yüklenmiş işlevleri desteklemez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2191 oluşturur:

```c
// C2191.c
// compile with: /Za /c
void func( int );
void func( int, float );   // C2191 different parameter list
void func2( int, float );   // OK
```
