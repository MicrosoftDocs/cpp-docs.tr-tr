---
description: Şu konuda daha fazla bilgi edinin:/PDBPATH
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
ms.openlocfilehash: 41207d7cfce3d72ecb9517d9ad3af8bcd3f901d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226057"
---
# <a name="pdbpath"></a>/PDBPATH

```
/PDBPATH[:VERBOSE] filename
```

### <a name="parameters"></a>Parametreler

*filename*<br/>
Eşleşen. pdb dosyasını bulmak istediğiniz. dll veya. exe dosyasının adı.

**: VERBOSE**<br/>
Seçim . Pdb dosyasını bulmak için bir girişimde bulunuldu tüm dizinleri raporlar.

## <a name="remarks"></a>Açıklamalar

/PDBPATH, bilgisayarınızda hata ayıklayıcının bir. pdb dosyasını arayacağından aynı yolların yanı sıra, varsa. pdb dosyalarının dosya *adında* belirtilen dosyaya karşılık geldiğini rapor edecektir.

Visual Studio hata ayıklayıcısını kullanırken, hata ayıklayıcının hata ayıkladığınızda dosyanın farklı bir sürümü için bir. pdb dosyası kullandığı için bir sorunla karşılaşabilirsiniz.

/PDBPATH,. pdb dosyalarını aşağıdaki yollarla arar:

- Yürütülebilir dosyanın bulunduğu konumu kontrol edin.

- Yürütülebilir dosyanın çalıştırılabilire yazılmış konumunu kontrol edin. Bu genellikle görüntünün bağlandığı zaman konumudur.

- Visual Studio IDE 'de yapılandırılmış arama yolunu inceleyin.

- _NT_SYMBOL_PATH yolları ve _NT_ALT_SYMBOL_PATH ortam değişkenlerini kontrol edin.

- Windows dizinini iade edin.

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](dumpbin-options.md)<br/>
[/PDBALTPATH (diğer PDB yolunu kullan)](pdbaltpath-use-alternate-pdb-path.md)
