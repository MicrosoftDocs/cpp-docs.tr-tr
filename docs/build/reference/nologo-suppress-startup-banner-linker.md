---
title: "-NOLOGO (Başlangıç başlığını gösterme) (Bağlayıcı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.SuppressStartupBanner
- /nologo
dev_langs:
- C++
helpviewer_keywords:
- suppress startup banner linker option
- -NOLOGO linker option
- /NOLOGO linker option
- copyright message
- version numbers, preventing linker display
- banners, suppressing startup
- NOLOGO linker option
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c9cffaea51ad1ba17462292f4feae531361200d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="nologo-suppress-startup-banner-linker"></a>/NOLOGO (Başlangıç Başlığını Gösterme) (Bağlayıcı)
```  
/NOLOGO  
```  
  
## <a name="remarks"></a>Açıklamalar  
 / Nologo seçeneği telif hakkı iletisi ve sürüm numarasını görüntülenmesini engeller.  
  
 Bu seçenek, aynı zamanda komut dosyaları Yankı bastırır. Ayrıntılar için bkz [LINK komut dosyaları](../../build/reference/link-command-files.md).  
  
 Varsayılan olarak, bu bilgileri çıktı penceresinde bağlayıcı tarafından gönderilir. Komut satırında bunu standart çıktıya gönderilir ve bir dosyaya yönlendirilebilir.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Bu seçenek, yalnızca komut satırından kullanılmalıdır.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bu bağlayıcı seçeneği programlı olarak değiştirilemez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)