---
title: /NXCOMPAT (Veri Yürütme Önlemesi ile Uyumlu)
ms.date: 12/29/2017
f1_keywords:
- /NXCOMPAT
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
ms.openlocfilehash: a8550337189f9c92a1c8a8d86f2f9b2b829bbc3e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320376"
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

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. De seçeneği girin **ek seçenekler** kutusu. Seçin **Tamam** veya **Uygula** değişikliği uygulamak için.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
