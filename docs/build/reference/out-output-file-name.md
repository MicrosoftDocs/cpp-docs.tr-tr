---
title: "-OUT (çıktı dosyası adı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.OutputFile
- /out
dev_langs: C++
helpviewer_keywords:
- output files, name linker option
- -OUT linker option
- OUT linker option
- /OUT C++ linker option
- linker [C++], output files
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1dbf2e353ffb060a7bba2f38617e8fa86a1ab9c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="out-output-file-name"></a>/OUT (Çıktı Dosyası Adı)
```  
/OUT:filename  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 *Dosya adı*  
 Bir kullanıcı tarafından belirtilen çıkış dosyasının adı. Varsayılan adı değiştirir.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan ad ve konum bağlayıcı oluşturur programın /OUT seçeneğini geçersiz kılar.  
  
 Varsayılan olarak, bağlayıcı temel belirtilen ilk .obj dosyasının adını ve uygun bir uzantı (.exe veya .dll) kullanarak dosya adı oluşturur.  
  
 Bu bir .mapfile veya içeri aktarma kitaplığı için varsayılan taban adı seçeneği. Ayrıntılar için bkz [oluşturmak Mapfile](../../build/reference/map-generate-mapfile.md) (/ eşleme) ve [/IMPLIB](../../build/reference/implib-name-import-library.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **genel** özellik sayfası.  
  
4.  Değiştirme **çıktı dosyası** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)