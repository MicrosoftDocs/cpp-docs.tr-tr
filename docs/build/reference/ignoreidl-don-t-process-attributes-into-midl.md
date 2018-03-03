---
title: "-IGNOREIDL (tan &#39; MIDL t işlem öznitelikler) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.IgnoreEmbeddedIDL
- /ignoreidl
dev_langs:
- C++
helpviewer_keywords:
- IGNOREIDL linker option
- -IGNOREIDL linker option
- /IGNOREIDL linker option
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe2f1d33f9269380bf0d914d5805cce3b0a92b90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ignoreidl-don39t-process-attributes-into-midl"></a>/ IGNOREIDL (tan &#39; MIDL t işlem öznitelikler)
```  
/IGNOREIDL  
```  
  
## <a name="remarks"></a>Açıklamalar  
 /IGNOREIDL seçeneği herhangi bir belirtir [IDL öznitelikleri](../../windows/idl-attributes.md) kaynağında kod bir .idl dosyasına işlenmesi gerektiğini değil.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **katıştırılmış IDL** özellik sayfası.  
  
4.  Değiştirme **yoksay katıştırılmış IDL** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)   
 [/ IDLOUT (MIDL çıktı dosyalarını Adlandır)](../../build/reference/idlout-name-midl-output-files.md)   
 [/ TLBOUT (adı. TLB dosyası)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [/ MIDL (MIDL komut satırı seçeneklerini belirt)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Öznitelikli Program Derleme](../../windows/building-an-attributed-program.md)