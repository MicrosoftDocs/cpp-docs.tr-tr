---
title: -Yd (hata ayıklama bilgilerini nesne dosyasına Yerleştir) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /yd
dev_langs:
- C++
helpviewer_keywords:
- /Yd compiler option [C++]
- -Yd compiler option [C++]
- debugging [C++], debug information files
- Yd compiler option [C++]
ms.assetid: c5a699fe-65ce-461e-964c-7f5eb2a8320a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86cb8a42b77cd0a932530455f1125125a9f546d9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42585973"
---
# <a name="yd-place-debug-information-in-object-file"></a>/Yd (Hata Ayıklama Bilgilerini Nesne Dosyasına Yerleştir)
Hata ayıklama bilgileri tüm nesne dosyalarına tam oşluklar oluşturulan önceden derlenmiş üst bilgi (.pch) dosyasından ile kullanıldığında [/Yc](../../build/reference/yc-create-precompiled-header-file.md) ve [/z7](../../build/reference/z7-zi-zi-debug-information-format.md) seçenekleri. Kullanım dışı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Yd  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/YD** kullanım dışı; Visual C++ artık birden çok nesne tek .pdb dosyasına yazılırken destekler, kullanın **/zi** yerine. Kullanım dışı derleyici seçeneklerinin bir listesi için bkz. **kullanım dışı ve derleyici seçenekleri kaldırıldı** içinde [kategoriye göre listelenmiş derleyici seçenekleri](../../build/reference/compiler-options-listed-by-category.md).  
  
 Bir kitaplığı içeren hata ayıklama bilgileri dağıtmak gerekli olmadıkça kullanın [/zi](../../build/reference/z7-zi-zi-debug-information-format.md) seçeneği yerine **/z7** ve **/Yd**.  
  
 Her .obj dosyasında tam hata ayıklama bilgilerinin depolanması, yalnızca hata ayıklama bilgilerini içeren kitaplıkları dağıtmak gereklidir. Bu derleme yavaşlatır ve önemli ölçüde disk alanı gerektirir. Zaman **/Yc** ve **/z7** olmadan kullanılan **/Yd**, derleyici, .pch dosyasından oluşturulan ilk .obj dosyasındaki ortak hata ayıklama bilgilerini depolar. Derleyici, bu bilgileri .obj dosyaları daha sonra .pch dosyasından oluşturulan içine eklemez; Bu bilgilere çapraz başvurular ekler. .Pch dosyası Adlandır kaç .obj dosyaları kullanımı ne olursa olsun, yalnızca bir .obj dosyası genel hata ayıklama bilgileri içerir.  
  
 Bu varsayılan davranışı sonuçları daha hızlı derleme sürelerini ve disk alanı taleplerini azaltır olsa da, küçük bir değişiklik içeren genel hata ayıklama bilgileri .obj dosyasına yeniden gerektiriyorsa, istenmeyen. Bu durumda, derleyici, özgün .obj dosyasına çapraz başvuru içeren tüm .obj dosyalarını yeniden oluşturmanız gerekir. Ayrıca, bir ortak .pch dosyası farklı projeleri tarafından kullanılıyorsa, tek bir .obj dosyasına çapraz güvenme zordur.  
  
 Önceden derlenmiş üst bilgiler hakkında daha fazla bilgi için bkz:  
  
-   [/Y (Önceden Derlenmiş Üst Bilgiler)](../../build/reference/y-precompiled-headers.md)  
  
-   [Önceden Derlenmiş Üst Bilgi Dosyaları Oluşturma](../../build/reference/creating-precompiled-header-files.md)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).  
  
2.  Tıklayın **C/C++** klasör.  
  
3.  Tıklayın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneğini yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="examples"></a>Örnekler  
 F.cpp ve bunlar her içeren G.cpp, iki temel dosyası olduğunu varsayalım **#include** ifadeleri:  
  
```  
#include "windows.h"  
#include "etc.h"  
```  
  
 Aşağıdaki komut, önceden derlenmiş üst bilgi oluşturur. dosya ETC.pch ve F.obj nesne dosyası:  
  
```  
CL /YcETC.H /Z7 F.CPP  
```  
  
 Nesne dosyası F.obj türüne ve sembol bilgilerini WINDOWS.h ve ETC.h (ve içerdikleri diğer üst bilgi dosyaları) içerir. Artık G.cpp kaynak dosyasını derlemek için önceden derlenmiş üst bilgi ETC.pch kullanabilirsiniz:  
  
```  
CL /YuETC.H /Z7 G.CPP  
```  
  
 G.obj nesne dosyası önceden derlenmiş üst bilgi için hata ayıklama bilgisi içermez, ancak yalnızca bu bilgileri F.obj başvuruyor. F.obj dosyayla bağlantı unutmayın.  
  
 Varsa, önceden derlenmiş üst bilgi ile derlenmemiş **/z7**, onu kullanarak sonraki derlemelerde kullanmaya devam edebilirsiniz **/z7**. Ancak, hata ayıklama bilgileri geçerli nesne dosyasında yerleştirilir ve işlevleri ve derlenmiş üstbilgide tanımlanan türleri için yerel semboller hata ayıklayıcısı için kullanılabilir değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)