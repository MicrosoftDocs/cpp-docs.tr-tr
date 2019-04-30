---
title: Bağlayıcı Araçları Uyarısı LNK4197
ms.date: 09/05/2018
f1_keywords:
- LNK4197
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
ms.openlocfilehash: 0abad1b98ff4782f077312752603ec17fd611c12
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390366"
---
# <a name="linker-tools-warning-lnk4197"></a>Bağlayıcı Araçları Uyarısı LNK4197

> dışarı aktarma '*exportname*' belirtilmiş birden çok kez; ilk belirtim kullanılıyor

Bir dışarı aktarma, birden çok belirtilen ve farklı yolları. Bağlayıcı ilk belirtimi kullanır ve kalan yok sayar.

C çalışma zamanı kitaplığı yeniden, bu iletiyi yoksayabilirsiniz.

Bir dışarı aktarma, birden çok kez tamamen aynı şekilde belirtilirse, bağlayıcı bir uyarı veremez.

Örneğin, aşağıdaki .def dosyası içeriğini, bu uyarı vermesine neden olur:

```
EXPORTS
   functioname      NONAME
   functioname      @10
```

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Aynı dışarı aktarma belirtilen komut satırında hem de (dışarı aktarma ile:) ve .def dosyasında.

2. Aynı dışarı aktarma, farklı öznitelikleri .def dosyasında iki kez listelenir.