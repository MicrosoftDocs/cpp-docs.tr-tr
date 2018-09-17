---
title: -PROFILE (performans araçları Profiler) | Microsoft Docs
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
ms.openlocfilehash: 859ea4091502fa6c339a809a5b9e439c91462bd7
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707776"
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (Performans Araçları Profil Oluşturucusu)

Performans araçları Profilcisi ile kullanılabilecek bir çıkış dosyası üretir.

## <a name="syntax"></a>Sözdizimi

```
/PROFILE
```

## <a name="remarks"></a>Açıklamalar

/ PROFILE bağlayıcı şunlardan anlamına gelir:

- [/ OPT: REF](../../build/reference/opt-optimizations.md)

- / OPT: NOICF

- [/ INCREMENTAL: NO](../../build/reference/incremental-link-incrementally.md)

- [/ FIXED: NO](../../build/reference/fixed-fixed-base-address.md)

/ PROFILE bağlayıcı program görüntüyü bir yeniden konumlandırma bölümü oluşturmak neden olur.  Bir yeniden konumlandırma bölümü profil verilerini almak için program görüntüyü dönüştürmek profil oluşturucu sağlar.

**/ PROFİL** yalnızca (takım geliştirme) Enterprise sürümlerinde kullanılabilir.  PREfast hakkında daha fazla bilgi için bkz. [C/C++ genel bakış için Kod Analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-overview).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Genişletin **bağlayıcı** düğümü.

1. Seçin **Gelişmiş** özellik sayfası.

1. Değiştirme **profili** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)