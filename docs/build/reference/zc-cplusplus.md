---
description: 'Şu konuda daha fazla bilgi edinin:/Zc: __cplusplus (güncelleştirilmiş __cplusplus makrosunu etkinleştir)'
title: /Zc:__cplusplus (Güncelleştirilmiş __cplusplus makrosunu etkinleştirme)
ms.date: 05/16/2019
f1_keywords:
- /Zc:__cplusplus
helpviewer_keywords:
- -Zc:__cplusplus compiler option (C++)
- __cplusplus macro (C++)
ms.openlocfilehash: 3aa5579a0315c2bba5e74a8a3c191801328fc589
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114682"
---
# <a name="zc__cplusplus-enable-updated-__cplusplus-macro"></a>/Zc:__cplusplus (Güncelleştirilmiş __cplusplus makrosunu etkinleştirme)

**/Zc: __cplusplus** derleyici seçeneği, **\_ \_ CPlusPlus** Önişlemci makrosunun son C++ dil standartları desteği için güncelleştirilmiş bir değer raporoluşturmasını sağlar. Varsayılan olarak, Visual Studio her zaman **\_ \_ CPlusPlus** önişlemci makrosu için "199711l" değerini döndürür.

## <a name="syntax"></a>Syntax

> **/Zc: __cplusplus**[ **-** ]

## <a name="remarks"></a>Açıklamalar

**\_ \_ CPlusPlus** önişlemci makrosu genellikle belirli bir C++ standardı sürümü için destek bildirmek üzere kullanılır. Varolan birçok kod, "199711L" ile eşleşen bu makronun değerine bağlı olarak göründüğünden, **/Zc: __cplusplus** derleyici seçeneğini kullanarak açıkça kabul etmediğiniz takdirde derleyici makronun değerini değiştirmez. **/Zc: __cplusplus** seçeneği Visual Studio 2017 sürüm 15,7 ' den başlayarak kullanılabilir ve varsayılan olarak kapalıdır. Visual Studio 'nun önceki sürümlerinde ve varsayılan olarak veya **/Zc: __cplusplus-** belirtilmişse, Visual Studio, **\_ \_ CPlusPlus** önişlemci makrosu için "199711l" değerini döndürür. [/Permissive-](permissive-standards-conformance.md) seçeneği **/zc: __cplusplus**'yi etkinleştirmez.

**/Zc: __cplusplus** seçeneği etkin olduğunda, **\_ \_ CPlusPlus** makrosu tarafından bildirilen değer [/STD](std-specify-language-standard-version.md) sürüm anahtarı ayarına bağlıdır. Bu tablo, makro için olası değerleri gösterir:

|/Zc: __cplusplus anahtarı|/std: c++ anahtarı|__cplusplus değeri|
|-|-|-|
Zc: __cplusplus|/std: c++ 14 (varsayılan)|201402L
Zc: __cplusplus|/std: c++ 17|201703L
Zc: __cplusplus|/std: c + + en son|201704L
Zc: __cplusplus-(devre dışı)|Herhangi bir değer|199711L
Belirtilmemiş|Herhangi bir değer|199711L

Derleyici, C++ 98, C++ 03 veya C++ 11 için standartlar anahtarlarını desteklemez.

Derleyici araç takımı üzerinde yapılan değişikliklerin daha ayrıntılı algılanması için [_MSC_VER](../../preprocessor/predefined-macros.md) önceden tanımlanmış makroyu kullanın. Visual Studio 2017 ve sonraki sürümlerindeki her araç takımı güncelleştirmesi için bu yerleşik makronun değeri artırılır. [_MSVC_LANG](../../preprocessor/predefined-macros.md) önceden tanımlanmış makro, **/zc: __cplusplus** seçeneğinin etkin mi yoksa devre dışı mı olduğunu standart sürümü bildiriyor. **/Zc: __cplusplus** etkinleştirildiğinde `__cplusplus == _MSVC_LANG` .

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio 'da Bu derleyici seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçeneklere:** bölmesine **/zc: __cplusplus** veya **/Zc: __cplusplus** ekleyin.

## <a name="see-also"></a>Ayrıca bkz.

- [/Zc (Uyumluluk)](zc-conformance.md)
- [/std (Dil standart sürümünü belirt)](std-specify-language-standard-version.md)
- [Önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md)
