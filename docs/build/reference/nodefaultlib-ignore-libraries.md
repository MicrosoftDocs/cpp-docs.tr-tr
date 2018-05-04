---
title: -NODEFAULTLIB (kitaplıkları yoksay) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLinkerTool.OVERWRITEDefaultLibraryNames
- /nodefaultlib
dev_langs:
- C++
helpviewer_keywords:
- default libraries, removing
- -NODEFAULTLIB linker option
- libraries, ignore
- NODEFAULTLIB linker option
- /NODEFAULTLIB linker option
- ignore libraries linker option
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51caac10218d5f4d1787b2256875001ac32dc2b9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="nodefaultlib-ignore-libraries"></a>/NODEFAULTLIB (Kitaplıkları Yoksay)
```  
/NODEFAULTLIB[:library]   
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 *Kitaplığı*  
 Dış başvurular çözdüğünde yoksaymak için bağlayıcı istediğiniz kitaplık.  
  
## <a name="remarks"></a>Açıklamalar  
 Dış başvurular çözülürken arar kitaplıkları listesinden bir veya daha fazla varsayılan kitaplık kaldırmak için bağlayıcı /NODEFAULTLIB seçeneği söyler.  
  
 Varsayılan kitaplıklarına başvurular içermeyen bir .obj dosyası oluşturmak için kullanmak [/Zl (varsayılan kitaplık adını atla)](../../build/reference/zl-omit-default-library-name.md).  
  
 Varsayılan olarak, /NODEFAULTLIB tüm varsayılan kitaplık dış başvuruları çözülürken arar kitaplıkları listesinden kaldırır. İsteğe bağlı *Kitaplığı* parametresi belirtilen bir kitaplık veya kitaplıkları arar dış başvuruları çözülürken kitaplıkları listesinden kaldırmak olanak sağlar. Dışlamak istediğiniz her kitaplığın bir /NODEFAULTLIB seçeneğini belirtin.  
  
 Bağlayıcı ilk açıkça belirtin, ardından varsayılan kitaplıkları /DEFAULTLIB seçeneğiyle belirtilen kitaplıkları ve ardından .obj dosyaları adlı varsayılan kitaplıklarında arayarak dış tanımları başvurular çözümler.  
  
 / NODEFAULTLIB:*Kitaplığı* geçersiz kılmaları [/DEFAULTLIB:](../../build/reference/defaultlib-specify-default-library.md)*Kitaplığı* zaman aynı *Kitaplığı* adı hem de belirtilir.  
  
 /NODEFAULTLIB kullanırsanız, örneğin, C çalışma zamanı kitaplığı olmadan, program oluşturmak için aynı zamanda kullanmak zorunda kalabilirsiniz [/Entry](../../build/reference/entry-entry-point-symbol.md) programınızın giriş noktası (işlev) belirtmek için. Daha fazla bilgi için bkz: [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **giriş**özellik sayfası.  
  
4.  Seçin **tüm varsayılan kitaplıkları Yoksay** özelliği veya içinde yoksay istediğiniz kitaplıkları listesini belirtin **yoksay belirli Kitaplığı** özelliği. **Komut satırı** özellik sayfası, bu özellikler yaptığınız değişikliklerin etkisini gösterir.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)