---
title: '/Deneysel: Önişlemci (Önişlemci uyumluluk modunu etkinleştir)'
description: 'Standart bir uyumlu Önişlemci için deneysel derleyici desteğini etkinleştirmek üzere/deneysel: Önişlemci derleyici seçeneğini kullanın.'
ms.date: 10/31/2019
f1_keywords:
- preprocessor
- /experimental:preprocessor
helpviewer_keywords:
- preprocessor conformance
- /experimental:preprocessor
- Enable preprocessor conformance mode
ms.openlocfilehash: cb1ac63d2c12083975139455d8625544cb419adf
ms.sourcegitcommit: 2362d15b5eb18d27773c3f7522da3d0eed9e2571
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73754047"
---
# <a name="experimentalpreprocessor-enable-preprocessor-conformance-mode"></a>/Deneysel: Önişlemci (Önişlemci uyumluluk modunu etkinleştir)

Bu seçenek, C99 Önişlemci özellikleri de dahil olmak üzere C++ 11 standartlarına daha yakından uyumlu olan deneysel, belirteç tabanlı bir Önişlemci sağlar. Daha fazla bilgi için bkz. [MSVC deneysel Önişlemci genel bakış](../../preprocessor/preprocessor-experimental-overview.md).

## <a name="syntax"></a>Sözdizimi

> **/deneysel: Önişlemci**[ **-** ]

## <a name="remarks"></a>Açıklamalar

Deneysel uyumlu Önişlemci 'yi etkinleştirmek için **/deneysel: Önişlemci** derleyici seçeneğini kullanın. Geleneksel Önişlemci 'yi açıkça belirtmek için **/deneysel: Önişlemci-** seçeneğini kullanabilirsiniz.

**/Deneysel: Önişlemci** seçeneği, Visual Studio 2017 sürüm 15,8 ' den başlayarak kullanılabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **CC++ /**  > **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini **/deneysel: Önişlemci** içerecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)
