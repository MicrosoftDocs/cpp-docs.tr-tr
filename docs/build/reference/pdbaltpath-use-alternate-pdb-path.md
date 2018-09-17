---
title: -PDBALTPATH (diğer PDB yolunu kullan) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /pdbaltpath
dev_langs:
- C++
helpviewer_keywords:
- .pdb files, path
- PDBALTPATH dumpbin option
- -PDBALTPATH dumpbin option
- /PDBALTPATH dumpbin option
- PDB files, path
ms.assetid: 72e200aa-e2c3-4ad8-b687-25528da1aaaf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72c494745fa33c8feeb4955f4542e9db5ed22307
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718399"
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

## <a name="see-also"></a>Ayrıca Bkz.

[DUMPBIN Seçenekleri](../../build/reference/dumpbin-options.md)<br/>
[/PDBPATH](../../build/reference/pdbpath.md)