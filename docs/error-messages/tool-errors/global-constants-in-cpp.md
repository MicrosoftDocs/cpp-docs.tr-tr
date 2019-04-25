---
title: C++'da Global Sabitler
ms.date: 11/04/2016
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
ms.openlocfilehash: 2f0621f52fe445f8f2058ef902824ddc1f5e2bb5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62255436"
---
# <a name="global-constants-in-c"></a>C++'da Global Sabitler

C++ global sabitler statik bağlantısı vardır. Bu c farklı. Genel bir kullanmayı denerseniz c++ birden çok dosya içindeki sabit çözülmemiş dış hata alırsınız. Derleyici global sabitler, değişken için ayrılmış boşluk bırakarak iyileştirir.

Bu hatayı gidermek için bir const başlatmalar bir üstbilgi dosyasına eklenecek ve gerektiğinde, yalnızca işlev prototipi olduğu gibi CPP dosyalarınızda bu üstbilgisini yoludur. Diğer bir olasılık değişkeni sabit olmayan yapın ve sabit bir başvuru da değerlendirirken kullanmaktır.

Aşağıdaki örnek, C2019 oluşturur:

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

[Bağlayıcı Araçları Hatası LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)