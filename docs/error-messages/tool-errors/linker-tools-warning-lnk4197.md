---
title: Bağlayıcı araçları uyarısı LNK4197 | Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4197
dev_langs:
- C++
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55044ce511e2584e2859b7e8a8d723cbe0976105
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894492"
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