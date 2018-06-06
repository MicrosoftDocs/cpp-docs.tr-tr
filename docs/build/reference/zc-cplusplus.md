---
title: /ZC:__cplusplus (etkinleştir güncelleştirilmiş __cplusplus makrosu)
ms.custom: ''
ms.date: 05/30/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:__cplusplus
dev_langs:
- C++
helpviewer_keywords:
- -Zc:__cplusplus compiler option (C++)
- __cplusplus macro (C++)
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a796794c0086b09c15ee88442e0fea4d1b114d98
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705797"
---
# <a name="zccplusplus-enable-updated-cplusplus-macro"></a>/ZC:__cplusplus (etkinleştir güncelleştirilmiş __cplusplus makrosu)

**/Zc:__cplusplus** derleyici seçeneği etkinleştirir  **\_ \_cplusplus** son C++ dili standartları desteği için güncelleştirilmiş bir değer bildirmek için önişlemci makrosu. Varsayılan olarak, Visual Studio her zaman değeri "199711 L" döndürür  **\_ \_cplusplus** önişlemci makrosu.

## <a name="syntax"></a>Sözdizimi

> **/ZC:__cplusplus**[**-**]

## <a name="remarks"></a>Açıklamalar

**\_ \_Cplusplus** önişlemci makrosu C++ standart, belirli bir sürümü için rapor desteklemek için yaygın olarak kullanılır. Var olan kodu çok sayıda göründüğünden "199711 L" eşleşen bu makrosu değerini bağımlı, açıkça kullanarak katılımı sürece derleyici makrosu değeri değişmez **/Zc:__cplusplus** derleyici seçeneği. **/Zc:__cplusplus** seçeneği Visual Studio 2017 sürüm 15.7 itibaren kullanılabilir ve varsayılan olarak kapalıdır. Visual Studio ve varsayılan olarak, eski sürümlerinde veya **/Zc:__cplusplus-** belirtilirse, Visual Studio "199711 L" değeri döndürür için  **\_ \_cplusplus** Önişlemci makrosu. [/ İzin veren-](permissive-standards-conformance.md) seçeneği sağlamaz **/Zc:__cplusplus**.

Zaman **/Zc:__cplusplus** seçeneği etkin tarafından bildirilen değer  **\_ \_cplusplus** makrosu bağımlı [/std](std-specify-language-standard-version.md) sürüm anahtarı ayar. Bu tabloda makrosu için olası değerler gösterilir:

|/ZC:__cplusplus anahtarı|/Std:c++ anahtarı|__cplusplus değeri|
|-|-|-|
ZC:__cplusplus|/ Std: c ++ 14 (varsayılan)|201402 M
ZC:__cplusplus|/ Std: c ++ 17|201703 M
ZC:__cplusplus|/ Std: c ++ son|201704 M
Zc:__cplusplus-(devre dışı)|Herhangi bir değer|199711 M
Belirtilmemiş.|Herhangi bir değer|199711 M

Derleyici, C ++ 98, C ++ 03 veya C ++ 11 standartları anahtarları desteklemiyor.

Derleyici araç setini değişiklikler geçirmiş algılanması için kullanmak [_MSC_VER](../../preprocessor/predefined-macros.md) önceden tanımlanmış makrosu. Bu yerleşik makrosu değeri, her bir araç takımı güncelleştirme Visual Studio 2017 ve sonraki sürümler için artırılır. [_MSVC_LANG](../../preprocessor/predefined-macros.md) önceden tanımlanmış makrosu raporları standart sürümü olup olmadığını **/Zc:__cplusplus** seçeneği etkin veya devre dışı. Zaman **/Zc:__cplusplus** etkin, `__cplusplus == _MSVC_LANG`.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio'da Bu derleyici seçeneği ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Ekleme **/Zc:__cplusplus** veya **/Zc:__cplusplus-** için **ek seçenekler:** bölmesi.

## <a name="see-also"></a>Ayrıca bkz.

- [/Zc (Uyumluluk)](zc-conformance.md)
- [/Std (belirt dil standard sürüm)](std-specify-language-standard-version.md)
- [Önceden tanımlı makrolar](../../preprocessor/predefined-macros.md)
