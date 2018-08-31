---
title: -MIDL (MIDL komut satırı seçeneklerini belirt) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /midl
- VC.Project.VCLinkerTool.MidlCommandFile
dev_langs:
- C++
helpviewer_keywords:
- -MIDL linker option
- MIDL
- /MIDL linker option
- MIDL linker option
- MIDL, command line options
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7fc5e4b0b3e19f9a71e1ada445181bede68d65a5
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222687"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL (MIDL Komut Satırı Seçeneklerini Belirt)
```  
/MIDL:@file  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 `file`  
 İçeren dosyanın adını [MIDL komut satırı seçeneklerini](/windows/desktop/Midl/general-midl-command-line-syntax).  
  
## <a name="remarks"></a>Açıklamalar  
 TLB dosya bir IDL dosyası dönüştürülmesi için tüm seçenekleri verilmelidir `file`; MIDL komut satırı seçenekleri, bağlayıcı'nın komut satırında belirtilemez. /MIDL belirtilmezse, MIDL Derleyici yalnızca IDL dosyası adı ve diğer bir seçenek ile çağrılır.  
  
 Bu dosya her satırda bir MIDL komut satırı seçeneği içermelidir.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklayın **bağlayıcı** klasör.  
  
3.  Tıklayın **katıştırılmış IDL** özellik sayfası.  
  
4.  Değiştirme **MIDL komutları** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)   
 [/ IDLOUT (MIDL çıktı dosyalarının adı)](../../build/reference/idlout-name-midl-output-files.md)   
 [/ IGNOREIDL (öznitelikleri Mıdl'ye işleme)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/ TLBOUT (adı. TLB dosyası)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [Öznitelikli Program Derleme](../../windows/building-an-attributed-program.md)