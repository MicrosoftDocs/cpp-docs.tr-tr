---
title: "-ALLOWBIND (DLL bağlamayı önle) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.PreventDLLBinding
- /allowbind
dev_langs: C++
helpviewer_keywords:
- /ALLOWBIND linker option
- binding DLLs
- preventing DLL binding
- ALLOWBIND linker option
- -ALLOWBIND linker option
- DLLs [C++], preventing binding
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dc5d5827da555cc11a7fbc1417a9a0e26f953cea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="allowbind-prevent-dll-binding"></a>/ALLOWBIND (DLL Bağlamayı Önle)
```  
/ALLOWBIND[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 /ALLOWBIND:No biraz Bind.exe için görüntüyü bağlanması için izin verilmiyor gösteren bir DLL'in üstbilgisinde ayarlar. Dijital olarak imzalı olup olmadığını bağlanması için bir DLL istemeyebilirsiniz (bağlama imza geçersiz kılar).  
  
 Varolan bir DLL için /ALLOWBIND işlevselliği ile düzenleyebilirsiniz [/ALLOWBIND](../../build/reference/allowbind.md) EDITBIN yardımcı programının seçeneği.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri**, **bağlayıcı**seçip **komut satırı**.  
  
3.  Girin `/ALLOWBIND:NO` içine **ek seçenekler**.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)   
 [BindImage işlevi](http://msdn.microsoft.com/library/windows/desktop/ms679278.aspx)   
 [BindImageEx işlevi](http://msdn.microsoft.com/library/windows/desktop/ms679279.aspx)