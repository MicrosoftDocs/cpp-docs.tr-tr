---
title: Derleyici Hatası C2801 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2801
dev_langs:
- C++
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d57ee5bf5f5152ef55852c9f9b829bc4a1d17d41
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040641"
---
# <a name="compiler-error-c2801"></a>Derleyici Hatası C2801

'operator işleci' statik olmayan üye olmanız gerekir

Aşağıdaki işleçleri yalnızca statik olmayan üye olarak aşırı yüklenebilir:

- Atama `=`

- Sınıf üyesi erişimi `->`

- Subscripting `[]`

- İşlev çağrısı `()`

Olası C2801 neden olur:

- Aşırı yüklenmiş işleç, bir sınıf, yapı veya birleşim üyesi değil.

- Aşırı yüklenmiş işleç bildirilmiş `static`.

- Aşağıdaki örnek, C2801 oluşturur:

```
// C2801.cpp
// compile with: /c
operator[]();   // C2801 not a member
class A {
   static operator->();   // C2801 static
   operator()();   // OK
};
```