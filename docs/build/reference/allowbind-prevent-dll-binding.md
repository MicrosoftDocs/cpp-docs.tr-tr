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
ms.openlocfilehash: a0bff9ec6502aab5787c492a15e008bc29926163
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2018
ms.locfileid: "42465643"
---
# <a name="allowbind-prevent-dll-binding"></a>/ALLOWBIND (DLL Bağlamayı Önle)
```  
/ALLOWBIND[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 /ALLOWBIND:No görüntü bağlanması için izin verilmiyor Bind.exe'yi gösteren DLL üst bilgisinde bir bit ayarlar. Bir DLL dijital olarak imzalanmışsa bağlı olmasını istemeyebilirsiniz (bağlama imzayı).  
  
 Mevcut bir DLL ile /ALLOWBIND işlevselliği için düzenleyebilirsiniz [/ALLOWBIND](../../build/reference/allowbind.md) yardımcı programının EDITBIN seçeneği.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).  
  
2.  Genişletin **yapılandırma özellikleri**, **bağlayıcı**seçip **komut satırı**.  
  
3.  Girin `/ALLOWBIND:NO` içine **ek seçenekler**.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)   
 [BindImage işlevi](/windows/desktop/api/imagehlp/nf-imagehlp-bindimage)   
 [BindImageEx işlevi](/windows/desktop/api/imagehlp/nf-imagehlp-bindimageex)