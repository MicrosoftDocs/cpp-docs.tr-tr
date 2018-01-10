---
title: "-FU (adı zorlanmış #using) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.ForcedUsingFiles
- /FU
- VC.Project.VCNMakeTool.ForcedUsingAssemblies
dev_langs: C++
helpviewer_keywords:
- -FU compiler option [C++]
- FU compiler option [C++]
- /FU compiler option [C++]
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 17b62859aaf0c9dc6b3313fbb726602b5b83a82c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fu-name-forced-using-file"></a>/FU (Zorlanan #using Dosyasını Adlandır)
Bir dosya adıyla geçirme alternatif olarak kullanabileceğiniz bir derleyici seçeneği [#using yönergesi](../../preprocessor/hash-using-directive-cpp.md) kaynak kodunda.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/FU file  
```  
  
## <a name="arguments"></a>Arguments  
 `file`  
 Bu derlemede başvurmak için meta veri dosyası belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 /FU anahtar yalnızca bir dosya adı alır. Birden çok dosya belirtmek için her birinde /FU kullanın.  
  
 Kullanıyorsanız [!INCLUDE[cppcli](../../build/reference/includes/cppcli_md.md)] ve kullanmak için meta veri başvuran [arkadaş derlemeleri](../../dotnet/friend-assemblies-cpp.md) özelliğini kullanamaz **/FU**. Kullanarak kodda metadata başvurmalıdır `#using`— ile birlikte `[as friend]` özniteliği. Arkadaş derlemeleri desteklenmez [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]).  
  
 Bir derlemeyi ya da ortak dil çalışma zamanı (CLR) için modülü oluşturma hakkında daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md). Yapı içinde hakkında bilgi için [!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)], bkz: [uygulamaları ve kitaplıkları derleme](../../cppcx/building-apps-and-libraries-c-cx.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **C/C++** klasör.  
  
3.  Seçin **Gelişmiş** özellik sayfası.  
  
4.  Değiştirme **zorla #using** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıktı dosyası (/ F) seçenekleri](../../build/reference/output-file-f-options.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)