---
title: Derleyici Hatası C3179
ms.date: 11/04/2016
f1_keywords:
- C3179
helpviewer_keywords:
- C3179
ms.assetid: 60d7e41b-25fd-48ac-8b79-830c062f4dcd
ms.openlocfilehash: a5c92e8a776e318e732448ba31beedef946d9f41
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174074"
---
# <a name="compiler-error-c3179"></a>Derleyici Hatası C3179

adlandırılmamış bir yönetilen veya WinRT türüne izin verilmiyor

Tüm CLR ve WinRT sınıflar ve yapılar adlara sahip olmalıdır.

Aşağıdaki örnek, C3179 oluşturur ve bu sorunun nasıl gösterir:

```
// C3179a.cpp
// compile with: /clr /c
typedef value struct { // C3179
// try the following line instead
// typedef value struct MyStruct {
   int i;
} V;
```
