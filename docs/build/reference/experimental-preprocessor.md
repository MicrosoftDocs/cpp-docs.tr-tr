---
title: '/Deneysel: Önişlemci (Önişlemci uyumluluk modunu etkinleştir)'
description: 'Standart bir uyumlu Önişlemci için deneysel derleyici desteğini etkinleştirmek üzere/deneysel: Önişlemci derleyici seçeneğini kullanın.'
ms.date: 09/10/2020
f1_keywords:
- preprocessor
- /experimental:preprocessor
helpviewer_keywords:
- preprocessor conformance
- /experimental:preprocessor
- Enable preprocessor conformance mode
ms.openlocfilehash: 9a98289434e7154d2ec8b8753d990876a8218acf
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042101"
---
# <a name="experimentalpreprocessor-enable-preprocessor-conformance-mode"></a>`/experimental:preprocessor` (Önişlemci uyumluluk modunu etkinleştir)

Bu seçenek, Visual Studio 2019 sürüm 16,5 ' den itibaren derleyici seçeneği ile birlikte kullanımdan kalkmıştır [`/Zc:preprocessor`](zc-preprocessor.md) . **`/experimental:preprocessor`** C99 Önişlemci özellikleri de dahil olmak üzere C++ 11 standartlarına daha yakından uyumlu olan deneysel, belirteç tabanlı bir Önişlemci sağlar. Daha fazla bilgi için bkz. [MSVC New Önişlemci Overview](../../preprocessor/preprocessor-experimental-overview.md).

## <a name="syntax"></a>Syntax

> **`/experimental:preprocessor`**\[**`-`**]

## <a name="remarks"></a>Açıklamalar

**`/experimental:preprocessor`** Deneysel uyumsuz Önişlemci 'yi etkinleştirmek için derleyici seçeneğini kullanın. **`/experimental:preprocessor-`** Geleneksel Önişlemci 'yi açıkça belirtmek için seçeneğini kullanabilirsiniz.

Bu **`/experimental:preprocessor`** seçenek, Visual Studio 2017 sürüm 15,8 ' den itibaren kullanılabilir. Visual Studio 2019 sürüm 16,5 ' den başlayarak yeni Önişlemci tamamlanmıştır ve [`/Zc:preprocessor`](zc-preprocessor.md) derleyici seçeneği altında kullanılabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini içerecek şekilde değiştirin *`/experimental:preprocessor`* ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)
