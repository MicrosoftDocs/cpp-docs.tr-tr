---
title: "-ERRORREPORT (dahili bağlayıcı hatalarını raporla) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ERRORREPORT
- VC.Project.VCLinkerTool.ErrorReporting
dev_langs: C++
helpviewer_keywords:
- /ERRORREPORT linker option
- ERRORREPORT linker option
- -ERRORREPORT linker option
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e6242457bb4da3e19700f5018b2a484bfa05630b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT (Dahili Bağlayıcı Hatalarını Raporla)
```  
/errorReport:[ none | prompt | queue | send ]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Doğrudan Microsoft'a iç derleyici hatası (çok) bilgileri sağlamanıza olanak tanır.  
  
 Seçenek **/errorReport:send** otomatik olarak hata bilgilerini Microsoft ancak başarı göndermeye çalıştığında kayıt defteri ayarlarına bağlıdır. Kayıt defterinde uygun değerleri ayarlama hakkında daha fazla bilgi için bkz: [Visual Studio 2008 komut satırı araçları'nda otomatik hata raporlamayı etkinleştirme](http://go.microsoft.com/fwlink/?LinkID=184695) MSDN Web sitesinde.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projeyi açın **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **yapılandırma özellikleri** klasör.  
  
3.  Tıklatın **bağlayıcı** klasör.  
  
4.  Tıklatın **Gelişmiş** özellik sayfası.  
  
5.  Değiştirme **hata raporlama**özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ errorreport (dahili derleme hatalarını raporla)](../../build/reference/errorreport-report-internal-compiler-errors.md)   
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)