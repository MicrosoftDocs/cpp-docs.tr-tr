---
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
ms.openlocfilehash: 24528eb4c387c4cd0921ab089370d72b076ad640
ms.sourcegitcommit: 06fc71a46e3c4f6202a1c0bc604aa40611f50d36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/27/2019
ms.locfileid: "58508760"
---
# <a name="nodefaultlib-ignore-libraries"></a>/NODEFAULTLIB (Kitaplıkları Yoksay)

> **/ NODEFAULTLIB**[__:__*Kitaplığı*]

## <a name="arguments"></a>Arguments

*Kitaplık*<br/>
Dış başvurular çözümlediğinde yok saymak için bağlayıcı istediğiniz kitaplık.

## <a name="remarks"></a>Açıklamalar

/ Nodefaultlıb seçeneği bir veya daha fazla varsayılan kitaplığı dış başvuruların çözümlenmesi sırasında aradığı kitaplık listesinden kaldırmak için söyler.

Varsayılan kitaplıklar için başvuru içeren bir .obj dosyası oluşturmak için kullanın [/Zl (varsayılan kitaplık adını atla)](zl-omit-default-library-name.md).

Varsayılan olarak, tüm varsayılan kitaplıkları/nodefaultlıb dış başvuruların çözümlenmesi sırasında aradığı kitaplık listesinden kaldırır. İsteğe bağlı *Kitaplığı* parametresi belirtilen kitaplık dış başvuruların çözümlenmesi sırasında aradığı kitaplık listesinden kaldırmak olanak tanır. Çıkarmak istediğiniz her bir kitaplık için bir/nodefaultlıb seçeneği belirtin.

Bağlayıcı ilk açıkça belirtin, ardından kitaplıkları varsayılan belirtilen kitaplıklarda arama yaparak başvuruları dış tanımlara çözümler [/DEFAULTLIB:](defaultlib-specify-default-library.md) seçeneğini ve ardından varsayılan kitaplıkları adlı .obj dosyaları.

/ NODEFAULTLIB:*Kitaplığı* /DEFAULTLIB geçersiz kılar:*Kitaplığı* olduğunda aynı *Kitaplığı* adı hem de belirtilir.

/ Nodefaultlıb programınızın C çalışma zamanı kitaplığı olmadan oluşturmak için kullanıyorsanız, ayrıca kullanmak zorunda kalabilirsiniz [/Entry](entry-entry-point-symbol.md) programınızın giriş noktası işlevi belirtmek için. Daha fazla bilgi için [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **giriş** özellik sayfası.

1. Seçin **tüm varsayılan kitaplıkları Yoksay** özelliği. Ya da kitaplıkları yoksayma istediğiniz noktalı virgülle ayrılmış bir listesini belirtin **belirli varsayılan kitaplıkları Yoksay** özelliği. **Komut satırı** özellik sayfası, bu özelliklerin yaptığınız değişikliklerin etkisini gösterir.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
