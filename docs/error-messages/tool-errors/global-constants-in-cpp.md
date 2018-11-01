---
title: C++'da Global Sabitler
ms.date: 11/04/2016
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
ms.openlocfilehash: 3da61b7718dadba9b454ee079651ce6372f21756
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432623"
---
# <a name="global-constants-in-c"></a>C++'da Global Sabitler

C++ global sabitler statik bağlantısı vardır. Bu c farklı. Genel bir kullanmayı denerseniz c++ birden çok dosya içindeki sabit çözülmemiş dış hata alırsınız. Derleyici global sabitler, değişken için ayrılmış boşluk bırakarak iyileştirir.

Bu hatayı gidermek için bir const başlatmalar bir üstbilgi dosyasına eklenecek ve gerektiğinde, yalnızca işlev prototipi olduğu gibi CPP dosyalarınızda bu üstbilgisini yoludur. Diğer bir olasılık değişkeni sabit olmayan yapın ve sabit bir başvuru da değerlendirirken kullanmaktır.

Aşağıdaki örnek, C2019 oluşturur:

```
// global_constants.cpp
// LNK2019 expected
void test(void);
const int lnktest1 = 0;

int main() {
   test();
}
```

Ardından,

```
// global_constants_2.cpp
// compile with: global_constants.cpp
extern int lnktest1;

void test() {
  int i = lnktest1;   // LNK2019
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Araçları Hatası LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)