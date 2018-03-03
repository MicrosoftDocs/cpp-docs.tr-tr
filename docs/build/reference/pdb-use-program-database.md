---
title: "-PDB (Program veritabanını kullan) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /pdb
- VC.Project.VCLinkerTool.ProgramDatabaseFile
dev_langs:
- C++
helpviewer_keywords:
- -PDB linker option
- /PDB linker option
- PDB linker option
- PDB files, creating
- .pdb files, creating
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9b8b255e88a199397463d26d408d425234571552
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="pdb-use-program-database"></a>/PDB (Program Veritabanını Kullan)
```  
/PDB:filename  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 *Dosya adı*  
 Kullanıcı tarafından belirtilen veritabanı için bir ad bağlayıcı oluşturan program (PDB). Varsayılan adı değiştirir.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, zaman [/DEBUG](../../build/reference/debug-generate-debug-info.md) belirtilirse, bağlayıcı, hata ayıklama bilgilerini tutan bir program veritabanı (PDB) oluşturur. PDB için varsayılan dosya adı uzantısı .pdb ve program taban adına sahip.  
  
 / Pdb kullanın:*filename* PDB dosyası adını belirtmek için. / Debug belirtilmezse, / pdb seçeneği göz ardı edilir.  
  
 PDB dosyası 2 GB olabilir.  
  
 Daha fazla bilgi için bkz: [bağlayıcı girişi olarak .pdb dosyaları](../../build/reference/dot-pdb-files-as-linker-input.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **hata ayıklama** özellik sayfası.  
  
4.  Değiştirme **Program veritabanı dosya oluşturmak** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)