---
title: /Zc:trigraphs (Trigraphs Substitution) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /Zc
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5fdc5fc6432335e964a05185b7647b152a57d8f4
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs (Trigrafları Değiştirme)

Zaman **/ZC: trigraphs** belirtilirse, derleyici, karşılık gelen bir noktalama karakteri kullanarak trigrafı karakter dizisi yerini alır.

## <a name="syntax"></a>Sözdizimi

> **/Zc:trigraphs**[**-**]  

## <a name="remarks"></a>Açıklamalar

A *trigrafı* oluşur iki ardışık soru işaretleri ("??") benzersiz bir üçüncü karakter. C dili standart trigrafları uygun grafik sunumlarını bazı noktalama karakterleri içermeyen bir karakter kümesi kullanan kaynak dosyaları için destekler. Örneğin, trigrafları etkinleştirildiğinde, derleyici değiştirir "?? = "'#' karakteri kullanarak trigrafı. C ++ 14, olduğu gibi C. trigrafları desteklenir C ++ 17 standart trigrafları C++ dili kaldırır. C++ kodu **/ZC: trigraphs** derleyici seçeneği tarafından karşılık gelen noktalama karakteri trigrafı sıralarının değiştirme sağlar. **/ZC:trigraphs-** trigrafı değiştirme devre dışı bırakır.

**/ZC: trigraphs** seçeneği varsayılan olarak kapalıdır ve seçeneği ne zaman etkilenen [/ izin veren-](permissive-standards-conformance.md) seçeneği belirtildi.

C/C++ trigrafları ve trigrafları kullanmayı gösteren bir örnek listesi için bkz: [Trigrafları](../../c-language/trigraphs.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/ZC: trigraphs** veya **/Zc:trigraphs-** ve ardından **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>
[Trigraflar](../../c-language/trigraphs.md)<br/>
