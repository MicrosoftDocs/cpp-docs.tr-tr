---
title: -ALLOWBIND (DLL bağlamayı önle) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.PreventDLLBinding
- /allowbind
dev_langs:
- C++
helpviewer_keywords:
- /ALLOWBIND linker option
- binding DLLs
- preventing DLL binding
- ALLOWBIND linker option
- -ALLOWBIND linker option
- DLLs [C++], preventing binding
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31968e27c46cb5ea220a4cfe19c36820c4cf8444
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369646"
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