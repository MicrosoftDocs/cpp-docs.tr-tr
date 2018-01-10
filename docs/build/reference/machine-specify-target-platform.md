---
title: -Makine (hedef platformu belirt) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.TargetMachine
- /machine
dev_langs: C++
helpviewer_keywords:
- mapfiles, creating linker
- target platform
- -MACHINE linker option
- /MACHINE linker option
- MACHINE linker option
ms.assetid: 8d41bf4b-7e53-4ab9-9085-d852b08d31c2
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: edc3f4dc590ed5a8a763a4289fc5e15d8529e313
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="machine-specify-target-platform"></a>/MACHINE (Hedef Platformu Belirt)
```  
/MACHINE:{ARM|EBC|X64|X86}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 /MACHINE seçeneği programı hedef platformu belirtir.  
  
 Genellikle, /MACHINE seçeneği belirtmeniz gerekmez. BAĞLANTI .obj dosyaları makine türünden oluşturur. Ancak, bazı durumlarda, bağlantı sorunları ve makine türünü belirleyemiyor bir [Bağlayıcı araçları hatası LNK1113](../../error-messages/tool-errors/linker-tools-error-lnk1113.md). Böyle bir hata oluşursa, /MACHINE belirtin.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **Gelişmiş** özellik sayfası.  
  
4.  Değiştirme **hedef makine** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)