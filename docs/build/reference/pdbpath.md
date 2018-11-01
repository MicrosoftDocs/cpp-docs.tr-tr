---
title: /PDBPATH
ms.date: 11/04/2016
f1_keywords:
- /pdbpath
helpviewer_keywords:
- .pdb files, path
- -PDBPATH dumpbin option
- /PDBPATH dumpbin option
- PDBPATH dumpbin option
- PDB files, path
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
ms.openlocfilehash: d77ab2eb056326ba372a60cc79688d26b252ac44
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527224"
---
# <a name="pdbpath"></a>/PDBPATH

```
/PDBPATH[:VERBOSE] filename
```

### <a name="parameters"></a>Parametreler

*Dosya adı*<br/>
Eşleşen .pdb dosyasını bulmak istediğiniz .dll veya .exe dosyasının adı.

**: AYRINTILI**<br/>
(İsteğe bağlı) Tüm dizinler .pdb dosyasını bulmak için denemesi yapıldığı bildirir.

## <a name="remarks"></a>Açıklamalar

/ PDBPATH bilgisayarınız varsa, .pdb dosyaları içinde belirtilen dosyaya karşılık gelen, hata ayıklayıcı bir .pdb dosyası için arama ve raporlar aynı yollar boyunca arama yapacağı *filename*.

Hata ayıklayıcı bir .pdb dosyası ayıkladığınız dosyayı farklı bir sürümü kullanıyor. Bunun nedeni, Visual Studio hata ayıklayıcısını kullanırken bir sorunla karşılaşabilirsiniz.

/ PDBPATH aşağıdaki yollarla birlikte .pdb dosyaları arar:

- Yürütülebilir dosyanın bulunduğu konumu kontrol edin.

- Çalıştırılabilir dosyaya yazılan PDB konumunu denetleyin. Bu genellikle görüntünün bağlı olduğu zaman konumdur.

- Visual Studio IDE içinde yapılandırılan arama yolu boyunca denetleyin.

- _NT_SYMBOL_PATH ve _NT_ALT_SYMBOL_PATH yolları boyunca ortam değişkenlerinizi denetleyin.

- Windows dizinde denetleyin.

## <a name="see-also"></a>Ayrıca Bkz.

[DUMPBIN Seçenekleri](../../build/reference/dumpbin-options.md)<br/>
[/PDBALTPATH (Diğer PDB Yolunu Kullan)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)