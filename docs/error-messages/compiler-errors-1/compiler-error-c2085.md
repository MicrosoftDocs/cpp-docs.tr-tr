---
title: Derleyici Hatası C2085 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2085
dev_langs:
- C++
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d88968e49e38a13782dde2d905a614ad4d177e81
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082384"
---
# <a name="compiler-error-c2085"></a>Derleyici Hatası C2085

'identifier': biçimsel parametre listesinde değil

Tanımlayıcı, bir işlev tanımında ancak biçimsel parametre listesinde bildirildi. (Yalnızca ANSI C)

Aşağıdaki örnek, C2085 oluşturur:

```
// C2085.c
void func1( void )
int main( void ) {}   // C2085
```

Olası çözüm:

```
// C2085b.c
void func1( void );
int main( void ) {}
```

Noktalı virgül eksik olan `func1()` bu nedenle bir prototipi bir işlev tanımı gibi görünüyor `main` içinde tanımlanan `func1()`, hatası C2085 tanımlayıcısı oluşturma `main`.