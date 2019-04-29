---
title: /Zc:trigraphs (Trigrafları Değiştirme)
ms.date: 03/06/2018
f1_keywords:
- /Zc
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
ms.openlocfilehash: 7a20123603030dfe719cd8990018f795df137981
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316008"
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs (Trigrafları Değiştirme)

Zaman **/ZC: trigraphs** belirtilirse, derleyici, karşılık gelen bir noktalama karakteri kullanarak bir trigraf karakter dizisi yerini alır.

## <a name="syntax"></a>Sözdizimi

> **/Zc:trigraphs**[**-**]

## <a name="remarks"></a>Açıklamalar

A *trigraf* oluşur birbirini izleyen iki soru işareti ("??") üçüncü bir benzersiz karakter. C dil standardı trigrafları bazı noktalama karakterleri için uygun grafik sunumlar içermeyen bir karakter kümesini kullandırır kaynak dosyaları için destekler. Örneğin, derleyici trigrafları etkinleştirildiğinde, yerini alan "?? = "trigraf '#' karakterinden kullanarak. C ++ 14, olduğu gibi c trigrafları desteklenir Trigrafları, C ++ 17 standardına C++ dili kaldırır. C++ kodunda **/ZC: trigraphs** derleyici seçeneği tarafından karşılık gelen noktalama karakteri trigraf dizileri değiştirme sağlar. **/ZC:trigraphs-** trigraf değiştirme devre dışı bırakır.

**/ZC: trigraphs** seçeneği varsayılan olarak kapalıdır ve seçeneği ne zaman etkilenen [/ permissive-](permissive-standards-conformance.md) seçeneği belirtildi.

C/C++ trigrafları ve trigrafları kullanmayı gösteren bir örnek listesi için bkz: [Trigrafları](../../c-language/trigraphs.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/ZC: trigraphs** veya **/Zc:trigraphs-** seçip **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)<br/>
[Trigraflar](../../c-language/trigraphs.md)<br/>
