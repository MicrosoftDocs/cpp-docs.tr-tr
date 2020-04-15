---
title: Ön işlemci
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
ms.openlocfilehash: 7188d7a6803c9eec109a59906cf0c016a460819d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337502"
---
# <a name="preprocessor"></a>Ön işlemci

Önişlemci, çevirinin ilk aşamasının bir parçası olarak kaynak dosyanın metnini manipüle eden bir metin işlemcisidir. Önişlemci kaynak metni ayrışdırmaz, ancak makro aramaları bulmak için belirteçlere ayırır. Derleyici normalde ilk geçişinde önişlemciyi çağırsa da, önişlemci metni derlemeden işlemek için ayrı ayrı çağrılabilir.

Önişlemcideki başvuru malzemesi aşağıdaki bölümleri içerir:

- [Ön işlemci yönergeleri](../preprocessor/preprocessor-directives.md)

- [Önişlemci operatörleri](../preprocessor/preprocessor-operators.md)

- [Önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md)

- [Pragmalar](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

**Microsoft'a Özgü**

[/E](../build/reference/e-preprocess-to-stdout.md) veya [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) derleyici seçeneğini kullanarak ön işlemden sonra kaynak kodunuzu listeleyebilirsiniz. Her iki seçenek de önişlemciyi çağırır ve ortaya çıkan metni çoğu durumda konsol olan standart çıktı aygıtına gönderir. İki seçenek arasındaki fark, `/E` `#line` yönergeleri içerir `/EP` ve bu yönergeleri siler.

**END Microsoft Özel**

## <a name="special-terminology"></a><a name="_predir_special_terminology"></a>Özel terminoloji

Önişlemci belgelerinde, "bağımsız değişken" terimi bir işleve geçirilen varlığı ifade eder. Bazı durumlarda, işlev çağrısında belirtilen bağımsız değişken ifadesini ve işlev tanımında belirtilen bağımsız değişken bildirimini açıklayan "gerçek" veya "biçimsel" olarak değiştirilir.

"Değişken" terimi basit bir C tipi veri nesnesini ifade eder. "Nesne" terimi hem C++ nesnelerini hem de değişkenleri ifade eder; Bu kapsayıcı bir terim.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ önişlemci başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)\
[Çevirinin aşamaları](../preprocessor/phases-of-translation.md)
