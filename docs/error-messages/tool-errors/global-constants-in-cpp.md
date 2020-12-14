---
description: "Daha fazla bilgi edinin: C++ ' da Global sabitler"
title: C++'da Global Sabitler
ms.date: 11/04/2016
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
ms.openlocfilehash: 8e960e7e10942fc231fcdeafef6e8d755694c460
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261664"
---
# <a name="global-constants-in-c"></a>C++'da Global Sabitler

C++ genel sabitlerinde statik bağlantı vardır. Bu, C 'den farklıdır. C++ ' da birden çok dosyada genel bir sabit kullanmayı denerseniz, çözümlenmemiş bir dış hata alırsınız. Derleyici, genel sabitleri en iyi duruma getirir ve değişken için ayrılan alan yok bırakır.

Bu hatayı çözmek için bir yol, bir üstbilgi dosyasına const başlatmaları dahil etmek ve gerekli olduğunda bu üstbilgiyi, prototip dosyalarınıza dahil etmek olacaktır. Diğer bir olasılık ise değişkeni sabit olmayan bir hale getirmek ve değerlendirmek için sabit bir başvuru kullanmaktır.

Aşağıdaki örnek C2019 oluşturur:

```cpp
// global_constants.cpp
// LNK2019 expected
void test(void);
const int lnktest1 = 0;

int main() {
   test();
}
```

Ardından,

```cpp
// global_constants_2.cpp
// compile with: global_constants.cpp
extern int lnktest1;

void test() {
  int i = lnktest1;   // LNK2019
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Araçları hatası LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
