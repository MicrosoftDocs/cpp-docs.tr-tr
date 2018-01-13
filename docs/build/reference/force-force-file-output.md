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
ms.workload: cplusplus
ms.openlocfilehash: 8ec19beec52a217df1237de41d0bd81ab447a56d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)