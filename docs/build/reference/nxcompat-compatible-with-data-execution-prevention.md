---
title: /NXCOMPAT (Veri Yürütme Önlemesi ile Uyumlu)
ms.date: 12/29/2017
f1_keywords:
- /NXCOMPAT
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
ms.openlocfilehash: 7c788f5ec499f0edf0c44f1ff269af9767af6c08
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492671"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (Veri Yürütme Önlemesi ile Uyumlu)

Yürütülebilir bir dosyanın Windows Veri Yürütme Engellemesi özelliği ile uyumlu olduğunu gösterir.

## <a name="syntax"></a>Sözdizimi

> **/NXCOMPAT** [ **: NO**]

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak **/NXCOMPAT** açık olur.

**/NXCOMPAT: Hayır** , bir yürütülebilir dosyayı veri yürütme engellemesi ile uyumsuz olarak açıkça belirtmek için kullanılabilir.

Veri Yürütme Engellemesi hakkında daha fazla bilgi için şu makalelere bakın:

- [Veri Yürütme Engellemesi (DEP) özelliğinin ayrıntılı açıklaması](https://support.microsoft.com/help/875352/a-detailed-description-of-the-data-execution-prevention-dep-feature-in)

- [Veri Yürütme Engellemesi](/windows/win32/Memory/data-execution-prevention)

- [Veri Yürütme Engellemesi (Windows Embedded)](/previous-versions/windows/embedded/ms913190\(v=winembedded.5\))

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio 'da bu bağlayıcı seçeneğini ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > bağlayıcıkomut > **satırı** özellik sayfasını seçin.

1. **Ek seçenekler** kutusuna seçeneği girin. Değişikliği uygulamak için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
