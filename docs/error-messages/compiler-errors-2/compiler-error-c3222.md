---
title: Derleyici Hatası C3222 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3222
dev_langs:
- C++
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30231f74b379cd9d69806fbd4b49ba0cb55ad871
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048324"
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
