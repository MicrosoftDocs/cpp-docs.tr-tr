---
title: -TLBOUT (adı. TLB dosyası) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.TypeLibraryFile
- /tlbout
dev_langs:
- C++
helpviewer_keywords:
- tlb files, renaming
- TLBOUT linker option
- /TLBOUT linker option
- .tlb files, renaming
- -TLBOUT linker option
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1cc4103c387fe7a3dae68b642c10e326b361c54a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="tlbout-name-tlb-file"></a>/TLBOUT (.TLB Dosyası Adlandır)
```  
/TLBOUT:[path\]filename  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 *Yol*  
 .Tlb dosyası nerede oluşturulacağını bir mutlak veya göreli yol belirtimi.  
  
 *Dosya adı*  
 MIDL derleyici tarafından oluşturulan .tlb dosyası adını belirtir. Dosya uzantısı yok varsayılır; belirtin *filename*.tlb uzantısı istiyorsanız .tlb.  
  
## <a name="remarks"></a>Açıklamalar  
 /TLBOUT seçenek adını ve uzantısını .tlb dosyası belirtir.  
  
 MIDL derleyici projeleri bağlarken Visual C++ bağlayıcı tarafından çağrılır [Modülü](../../windows/module-cpp.md) özniteliği.  
  
 /TLBOUT belirtilmezse, .tlb dosyası adını alırsınız [/IDLOUT](../../build/reference/idlout-name-midl-output-files.md) *filename*. /IDLOUT belirtilmezse, vc70.tlb .tlb dosyası olarak adlandırılır.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **katıştırılmış IDL** özellik sayfası.  
  
4.  Değiştirme **tür kitaplığı** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)   
 [/ IGNOREIDL (öznitelikleri Mıdl'ye işleme)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/ MIDL (MIDL komut satırı seçeneklerini belirt)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Öznitelikli Program Derleme](../../windows/building-an-attributed-program.md)