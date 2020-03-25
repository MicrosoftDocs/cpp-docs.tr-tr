---
title: Bağlayıcı Araçları Uyarısı LNK4197
ms.date: 09/05/2018
f1_keywords:
- LNK4197
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
ms.openlocfilehash: 92702864a00455e4b70f00dfc9988bfb754e2e64
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183286"
---
# <a name="linker-tools-warning-lnk4197"></a>Bağlayıcı Araçları Uyarısı LNK4197

> '*exportname*' dışarı aktarma işlemi birden çok kez belirtildi; ilk belirtim kullanılıyor

Dışarı aktarma birden çok ve farklı şekilde belirtilir. Bağlayıcı ilk belirtimi kullanır ve REST 'yi yoksayar.

C çalışma zamanı kitaplığını yeniden oluşturuyorsanız bu iletiyi yoksayabilirsiniz.

Bir dışarı aktarma işlemi aynı şekilde birden çok kez belirtilirse bağlayıcı bir uyarı vermez.

Örneğin, bir. def dosyasının aşağıdaki içeriği bu uyarıya neden olur:

```
EXPORTS
   functioname      NONAME
   functioname      @10
```

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Aynı dışa aktarma hem komut satırında (Export:) aracılığıyla) belirtilir ve. def dosyasında.

2. Aynı dışa aktarma,. def dosyasında farklı özniteliklere sahip iki kez listelenir.
