---
description: Daha fazla bilgi edinin:/NODEFAULTLIB (kitaplıkları Yoksay)
title: /NODEFAULTLIB (Kitaplıkları Yoksay)
ms.date: 03/26/2019
f1_keywords:
- VC.Project.VCLinkerTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLinkerTool.OVERWRITEDefaultLibraryNames
- /nodefaultlib
helpviewer_keywords:
- default libraries, removing
- -NODEFAULTLIB linker option
- libraries, ignore
- NODEFAULTLIB linker option
- /NODEFAULTLIB linker option
- ignore libraries linker option
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
ms.openlocfilehash: 1443d7ac1e17d464baa829d8297234ae80f3b998
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196717"
---
# <a name="nodefaultlib-ignore-libraries"></a>/NODEFAULTLIB (Kitaplıkları Yoksay)

> **/Nodefaultlib**[__:__*Library*]

## <a name="arguments"></a>Arguments

*Kitaplığı*<br/>
Bağlayıcının dış başvuruları çözümlediğinde yoksaymasını istediğiniz kitaplık.

## <a name="remarks"></a>Açıklamalar

/NODEFAULTLıB seçeneği bağlayıcıya, dış başvuruları çözümlerken aradığı kitaplık listesinden bir veya daha fazla varsayılan kitaplığı kaldırmasını söyler.

Varsayılan kitaplıklara başvuru içermeyen bir. obj dosyası oluşturmak için [/zl (varsayılan kitaplık adını atla)](zl-omit-default-library-name.md)kullanın.

Varsayılan olarak,/NODEFAULTLIB, dış başvuruları çözümlerken aradığı kitaplık listesinden tüm varsayılan kitaplıkları kaldırır. İsteğe bağlı *kitaplık* parametresi, dış başvuruları çözümlerken aradığı kitaplık listesinden belirtilen bir kitaplığı kaldırmanızı sağlar. Dışlamak istediğiniz her kitaplık için bir/NODEFAULTLIB seçeneği belirtin.

Bağlayıcı, önce açıkça belirttiğiniz kitaplıklarda, ardından [/defaultlib:](defaultlib-specify-default-library.md) seçeneğiyle belirtilen varsayılan kitaplıklarda ve. obj dosyalarında adlı varsayılan kitaplıklarda arama yaparak dış tanımlara yapılan başvuruları çözer.

/NODEFAULTLIB:*kitaplık* , her ikisinde de aynı *kitaplık* adı belirtildiğinde/defaultlib:*Library* geçersiz kılar.

Programınızı C çalışma zamanı kitaplığı olmadan derlemek için/NODEFAULTLIB kullanırsanız, programınızda giriş noktası işlevini belirtmek için [/Entry](entry-entry-point-symbol.md) de kullanmanız gerekebilir. Daha fazla bilgi için bkz. [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **girişi** özellik sayfasını seçin.

1. **Tüm varsayılan kitaplıkları Yoksay** özelliğini seçin. Ya da **belirli varsayılan kitaplıkları Yoksay** özelliğinde yoksaymak istediğiniz kitaplıkların noktalı virgülle ayrılmış bir listesini belirtin. **Komut satırı** Özellik sayfası, bu özelliklerde yaptığınız değişikliklerin etkisini gösterir.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A> . ve.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
