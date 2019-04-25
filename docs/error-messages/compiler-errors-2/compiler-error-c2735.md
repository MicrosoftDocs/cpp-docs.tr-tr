---
title: Derleyici Hatası C2735
ms.date: 11/04/2016
f1_keywords:
- C2735
helpviewer_keywords:
- C2735
ms.assetid: 6ce45600-7148-4bc0-8699-af0ef137571e
ms.openlocfilehash: 73d5f61b5f86153db74a970d97b4656fb662bdad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152455"
---
# <a name="compiler-error-c2735"></a>Derleyici Hatası C2735

'anahtar sözcüğü' anahtar sözcüğü biçimsel parametre türü belirticisi içinde izin verilmiyor

Anahtar sözcüğü bu bağlamda geçersiz.

Aşağıdaki örnek, C2735 oluşturur:

```
// C2735.cpp
void f(inline int){}   // C2735
```