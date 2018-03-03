---
title: "-MANIFESTDEPENDENCY (bildirim bağımlılıklarını belirt) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalManifestDependencies
dev_langs:
- C++
helpviewer_keywords:
- MANIFESTDEPENDENCY linker option
- /MANIFESTDEPENDENCY linker option
- -MANIFESTDEPENDENCY linker option
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 01da83a57769dbe5b86c5bc2a73875231b769cdd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="manifestdependency-specify-manifest-dependencies"></a>/MANIFESTDEPENDENCY (Bildirim Bağımlılıklarını Belirt)
```  
/MANIFESTDEPENDENCY:manifest_dependency  
```  
  
## <a name="remarks"></a>Açıklamalar  
 / MANIFESTDEPENDENCY yerleştirilecek öznitelikleri belirtmenize olanak sağlar \<bağımlılık > bildirim dosyasının bölümü.  
  
 Bkz: [/MANIFEST (oluşturma yan yana derleme bildirimi)](../../build/reference/manifest-create-side-by-side-assembly-manifest.md) bildirim dosyasının nasıl oluşturulacağı hakkında bilgi için.  
  
 Daha fazla bilgi için \<bağımlılık > bölümüne bildirim dosyası [yayımcı yapılandırma dosyalarını](http://msdn.microsoft.com/library/aa375682).  
  
 / MANIFESTDEPENDENCY bilgi iki yoldan biriyle bağlayıcıya geçirilebilir:  
  
-   Komut satırında doğrudan (veya bir yanıt dosyası) /MANIFESTDEPENDENCY ile.  
  
-   Aracılığıyla [açıklama](../../preprocessor/comment-c-cpp.md) pragması.  
  
 Aşağıdaki örnek, pragma geçirilen /MANIFESTDEPENDENCY yorum gösterir,  
  
```  
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")  
```  
  
 Bu, bildirim dosyasındaki şu girdiyi sonuçlanır:  
  
```  
<dependency>  
  <dependentAssembly>  
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />  
  </dependentAssembly>  
</dependency>  
```  
  
 Aynı /MANIFESTDEPENDENCY açıklamaları komut satırında şu şekilde geçirilebilir:  
  
```  
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"  
```  
  
 Bağlayıcı /MANIFESTDEPENDENCY açıklamaları toplamak, yinelenen girişleri önlemek ve ardından sonuç XML dizesi bildirim dosyası ekleyin.  Çakışan girişleri bağlayıcı bulur, bildirim dosyası bozuk hale gelir ve uygulamayı başlatmak başarısız olur (bir giriş hatanın kaynağını belirten olan olay günlüğü için eklenebilir).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **bağlayıcı** düğümü.  
  
4.  Seçin **bildirim dosyası** özellik sayfası.  
  
5.  Değiştirme **ek bildirim bağımlılıklar** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)