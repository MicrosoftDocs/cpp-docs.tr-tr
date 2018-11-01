---
title: Derleyici Hatası C3279
ms.date: 11/04/2016
f1_keywords:
- C3279
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
ms.openlocfilehash: 5f39510ee9ec0e717d675aa8b396405bc33b4ea1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445012"
---
# <a name="compiler-error-c3279"></a>Derleyici Hatası C3279

sınıf şablonlarının açık örnek oluşumu cli ad alanında bildirilen kısmı ve açık özelleştirmelere izin verilmiyor

`cli` Ad alanı, Microsoft tarafından tanımlanır ve sahte şablonları içerir. Visual C++ Derleyici kullanıcı tanımlı, kısmı ve açık özelleştirmelere yanı sıra, sınıf şablonlarının açık örnek oluşturma işlemleri bu ad alanında izin vermez.

Aşağıdaki örnek, C3279 oluşturur:

```
// C3279.cpp
// compile with: /clr
namespace cli {
   template <> ref class array<int> {};   // C3279
   template <typename T> ref class array<T, 2> {};   // C3279
}
```