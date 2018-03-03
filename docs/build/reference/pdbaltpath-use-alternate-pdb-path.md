---
title: "-PDBALTPATH (diğer PDB yolunu kullan) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9053bc206a465eb32d8007fb8d58d13d45eb4a0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [/ PDBPATH](../../build/reference/pdbpath.md)