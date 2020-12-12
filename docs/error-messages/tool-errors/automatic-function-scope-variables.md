---
description: 'Daha fazla bilgi edinin: otomatik (işlev kapsamı) değişkenleri'
title: Otomatik (işlev kapsamı) değişkenleri
ms.date: 04/22/2019
helpviewer_keywords:
- automatic variables
- variables, automatic
- functions [C++], scope
- scope, declared within functions
ms.assetid: 6e1a14c2-1fb0-4937-8628-8d963cc35ed4
ms.openlocfilehash: 666a59ce6ebb9e8d011216f87ca45b49eabbc766
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323018"
---
# <a name="automatic-function-scope-variables"></a>Otomatik (işlev kapsamı) değişkenleri

Bir işlev içinde belirtilen değişken yalnızca o işlevin kapsamı içinde kullanılabilir.

```cpp
// LNK2019_AV.cpp
// compile with: /c
void test(void);

static int lnktest3 = 3;
int lnktest4 = 4;

int main() {
   static int lnktest1 = 1;
   int lnktest2 = 2;
   test();
}
```

ardından,

```cpp
// LNK2019_AV_2.cpp
// compile with: LNK2019_AV.cpp
// LNK2019 expected
extern int lnktest1;
extern int lnktest2;
extern int lnktest3;
extern int lnktest4;

void test(void) {
   int i = 0;
   i = lnktest1;
   i = lnktest2;
   i = lnktest3;
   i = lnktest4;   // OK
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı araçları hatası LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
