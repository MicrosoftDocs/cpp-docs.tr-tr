---
title: -PROFILE (performans araçları Profil Oluşturucusu) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.Profile
dev_langs:
- C++
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15379914b4c4852e3065d1abc03c2ce1b17fb044
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377124"
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (Performans Araçları Profil Oluşturucusu)
Performans araçları Profil Oluşturucu ile kullanılan bir çıktı dosyası oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/PROFILE  
```  
  
## <a name="remarks"></a>Açıklamalar  
 / PROFILE bağlayıcı şunlardan anlamına gelir:  
  
-   [/ OPT: BAŞVURU](../../build/reference/opt-optimizations.md)  
  
-   / OPT: NOICF  
  
-   [/ INCREMENTAL: HAYIR](../../build/reference/incremental-link-incrementally.md)  
  
-   [/ SABİT: HAYIR](../../build/reference/fixed-fixed-base-address.md)  
  
 / PROFILE bağlayıcı program görüntüyü yeniden konumlandırma bölüm oluşturmak neden olur.  Yeniden konumlandırma bölümü profil verileri almak için program görüntü dönüştürmek profil oluşturucu sağlar.  
  
 **/ PROFİL** yalnızca yalnızca (takım geliştirme) Enterprise sürümlerinde kullanılabilir.  PREfast hakkında daha fazla bilgi için bkz: [C/C++ genel bakış için Kod Analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-overview).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **bağlayıcı** düğümü.  
  
4.  Seçin **Gelişmiş** özellik sayfası.  
  
5.  Değiştirme **profil** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)