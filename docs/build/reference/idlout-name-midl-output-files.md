---
title: "-IDLOUT (MIDL çıktı dosyalarını Adlandır) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /idlout
- VC.Project.VCLinkerTool.MergedIDLBaseFileName
dev_langs: C++
helpviewer_keywords:
- MIDL, output file names
- .idl files, path
- MIDL
- /IDLOUT linker option
- IDL files, path
- -IDLOUT linker option
- IDLOUT linker option
ms.assetid: 10d00a6a-85b4-4de1-8732-e422c6931509
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8f9f798c31fc4b492565c3406f0cb26251a208d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="idlout-name-midl-output-files"></a>/IDLOUT (MIDL Çıktı Dosyalarını Adlandır)
```  
/IDLOUT:[path\]filename  
```  
  
## <a name="parameters"></a>Parametreler  
 *yol*  
 Bir mutlak veya göreli yol belirtimi. Bir yolu belirterek, yalnızca bir .idl dosyasının konumunu etkiler; diğer tüm dosyalar proje dizininde yer alır.  
  
 *Dosya adı*  
 MIDL derleyici tarafından oluşturulan .idl dosya adını belirtir. Dosya uzantısı yok varsayılır; belirtin *filename*.idl uzantı istiyorsanız .idl.  
  
## <a name="remarks"></a>Açıklamalar  
 /IDLOUT seçeneği .idl dosyasının uzantısını ve adını belirtir.  
  
 MIDL derleyici projeleri bağlarken Visual C++ bağlayıcı tarafından çağrılır [Modülü](../../windows/module-cpp.md) özniteliği.  
  
 / IDLOUT de MIDL derleyicisi ile ilişkili ve çıkış dosyalarının dosya adlarını belirtir:  
  
-   *filename*.tlb  
  
-   *Dosya adı*_p.c  
  
-   *Dosya adı*_i.c  
  
-   *filename*.h  
  
 *Dosya adı* /IDLOUT için geçirdiğiniz parametre. Varsa [/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md) belirtilirse, .tlb dosyası adını /TLBOUT elde *filename*.  
  
 /IDLOUT ne /TLBOUT belirtirseniz, bağlayıcı vc70.tlb, vc70.idl, vc70_p.c, vc70_i.c ve vc70.h oluşturur.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **katıştırılmış IDL** özellik sayfası.  
  
4.  Değiştirme **birleştirme IDL temel dosya adı** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)   
 [/ IGNOREIDL (öznitelikleri Mıdl'ye işleme)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/ MIDL (MIDL komut satırı seçeneklerini belirt)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Öznitelikli Program Derleme](../../windows/building-an-attributed-program.md)