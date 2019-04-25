---
title: Derleyici Hatası C2191
ms.date: 11/04/2016
f1_keywords:
- C2191
helpviewer_keywords:
- C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
ms.openlocfilehash: 23dfe1d95ab75f253fc2a7b4b00dfcd1aaaa3bbf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302976"
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