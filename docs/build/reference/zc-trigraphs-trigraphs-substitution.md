---
title: /Zc:trigraphs (Trigrafları Değiştirme)
ms.date: 03/06/2018
f1_keywords:
- /Zc:trigraphs
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
ms.openlocfilehash: 0e4c98e09551d39e3ff7978767b21f1d2c5bb318
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438654"
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs (Trigrafları Değiştirme)

**/Zc: trigraf** belirtildiğinde, derleyici bir trigraf karakter dizisini karşılık gelen noktalama karakterini kullanarak değiştirir.

## <a name="syntax"></a>Sözdizimi

> **/Zc: trigraf**[ **-** ]

## <a name="remarks"></a>Açıklamalar

*Üçlü grafik* , birbirini izleyen iki soru işaretinden ("??") ve ardından benzersiz bir üçüncü karakterle oluşur. C dil standardı, bazı noktalama karakterleri için kullanışlı grafik gösterimleri içermeyen bir karakter kümesi kullanan kaynak dosyalar için üç aylık grafiği destekler. Örneğin, trigraf etkin olduğunda, derleyici "?? = "' # ' karakterini kullanarak trigraf. C++ 14 aracılığıyla trigraf C 'de olduğu gibi desteklenir. C++ 17 standardı, C++ dilin trigraf 'yi kaldırır. C++ Kodda, **/Zc: trigraf** derleyici seçeneği, trigraf sıralarının karşılık gelen noktalama karakteriyle kullanılmasına izin vermez. **/Zc: trigraf-** trigraf değişimini devre dışı bırakır.

**/Zc: trigraf** seçeneği varsayılan olarak kapalıdır ve [/Permissive-](permissive-standards-conformance.md) seçeneği belirtildiğinde seçenek etkilenmez.

C/C++ trigraf listesi ve trigraf nasıl kullanılacağını gösteren bir örnek için bkz. [trigraf](../../c-language/trigraphs.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **CC++ /**  > **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini **/Zc: trigraf** veya **/Zc: trigraf** içerecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)<br/>
[Trigraflar](../../c-language/trigraphs.md)<br/>
