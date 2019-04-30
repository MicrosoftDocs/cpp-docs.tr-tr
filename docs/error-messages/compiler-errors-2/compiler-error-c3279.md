---
title: Derleyici Hatası C3279
ms.date: 11/04/2016
f1_keywords:
- C3279
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
ms.openlocfilehash: 5f39510ee9ec0e717d675aa8b396405bc33b4ea1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62381957"
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