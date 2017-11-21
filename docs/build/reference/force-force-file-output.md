---
title: "-FORCE (dosya çıktısını zorla) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
dev_langs: C++
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2990ff88e896c7cafb3ff8eb2d9acf149d7a90c0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="force-force-file-output"></a>/FORCE (Dosya Çıktısını Zorla)
```  
/FORCE:[MULTIPLE|UNRESOLVED]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 / Force seçeneği geçerli .exe dosyası oluşturmak için bağlayıcı söyler veya DLL bir simge başvurulan ancak olsa bile tanımlanan ya da tanımlanmış çarpın.  
  
 / Force seçeneği isteğe bağlı bir bağımsız değişken alabilir:  
  
-   BAĞLANTI bir simge için birden fazla tanım bulursa olup olmadığına bakılmaksızın bir çıktı dosyası oluşturmak için /Force:MULTIPLE kullanın.  
  
-   / Force kullanın: tanımlanmamış bir simge bağlantı bulursa olup olmadığına bakılmaksızın bir çıktı dosyası oluşturmak için ÇÖZÜMLENMEMİŞ. / FORCE: ÇÖZÜMLENMEMİŞ giriş noktası simgesi çözümlenmemiş ise göz ardı edilir.  
  
 / FORCE bağımsız değişken içermeyen iki birden çok anlamına gelir ve Çözülmemiş.  
  
 Bu seçenek ile oluşturulmuş bir dosya beklendiği gibi çalışmayabilir. / Force seçeneği belirtildiğinde bağlayıcı artımlı olarak bağlayacaksınız değil.  
  
 Bir modül ile derlenmiş ise **/CLR**, **/FORCE** görüntüyü oluşturmaz.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Seçenek içine türünü **ek seçenekler** kutusu.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)