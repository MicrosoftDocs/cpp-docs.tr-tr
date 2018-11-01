---
title: /NXCOMPAT (Veri Yürütme Önlemesi ile Uyumlu)
ms.date: 12/29/2017
f1_keywords:
- /NXCOMPAT
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
ms.openlocfilehash: 815719468e7dcf9325d19efe879b8f4ace040094
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490499"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (Veri Yürütme Önlemesi ile Uyumlu)

Bir yürütülebilir dosya Windows Veri Yürütme Engellemesi özelliği ile uyumlu olduğunu gösterir.

## <a name="syntax"></a>Sözdizimi

> **/ NXCOMPAT**[**: NO**]

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **/NXCOMPAT** açıktır.

**No** açıkça Veri Yürütme Engellemesi ile uyumsuz olarak yürütülebilen belirtmek için kullanılabilir.

Veri Yürütme engelleme hakkında daha fazla bilgi için şu makalelere bakın:

- [Veri Yürütme Engellemesi (DEP) özelliğinin ayrıntılı bir açıklaması](https://support.microsoft.com/help/875352/a-detailed-description-of-the-data-execution-prevention-dep-feature-in)

- [Veri Yürütme Engellemesi](/windows/desktop/Memory/data-execution-prevention)

- [Veri Yürütme Engellemesi (Windows Embedded)](/previous-versions/windows/embedded/ms913190\(v=winembedded.5\))

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio'da bu bağlayıcı seçeneğini ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. De seçeneği girin **ek seçenekler** kutusu. Seçin **Tamam** veya **Uygula** değişikliği uygulamak için.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
