---
title: -MD, -MT, -LD (çalışma zamanı kitaplığını kullan) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ld
- /mt
- VC.Project.VCCLWCECompilerTool.RuntimeLibrary
- VC.Project.VCCLCompilerTool.RuntimeLibrary
- /md
- /ml
dev_langs:
- C++
helpviewer_keywords:
- /MT compiler option [C++]
- -MD compiler option [C++]
- threading [C++], multithread compiler option
- MSVCRTD.lib
- MSVCRT.lib
- LIBCMT.lib
- MD compiler option [C++]
- /MD compiler option [C++]
- MT compiler option [C++]
- LD compiler option [C++]
- MDd compiler option [C++]
- -MDd compiler option [C++]
- LIBCD.lib
- -MTd compiler option [C++]
- MTd compiler option [C++]
- /MTd compiler option [C++]
- -LD compiler option [C++]
- /MDd compiler option [C++]
- multithread compiler option
- _STATIC_CPPLIB symbol
- LIBC.lib
- /LD compiler option [C++]
- DLLs [C++], compiler options
- LIBCMTD.lib
- -MT compiler option [C++]
ms.assetid: cf7ed652-dc3a-49b3-aab9-ad60e5395579
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b6fc814c1c2b0630a99cdaa19601be25c861580
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378265"
---
# <a name="md-mt-ld-use-run-time-library"></a>/MD, /MT, /LD (Çalışma Zamanı Kitaplığını Kullan)
Çok iş parçacıklı bir modülün bir DLL olup olmadığını belirtir ve çalışma zamanı kitaplığının perakende veya hata ayıklama sürümlerini gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/MD[d]  
/MT[d]  
/LD[d]  
```  
  
## <a name="remarks"></a>Açıklamalar  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**/MD**|Uygulamanın, çalışma zamanı kitaplığının çok iş parçacığına özgü ve DLL'ye özgü sürümlerini kullanmasını sağlar. Tanımlar `_MT` ve `_DLL` ve kitaplık adı MSVCRT.lib .obj dosyasına yerleştirmek derleyici neden olur.<br /><br /> Bu seçenekle derlenen uygulamalar, statik olarak MSVCRT.lib öğesine bağlıdır. Bu kitaplık, bağlayıcının dış başvuruları çözümlemesini sağlayan bir kod katmanı sağlar. Gerçek çalışma kod MSVCR içinde yer alan*versionnumber*. DLL MSVCRT.lib ile bağlantılı uygulamalar için çalışma zamanında kullanılabilir olması gerekir.|  
|**/MDd**|Tanımlar `_DEBUG`, `_MT`, ve `_DLL` ve çalışma zamanı kitaplığı hata ayıklama çoklu iş parçacığı kullanan ve DLL özgü sürümünü kullanmak için uygulamayı neden olur. Ayrıca, derleyicinin MSVCRTD.lib kitaplık adını .obj dosyasına yerleştirmesini sağlar.|  
|**/MT**|Uygulamanın, çalışma zamanı kitaplığının çok iş parçacığı, statik sürümünü kullanmasını sağlar. Tanımlar `_MT` ve böylece bağlayıcı LIBCMT.lib dış simgeleri çözümlemek için kullanacağı kitaplık adı LIBCMT.lib .obj dosyasına yerleştirmek derleyici neden olur.|  
|**/MTd**|Tanımlar `_DEBUG` ve `_MT`. Bu seçenek, aynı zamanda, derleyicinin LIBCMTD.lib kitaplık adını .obj dosyasına koyarak bağlayıcının dış simgeleri çözme sırasında LIBCMTD.lib kullanmasını sağlar.|  
|**/LD**|DLL oluşturur.<br /><br /> Geçişleri **/dll** bağlayıcı seçeneği. Bağlayıcı arar, ancak gerekli değildir, bir `DllMain` işlevi. Yazma varsa bir `DllMain` bağlayıcı işlevini ekler bir `DllMain` TRUE döndüren bir işlev.<br /><br /> DLL başlatma kodunu bağlar.<br /><br /> Komut satırında dışa aktarma (.exp) dosyası belirtilmezse, içeri aktarma kitaplığı (.lib) oluşturur. İçeri aktarma kitaplığını DLL'nizi çağıran uygulamalara bağlarsınız.<br /><br /> Yorumlar [/Fe (EXE dosyasını Adlandır)](../../build/reference/fe-name-exe-file.md) bir .exe dosyası yerine bir DLL adlandırma olarak. Varsayılan olarak, program adı olur *basename*.dll yerine *basename*.exe.<br /><br /> Gelir **/MT** açıkça belirtmediğiniz sürece **/MD**.|  
|**/LDd**|Hata ayıklama DLL'si oluşturur. Tanımlar `_MT` ve `_DEBUG`.|  
  
 C çalışma zamanı kitaplıkları ve hangi kitaplıkları ile derlerken kullanılan hakkında daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md), bkz: [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).  
  
 Belirli bir bağlayıcı çağrılması için geçirilen tüm modüllerin ile aynı çalışma zamanı kitaplığı derleyici seçeneği derlenmiştir gerekir (**/MD**, **/MT**, **/LD**).  
  
 Çalışma zamanı kitaplıkları hata ayıklama sürümleri kullanma hakkında daha fazla bilgi için bkz: [C çalışma zamanı kitaplığı başvurusu](../../c-runtime-library/c-run-time-library-reference.md).  
  
 Bilgi Bankası makalesi Q140584, uygun C çalışma zamanı kitaplığının nasıl seçileceğine de yer vermiştir.  
  
 DLL'ler hakkında daha fazla bilgi için bkz: [DLL'leri Visual C++'ta](../../build/dlls-in-visual-cpp.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **C/C++** klasör.  
  
3.  Seçin **kod oluşturma** özellik sayfası.  
  
4.  Değiştirme **çalışma zamanı kitaplığı** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeLibrary%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)