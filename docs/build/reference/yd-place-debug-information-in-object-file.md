---
title: "-Yd (hata ayıklama bilgilerini nesne dosyasına Yerleştir) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 419d97357fd3424d5de980f76c6758eaa47f3c7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="yd-place-debug-information-in-object-file"></a>/Yd (Hata Ayıklama Bilgilerini Nesne Dosyasına Yerleştir)
Hata ayıklama bilgisi tüm nesne dosyalarında tam meleri boşluk oluşturulan kullanıldığında önceden derlenmiş üst bilgi (.pch) dosyasından [/Yc](../../build/reference/yc-create-precompiled-header-file.md) ve [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md) seçenekleri. Kullanım dışı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Yd  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/YD** kullanım dışıdır; [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] tek .pdb dosyasına yazılırken birden fazla nesne artık destekler kullanmak **/zı** yerine. Kullanım dışı derleyici seçeneklerinin listesi için bkz: **kullanım dışı ve kaldırılmış derleyici seçenekleri** içinde [derleyici seçenekleri kategoriye göre listelenen](../../build/reference/compiler-options-listed-by-category.md).  
  
 Bir kitaplık içeren hata ayıklama bilgilerini dağıtmak gerekli olmadıkça kullanmak [/zı](../../build/reference/z7-zi-zi-debug-information-format.md) seçeneği yerine **/Z7** ve **/Yd**.  
  
 Her .obj dosyasında tam hata ayıklama bilgilerini depolamak, yalnızca hata ayıklama bilgileri içeren kitaplıkları dağıtmak gereklidir. Derleme yavaşlatır ve önemli ölçüde disk alanı gerektirir. Zaman **/Yc** ve **/Z7** olmadan kullanılan **/Yd**, derleyici .pch dosyasından oluşturulan ilk .obj dosyasında ortak hata ayıklama bilgileri depolar. Derleyici, bu bilgileri daha sonra .pch dosyasından oluşturulan .obj dosyaları içine eklemez; çapraz başvurular bilgi ekler. Kaç tane .obj dosyaları .pch dosyası kullanımı olsun, yalnızca bir .obj dosyası ortak hata ayıklama bilgileri içerir.  
  
 Bu varsayılan davranış sonuçlarında daha hızlı kez yapı ve disk alanı gereksinimlerini azaltır, ancak küçük değişiklikler ortak hata ayıklama bilgileri içeren .obj dosyasını yeniden oluşturma gerektiriyorsa istenmeyen. Bu durumda, derleyici, özgün .obj dosyaya çapraz başvurular içeren tüm .obj dosyaları yeniden oluşturmanız gerekir. Ayrıca, bir ortak .pch dosyası farklı projeler tarafından kullanılıyorsa, tek .obj dosyaya çapraz başvurular bağımlılık zordur.  
  
 Önceden derlenmiş üst bilgileri hakkında daha fazla bilgi için bkz:  
  
-   [/Y (önceden derlenmiş başlıklar)](../../build/reference/y-precompiled-headers.md)  
  
-   [Önceden Derlenmiş Üst Bilgi Dosyaları Oluşturma](../../build/reference/creating-precompiled-header-files.md)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="examples"></a>Örnekler  
 İki temel dosyaları, F.cpp ve bunlar her içeren G.cpp olduğunu varsayalım **#include** deyimleri:  
  
```  
#include "windows.h"  
#include "etc.h"  
```  
  
 Önceden derlenmiş üst bilgi aşağıdaki komut oluşturur dosya ETC.pch ve F.obj nesne dosyası:  
  
```  
CL /YcETC.H /Z7 F.CPP  
```  
  
 Nesne dosyası F.obj türü ve sembol bilgileri WINDOWS.h ve ETC.h (ve içerirler diğer üstbilgi dosyaları) içerir. Artık kaynak dosyaları G.cpp derlemek için önceden derlenmiş üst bilgi ETC.pch kullanabilirsiniz:  
  
```  
CL /YuETC.H /Z7 G.CPP  
```  
  
 Nesne dosyası G.obj önceden derlenmiş üst bilgi için hata ayıklama bilgilerini içermez ancak yalnızca bu bilgileri F.obj dosyasına başvuruyor. F.obj dosyasıyla bağlamanız gerekir unutmayın.  
  
 Önceden derlenmiş üstbilgi ile derlenmemiş varsa **/Z7**, bunu kullanarak sonraki derlemeleri içinde kullanmaya devam edebilirsiniz **/Z7**. Ancak, geçerli nesne dosyasında hata ayıklama bilgileri yerleştirilir ve işlevleri ve önceden derlenmiş üst bilgi tanımlanan türler için yerel semboller hata ayıklayıcısı için kullanılabilir değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)