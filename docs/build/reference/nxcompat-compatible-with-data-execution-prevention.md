---
title: /NXCOMPAT (Veri Yürütme Önlemesi ile Uyumlu)
description: Bir yürütülebilir dosyayı veri yürütmeC++ ENGELLEMESI (DEP) ile uyumlu olarak Işaretleyen Microsoft C/(MSVC)/NXCOMPAT bağlayıcı seçeneğini açıklar.
ms.date: 12/17/2019
f1_keywords:
- /NXCOMPAT
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
ms.openlocfilehash: f3a0906a49e3524fff3e1ef1643d1eceee28f169
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298993"
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (Veri Yürütme Önlemesi ile Uyumlu)

Yürütülebilir bir dosyanın Windows Veri Yürütme Engellemesi özelliği ile uyumlu olduğunu gösterir.

## <a name="syntax"></a>Sözdizimi

> **/NXCOMPAT**[ **: No**]

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak **/NXCOMPAT** açık olur.

**/NXCOMPAT: Hayır** , bir yürütülebilir dosyayı veri yürütme engellemesi ile uyumsuz olarak açıkça belirtmek için kullanılabilir.

Veri Yürütme Engellemesi hakkında daha fazla bilgi için şu makalelere bakın:

- [Veri Yürütme Engellemesi](/windows/win32/Memory/data-execution-prevention)

- [Veri Yürütme Engellemesi (Windows Embedded)](/previous-versions/windows/embedded/ms913190\(v=winembedded.5\))

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio 'da bu bağlayıcı seçeneğini ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** kutusuna seçeneği girin. Değişikliği uygulamak için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)\
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
