---
title: Derleyici Hatası C3269 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3269
dev_langs:
- C++
helpviewer_keywords:
- C3269
ms.assetid: c575f067-244d-4dd5-bf58-9e7630ea58b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84cb9acdd6444b934e7ec51691d87a6912880de2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061818"
---
# <a name="compiler-error-c3269"></a>Derleyici Hatası C3269

'function': bir üye işlevi bir yönetilen veya WinRTtype bildirilemez '...' ile

Yönetilen ve WinRT sınıf üyesi işlevleri değişken uzunluklu parametre listeleri bildiremezsiniz.

Aşağıdaki örnek, C3269 oluşturur ve bu sorunun nasıl gösterir:

```
// C3269_2.cpp
// compile with: /clr

ref struct A
{
   void func(int i, ...)   // C3269
   // try the following line instead
   // void func(int i )
   {
   }
};

int main()
{
}
```
