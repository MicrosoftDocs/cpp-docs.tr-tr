---
title: "-Include (simge başvurularını zorla) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /include
- VC.Project.VCLinkerTool.ForceSymbolReferences
dev_langs: C++
helpviewer_keywords:
- INCLUDE linker option
- force symbol references linker option
- symbol references linker force
- /INCLUDE linker option
- symbols, add to symbol table
- -INCLUDE linker option
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 85fe7b45d17ea7263ca2445aaa97cbf007532e4a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="include-force-symbol-references"></a>/INCLUDE (Simge Başvurularını Zorla)
```  
/INCLUDE:symbol  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 `symbol`  
 Sembol tablosuna eklenecek bir sembol belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Exclude dışlama kuralı belirler seçenek belirtilen bir simgeyi sembol tablosuna eklemek için bağlayıcı söyler.  
  
 Birden çok simgeleri belirtmek için virgül (,), noktalı virgül (;) veya sembol adları arasında bir boşluk yazın. Exclude dışlama kuralı belirler komut satırında belirttiğiniz:`symbol` her simge için bir kez.  
  
 Bağlayıcı çözümler `symbol` programa sembol tanımını içeren nesneyi ekleyerek düzenleyin. Bu özellik, aksi takdirde programına bağlanmaması bir kitaplık nesnesi dahil etmek için kullanışlıdır.  
  
 Bu seçenek ile bir simge belirtme geçersiz kılar sembolün tarafından kaldırılmasını [/OPT:REF](../../build/reference/opt-optimizations.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **giriş** özellik sayfası.  
  
4.  Değiştirme **simge başvurularını zorla** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)