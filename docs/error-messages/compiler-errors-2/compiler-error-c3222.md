---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3222'
title: Derleyici hatası C3222
ms.date: 11/04/2016
f1_keywords:
- C3222
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
ms.openlocfilehash: 77883b6bd9be034fff2a0bcf3babdb1489c9a937
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267722"
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
