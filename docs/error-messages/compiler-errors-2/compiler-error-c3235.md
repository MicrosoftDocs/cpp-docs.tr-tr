---
title: Derleyici Hatası C3235
ms.date: 11/04/2016
f1_keywords:
- C3235
helpviewer_keywords:
- C3235
ms.assetid: 0554d6c7-e1dc-4c99-8934-cbcf491c8203
ms.openlocfilehash: 1e74d479e75aee98dada16107b7e33d5cfe0c0cd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520326"
---
# <a name="compiler-error-c3235"></a>Derleyici Hatası C3235

'özelleştirmesi': bir genel sınıfın açık veya kısmı özelleştirmesine izin verilmez

Genel sınıflar açık ya da kısmi uzmanlıklar için kullanılamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3235 oluşturur.

```
// C3235.cpp
// compile with: /clr
generic<class T>
public ref class C {};

generic<>
public ref class C<int> {};   // C3235 Remove this specialization to resolve this error.
```