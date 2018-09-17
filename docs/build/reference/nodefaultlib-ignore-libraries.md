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
ms.openlocfilehash: ae291677743cc05b0eeb85b41ebfa84e5a6e022e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726316"
---
# <a name="nodefaultlib-ignore-libraries"></a>/NODEFAULTLIB (Kitaplıkları Yoksay)

```
/NODEFAULTLIB[:library]
```

## <a name="arguments"></a>Arguments

*Kitaplık*<br/>
Dış başvurular çözümlediğinde yok saymak için bağlayıcı istediğiniz kitaplık.

## <a name="remarks"></a>Açıklamalar

/ Nodefaultlıb seçeneği bir veya daha fazla varsayılan kitaplığı dış başvuruların çözümlenmesi sırasında aradığı kitaplık listesinden kaldırmak için söyler.

Varsayılan kitaplıklarına başvurular içermeyen bir .obj dosyası oluşturmak için kullanın [/Zl (varsayılan kitaplık adını atla)](../../build/reference/zl-omit-default-library-name.md).

Varsayılan olarak, tüm varsayılan kitaplıkları/nodefaultlıb dış başvuruların çözümlenmesi sırasında aradığı kitaplık listesinden kaldırır. İsteğe bağlı *Kitaplığı* parametresi sağlar, belirtilen bir kitaplık veya kitaplıkları, dış başvuruların çözümlenmesi sırasında aradığı kitaplık listesinden kaldırın. Çıkarmak istediğiniz her bir kitaplık için bir/nodefaultlıb seçeneği belirtin.

Bağlayıcı ilk açıkça belirtin, ardından varsayılan kitaplıkları /DEFAULTLIB seçeneği ile belirtilen kitaplıklarda ve ardından adlı .obj dosyalarında varsayılan kitaplık arayarak başvuruları dış tanımlara çözümler.

/ NODEFAULTLIB:*Kitaplığı* geçersiz kılar [/DEFAULTLIB:](../../build/reference/defaultlib-specify-default-library.md)*Kitaplığı* olduğunda aynı *Kitaplığı* adı hem de belirtilir.

/ Nodefaultlıb kullanırsanız, örneğin, programınız C çalışma zamanı kitaplığı olmadan oluşturmak için ayrıca kullanmak zorunda kalabilirsiniz [/Entry](../../build/reference/entry-entry-point-symbol.md) programınızın giriş noktası (işlev) belirtmek için. Daha fazla bilgi için [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **giriş**özellik sayfası.

1. Seçin **tüm varsayılan kitaplıkları Yoksay** özelliği veya yoksayma istediğiniz kitaplıkların bir listesi belirtin **belirli bir kitaplığı Yoksay** özelliği. **Komut satırı** özellik sayfası bu özelliklerin yaptığınız değişikliklerin etkisini gösterir.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)