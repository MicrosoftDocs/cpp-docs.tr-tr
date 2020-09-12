---
title: '/Zc: Önişlemci (Önişlemci uyumluluk modunu etkinleştir)'
description: 'Standart bir uyumlu Önişlemci için derleyici desteğini etkinleştirmek üzere/Zc: Önişlemci derleyici seçeneğini kullanın.'
ms.date: 09/10/2020
f1_keywords:
- preprocessor
- /Zc:preprocessor
helpviewer_keywords:
- preprocessor conformance
- /Zc:preprocessor
- Enable preprocessor conformance mode
ms.openlocfilehash: 356434e4892966b9a9304021dd5d8770dcc2f8b1
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042906"
---
# <a name="zcpreprocessor-enable-preprocessor-conformance-mode"></a>`/Zc:preprocessor` (Önişlemci uyumluluk modunu etkinleştir)

Bu seçenek, C99 ve C++ 11 ve sonraki standartlarına uyan belirteç tabanlı bir Önişlemci sağlar. Daha fazla bilgi için bkz. [MSVC New Önişlemci Overview](../../preprocessor/preprocessor-experimental-overview.md).

## <a name="syntax"></a>Syntax

> **`/Zc:preprocessor`**[**-**]

## <a name="remarks"></a>Açıklamalar

**`/Zc:preprocessor`** Uyumlu Önişlemci 'yi etkinleştirmek için derleyici seçeneğini kullanın. **`/Zc:preprocessor-`** Geleneksel (uyumsuz) Önişlemci 'yi açıkça belirtmek için seçeneğini kullanabilirsiniz.

Bu **`/Zc:preprocessor`** seçenek, Visual Studio 2019 sürüm 16,5 ' den itibaren kullanılabilir. Yeni Önişlemci seçeneğinin önceki, tamamlanmamış bir sürümü Visual Studio 2017 sürüm 15,8 ' den başlayarak Visual Studio 'nun sürümlerinde bulunabilir. Daha fazla bilgi için bkz. [`/experimental:preprocessor`](experimental-preprocessor.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini içerecek şekilde değiştirin *`/Zc:preprocessor`* ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)
