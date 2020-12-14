---
description: Şu konuda daha fazla bilgi edinin:/PDBALTPATH (diğer PDB yolunu kullan)
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
ms.openlocfilehash: f85a39fb4570773f01a98331e746f6b37b76c161
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226070"
---
# <a name="pdbaltpath-use-alternate-pdb-path"></a>/PDBALTPATH (Diğer PDB Yolunu Kullan)

```
/PDBALTPATH:pdb_file_name
```

## <a name="arguments"></a>Arguments

*pdb_file_name*<br/>
. Pdb dosyası için yol ve dosya adı.

## <a name="remarks"></a>Açıklamalar

Derlenmiş bir ikili dosyadaki program veritabanı (. pdb) dosyası için alternatif bir konum sağlamak üzere bu seçeneği kullanın. Normalde, bağlayıcı. pdb dosyasının konumunu, oluşturduğu ikililer olarak kaydeder. . Pdb dosyası için farklı bir yol ve dosya adı sağlamak üzere bu seçeneği kullanabilirsiniz. /PDBALTPATH ile birlikte sunulan bilgiler, gerçek. pdb dosyasının konumunu veya adını değiştirmez; bağlayıcının ikili dosyada yazdığı bilgileri değiştirir. Bu, yapı bilgisayarının dosya yapısından bağımsız bir yol sağlamanıza olanak sağlar. Bu seçeneğin iki yaygın kullanımları, bir ağ yolu veya yol bilgisi olmayan bir dosya sağlamaktır.

*Pdb_file_name* değeri rastgele bir dize, ortam değişkeni veya **% _PDB%** olabilir. Bağlayıcı, **% systemroot%** gibi bir ortam değişkenini değerine genişletmenizi sağlar. Bağlayıcı **% _PDB%** ve **% _ext%** ortam değişkenlerini tanımlar. % **_PDB%** , hiçbir yol bilgisi olmadan gerçek. pdb dosyasının dosya adına genişletilir ve **% _ext%** oluşturulan yürütülebilir dosyanın uzantısıdır.

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](dumpbin-options.md)<br/>
[/PDBPATH](pdbpath.md)
