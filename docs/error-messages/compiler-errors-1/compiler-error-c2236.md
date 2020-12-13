---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2236'
title: Derleyici hatası C2236
ms.date: 11/04/2016
f1_keywords:
- C2236
helpviewer_keywords:
- C2236
ms.assetid: 0b6771a7-a783-4729-9c3d-7a3339c432cc
ms.openlocfilehash: 91b04cad6be02a3a50a21af9ef3397fb17d9c43b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338732"
---
# <a name="compiler-error-c2236"></a>Derleyici hatası C2236

beklenmeyen belirteç ' identifier '. '; ' Öğesini unuttunuz mu?

Tanımlayıcı zaten bir tür olarak tanımlanmış ve Kullanıcı tanımlı bir tür tarafından geçersiz kılınamaz.

Aşağıdaki örnek C2236 oluşturur:

```cpp
// C2236.cpp
// compile with: /c
int class A {};  // C2236 "int class" is unexpected
int i;
class B {};
```
