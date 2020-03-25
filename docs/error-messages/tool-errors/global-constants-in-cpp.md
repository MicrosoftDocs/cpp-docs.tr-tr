---
title: C++'da Global Sabitler
ms.date: 11/04/2016
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
ms.openlocfilehash: cabe5e92a496181d60536d7274eca388aba5c068
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195480"
---
# <a name="global-constants-in-c"></a>C++'da Global Sabitler

C++Genel sabitler statik bağlantıya sahiptir. Bu, C 'den farklıdır. Birden çok dosyada içinde C++ genel bir sabit kullanmayı denerseniz, çözümlenmemiş bir dış hata alırsınız. Derleyici, genel sabitleri en iyi duruma getirir ve değişken için ayrılan alan yok bırakır.

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

ardından,

```cpp
// global_constants_2.cpp
// compile with: global_constants.cpp
extern int lnktest1;

void test() {
  int i = lnktest1;   // LNK2019
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Araçları Hatası LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
