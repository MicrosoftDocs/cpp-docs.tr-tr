---
title: Derleyici hatası C3222
ms.date: 11/04/2016
f1_keywords:
- C3222
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
ms.openlocfilehash: 96a6b1b81d2d82328dcb4ceaca376f247f785c13
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737952"
---
# <a name="compiler-error-c3222"></a>Derleyici hatası C3222

' Parameter ': yönetilen veya WinRT türünün veya genel işlevlerin üye işlevleri için varsayılan bağımsız değişkenler bildirilemez

Varsayılan bağımsız değişkenle bir yöntem parametresi bildirmek için izin verilmez. Yöntemin aşırı yüklenmiş bir biçimi, bu sorunu geçici olarak çözmek için bir yoldur. Diğer bir deyişle, parametresiz aynı ada sahip bir yöntem tanımlayabilir ve sonra Yöntem gövdesinde değişkeni başlatın.

Aşağıdaki örnek C3222 oluşturur:

```cpp
// C3222_2.cpp
// compile with: /clr
public ref class G {
   void f( int n = 0 );   // C3222
};
```
