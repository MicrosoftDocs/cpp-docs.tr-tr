---
title: "-DEFAULTLIB (varsayılan kitaplığı belirt) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
dev_langs: C++
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0f130dd9f445f51f68f24946bc9d541e95581b9f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB (Varsayılan Kitaplığı Belirt)
```  
/DEFAULTLIB:library  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 *Kitaplığı*  
 Dış başvurular çözülürken aramak için bir kitaplık adı.  
  
## <a name="remarks"></a>Açıklamalar  
 /DEFAULTLIB seçeneği bir ekler *Kitaplığı* bağlantı başvuruları çözülürken arar kitaplıkları listesi. Belirtilen komut satırında ve varsayılan kitaplık .obj dosyaları adlı önce kitaplıkları sonra /DEFAULTLIB ile belirtilen bir kitaplık aranır.  
  
 [Tüm varsayılan kitaplıkları Yoksay](../../build/reference/nodefaultlib-ignore-libraries.md) (/ NODEFAULTLIB) seçeneğini geçersiz kılar /DEFAULTLIB:*Kitaplığı*. [Kitaplıkları Yoksay](../../build/reference/nodefaultlib-ignore-libraries.md) (/ NODEFAULTLIB:*Kitaplığı*) seçeneğini geçersiz kılar /DEFAULTLIB:*Kitaplığı* zaman aynı *Kitaplığı* adı ikisi de belirtilmiş.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
-   Bu bağlayıcı seçeneği Visual Studio geliştirme ortamından kullanılabilir değil. Kitaplığa bağlantı aşamasına eklemek için kullanın **ek bağımlılıklar** özelliğinden **giriş** özellik sayfası.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)