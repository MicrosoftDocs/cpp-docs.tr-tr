---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3519'
title: Derleyici hatası C3519
ms.date: 11/04/2016
f1_keywords:
- C3519
helpviewer_keywords:
- C3519
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
ms.openlocfilehash: f8eb90620894627beab450275c6725d665d837e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113116"
---
# <a name="compiler-error-c3519"></a>Derleyici hatası C3519

' invalid_param ': embedded_idl özniteliğe geçersiz parametre

#İmport özniteliğine bir parametre geçirildi `embedded_idl` , ancak derleyici [](../../preprocessor/hash-import-directive-cpp.md)parametreyi tanımıyor.

İçin izin verilen tek parametreler `embedded_idl` `emitidl` ve ' dir `no_emitidl` .

Aşağıdaki örnek C3519 oluşturur:

```cpp
// C3519.cpp
// compile with: /LD
[module(name="MyLib2")];
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")
// C3519
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")
// OK
```
