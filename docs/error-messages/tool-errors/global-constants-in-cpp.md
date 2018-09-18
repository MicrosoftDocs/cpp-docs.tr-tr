---
title: C++'da Global sabitler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 00d033c1c4fc8fc3e534c8e4ee0c3d7867b83834
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103179"
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