---
title: /Zc:trigraphs (Trigrafları Değiştirme)
description: Trigraf uygunluk desteğini denetleyen bir Microsoft C++ derleyici seçeneği.
ms.date: 07/25/2020
f1_keywords:
- /Zc:trigraphs
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
ms.openlocfilehash: e24f3d2f0064c3acc04b4c3774f47f6e442d5ddd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211859"
---
# <a name="zctrigraphs-trigraphs-substitution"></a>`/Zc:trigraphs`(Trigraf değiştirme)

Belirtildiğinde **`/Zc:trigraphs`** , derleyici bir trigraf karakter dizisini karşılık gelen noktalama karakterini kullanarak değiştirir.

## <a name="syntax"></a>Sözdizimi

> **`/Zc:trigraphs`**[**`-`**]

## <a name="remarks"></a>Açıklamalar

*Üçlü grafik* , birbirini izleyen iki soru işaretinden ( **`??`** ) ve ardından benzersiz bir üçüncü karakterle oluşur. C dil standardı, bazı noktalama karakterleri için kullanışlı grafik gösterimleri içermeyen bir karakter kümesi kullanan kaynak dosyalar için trigraf destekler. Örneğin, trigraf etkin olduğunda, derleyici **`??=`** üç karakteri kullanarak trigraf yerini alır **`#`** . C++ 14 aracılığıyla trigraf C 'de olduğu gibi desteklenir. C++ 17 standardı, C++ dilinden trigraf 'yi kaldırır. C++ kodunda, **`/Zc:trigraphs`** derleyici seçeneği, trigraf sıralarının karşılık gelen noktalama karakteriyle kullanılmasına izin vermez. **`/Zc:trigraphs-`** Üçlü grafik değişimini devre dışı bırakır.

Seçenek **`/Zc:trigraphs`** Varsayılan olarak kapalıdır ve seçenek belirtildiğinde seçenek etkilenmez [`/permissive-`](permissive-standards-conformance.md) .

C/C++ trigraf listesi ve trigraf nasıl kullanılacağını gösteren bir örnek için bkz. [trigraf](../../c-language/trigraphs.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini, veya içerecek şekilde **`/Zc:trigraphs`** değiştirin **`/Zc:trigraphs-`** ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[`/Zc`Uyumsuzlu](zc-conformance.md)<br/>
[Trigraflar](../../c-language/trigraphs.md)
