---
title: -PDBPATH | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /pdbpath
dev_langs:
- C++
helpviewer_keywords:
- .pdb files, path
- -PDBPATH dumpbin option
- /PDBPATH dumpbin option
- PDBPATH dumpbin option
- PDB files, path
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c9d93ef38ba444fd716bd3363a6605eae66dfec
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699681"
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