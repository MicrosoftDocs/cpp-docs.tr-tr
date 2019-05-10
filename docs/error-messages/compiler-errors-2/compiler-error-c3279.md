---
title: Derleyici Hatası C3279
ms.date: 11/04/2016
f1_keywords:
- C3279
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
ms.openlocfilehash: 72646d7611163748fe7e27ea6c78cd38426eb6ad
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447818"
---
# <a name="compiler-error-c3279"></a>Derleyici Hatası C3279

sınıf şablonlarının açık örnek oluşumu cli ad alanında bildirilen kısmı ve açık özelleştirmelere izin verilmiyor

`cli` Ad alanı, Microsoft tarafından tanımlanır ve sahte şablonları içerir. Microsoft C++ derleyici izin vermiyor kullanıcı tanımlı, kısmı ve açık özelleştirmelere yanı sıra, sınıf şablonlarının açık örnek oluşturma işlemleri bu ad alanında.

Aşağıdaki örnek, C3279 oluşturur:

```
// C3279.cpp
// compile with: /clr
namespace cli {
   template <> ref class array<int> {};   // C3279
   template <typename T> ref class array<T, 2> {};   // C3279
}
```