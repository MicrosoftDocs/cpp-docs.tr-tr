---
title: /PDBALTPATH (Diğer PDB Yolunu Kullan)
ms.date: 11/04/2016
f1_keywords:
- /pdbaltpath
helpviewer_keywords:
- .pdb files, path
- PDBALTPATH dumpbin option
- -PDBALTPATH dumpbin option
- /PDBALTPATH dumpbin option
- PDB files, path
ms.assetid: 72e200aa-e2c3-4ad8-b687-25528da1aaaf
ms.openlocfilehash: 660e39a97b9fed0c5a9228fe011e7c0fa2566e68
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320038"
---
# <a name="pdbaltpath-use-alternate-pdb-path"></a>/PDBALTPATH (Diğer PDB Yolunu Kullan)

```
/PDBALTPATH:pdb_file_name
```

## <a name="arguments"></a>Arguments

*pdb_file_name*<br/>
.Pdb dosyasının yolunu ve dosya adı.

## <a name="remarks"></a>Açıklamalar

Program veritabanı (.pdb) dosyası, derlenmiş ikili dosyaları için alternatif bir konum sağlamak için bu seçeneği kullanın. Normalde, bağlayıcı .pdb dosyasının konumunu ürettiği içindeki ikili dosyaları kaydeder. Farklı yol ve dosya adı için .pdb dosyasını sağlamak için bu seçeneği kullanabilirsiniz. /PDBALTPATH ile sağlanan bilgiler, gerçek .pdb dosyasının adını ve konumunu değiştirmez. Bu bağlayıcı ikili dosyasına yazar bilgileri değiştirir. Bu, Yapı bilgisayarının dosya yapısı bağımsız bir yol sağlamak üzere sağlar. Bir ağ yolu veya hiçbir yol bilgisi olan bir dosyayı sağlamak için iki ortak kullandığı için bu seçeneği var.

Değerini *pdb_file_name* bir ortam değişkeni rastgele bir dize olabilir veya **_PDB %**. Bağlayıcı gibi bir ortam değişkeni genişletir **% SystemRoot %**, kendi değerine. Bağlayıcı ortam değişkenlerini tanımlar **_PDB %** ve **_EXT %**. **_PDB %** herhangi bir yol bilgisi olmadan gerçek .pdb dosyasının dosya adı genişletir ve **_EXT %** oluşturulan yürütülebilir dosya uzantısıdır.

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](dumpbin-options.md)<br/>
[/PDBPATH](pdbpath.md)
