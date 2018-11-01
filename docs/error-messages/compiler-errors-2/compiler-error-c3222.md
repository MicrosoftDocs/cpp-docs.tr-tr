---
title: Derleyici Hatası C3222
ms.date: 11/04/2016
f1_keywords:
- C3222
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
ms.openlocfilehash: 9f2c245e98609c8da8f5f89902d5c51bbf9d2b4f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638678"
---
# <a name="compiler-error-c3222"></a>Derleyici Hatası C3222

'parameter': yönetilen işlevleri veya WinRT türü veya genel işlevlerin üye için varsayılan bağımsız değişkenleri bildiremez

Varsayılan bağımsız değişkenli bir yöntem parametresi bildirmek için izin verilmez. Yöntemin aşırı yüklenmiş bir formun bu sorunu çözmek için bir yoludur. Diğer bir deyişle, hiçbir parametre ile aynı ada sahip bir yöntemi tanımlamak ve yöntem gövdesini değişkeninde'ı başlatın.

Aşağıdaki örnek, C3222 oluşturur:

```
// C3222_2.cpp
// compile with: /clr
public ref class G {
   void f( int n = 0 );   // C3222
};
```
