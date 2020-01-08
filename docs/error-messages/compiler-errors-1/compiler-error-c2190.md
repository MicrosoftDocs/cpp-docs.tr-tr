---
title: Derleyici hatası C2190
ms.date: 11/04/2016
f1_keywords:
- C2190
helpviewer_keywords:
- C2190
ms.assetid: 34e15f85-d979-4948-80fc-46c414508a70
ms.openlocfilehash: 027c7f49b361ef3aa06a4d74e10f0ff27331b4a9
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301892"
---
# <a name="compiler-error-c2190"></a>Derleyici hatası C2190

ilk parametre listesi ikinciden uzun

Bir C işlevi, daha kısa bir parametre listesiyle ikinci kez bildirildi. C, aşırı yüklenmiş işlevleri desteklemez.

Aşağıdaki örnek C2190 oluşturur:

```c
// C2190.c
// compile with: /Za /c
void func( int, float );
void func( int  );   // C2190, different parameter list
void func2( int  );   // OK
```
