---
title: "-PDBSTRIPPED (özel simgeleri) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /pdbstripped
- VC.Project.VCLinkerTool.StripPrivateSymbols
dev_langs: C++
helpviewer_keywords:
- /PDBSTRIPPED linker option
- -PDBSTRIPPED linker option
- .pdb files, stripping private symbols
- PDB files, stripping private symbols
- PDBSTRIPPED linker option
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 73288ef6bf6881d946e4ec4bdd94e9b85cc0e81a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="pdbstripped-strip-private-symbols"></a>/PDBSTRIPPED (Özel Simgeleri Çıkart)
```  
/PDBSTRIPPED:pdb_file_name  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 *pdb_file_name*  
 Kullanıcı tarafından belirtilen veritabanı için bir ad bağlayıcı oluşturan kırpılmış program (PDB).  
  
## <a name="remarks"></a>Açıklamalar  
 PDB dosyası oluşturma seçenekleri program yansımanıza derleyici veya bağlayıcı yapılandırdığınızda /PDBSTRIPPED seçeneği ikinci bir program veritabanı (PDB) dosyası oluşturur ([/DEBUG](../../build/reference/debug-generate-debug-info.md), [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), /Zd veya /zı). Bu ikinci PDB dosyası, sevk müşterilerinize istemezsiniz simgeleri atlar. İkinci PDB dosyası yalnızca içerir:  
  
-   Genel semboller  
  
-   Nesne dosyaları ve katkıda bulundukları yürütülebilir dosya bölümünü listesi  
  
-   Çerçeve işaretçisi en iyi duruma getirme (FPO) hata ayıklama kayıtlarını yığın geçiş yapmak için kullanılan  
  
 Kırpılmış PDB dosyası içermez:  
  
-   Tür bilgileri  
  
-   Satır numarası bilgileri  
  
-   İşlevler, yerel ve statik verileri için olanlar gibi nesne başına dosya CodeView simgeleri  
  
 /PDBSTRIPPED kullandığınızda tam PDB dosyası hala oluşturulur.  
  
 PDB dosyası oluşturmazsanız /PDBSTRIPPED göz ardı edilir.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **hata ayıklama** özellik sayfası.  
  
4.  Değiştirme **özel simgeleri** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)