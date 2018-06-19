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
ms.openlocfilehash: dec06c3d6a8a981a059f173700e716431acc53a7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374095"
---
# <a name="pdbaltpath-use-alternate-pdb-path"></a>/PDBALTPATH (Diğer PDB Yolunu Kullan)
```  
/PDBALTPATH:pdb_file_name  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 *pdb_file_name*  
 .Pdb dosyasının yolu ve dosya adı.  
  
## <a name="remarks"></a>Açıklamalar  
 Derlenmiş ikili dosya biçiminde Program veritabanı (.pdb) dosyası için farklı bir konuma sağlamak için bu seçeneği kullanın. Normalde, bağlayıcı .pdb dosyasının konumunu bu üretir ikili dosyaları kaydeder. Farklı bir yol ve .pdb dosyası için dosya adı sağlamak için bu seçeneği kullanın. /PDBALTPATH ile sağlanan bilgileri konumu ya da gerçek .pdb dosyasının adını değiştirmez; Bağlayıcı ikili dosya içinde Yazar bilgilerini değiştirir. Bu, yapı bilgisayarın dosya yapısı bağımsız bir yol sağlamak üzere sağlar. Bir ağ yolu veya yol bilgisi olan bir dosyayı sağlamak için bu seçeneği için iki genel kullanım şeklindedir.  
  
 Değeri *pdb_file_name* bir ortam değişkeni rastgele bir dize olabilir veya **_PDB %**. Bağlayıcı bir ortam değişkeni gibi genişletecek **% SystemRoot %**, kendi değerine. Ortam değişkenleri bağlayıcı tanımlar **_PDB %** ve **_EXT %**. **% _PDB %** herhangi bir yol bilgisi olmadan gerçek .pdb dosyasının dosya adı için genişletir ve **_EXT %** oluşturulan yürütülebilir dosya uzantısıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DUMPBIN seçenekleri](../../build/reference/dumpbin-options.md)   
 [/PDBPATH](../../build/reference/pdbpath.md)