---
description: 'Daha fazla bilgi edinin: Önişlemci'
title: Ön işlemci
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
ms.openlocfilehash: dd79766777926871e7bbf849f96420ef37052eba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202086"
---
# <a name="preprocessor"></a>Ön işlemci

Önişlemci, bir kaynak dosyanın metnini, çeviri ilk aşamasının bir parçası olarak işleyen bir metin işlemcisidir. Ön işlemci, kaynak metni ayrıştırmaz, ancak makro çağrılarını bulmak için belirteçlerin ölçeğini keser. Derleyici ilk geçişinde önişlemcisi olağan şekilde çağırır ancak, Önişlemci, metni derlenmeden işlemek için ayrı olarak da çağrılabilir.

Ön işlemci üzerindeki başvuru malzemeleri aşağıdaki bölümleri içerir:

- [Ön işlemci yönergeleri](../preprocessor/preprocessor-directives.md)

- [Ön işlemci işleçleri](../preprocessor/preprocessor-operators.md)

- [Önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md)

- [Pragmalar](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

**Microsoft'a Özgü**

[/E](../build/reference/e-preprocess-to-stdout.md) veya [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) derleyici seçeneğini kullanarak, ön işlemden sonra kaynak kodunuzun bir listesini elde edebilirsiniz. Her iki seçenek de Önişlemci 'yi çağırır ve sonuçta elde edilen metni standart çıkış cihazına gönderir, bu da çoğu durumda konsoldur. İki seçenek arasındaki fark, `/E` yönergeleri de içerir `#line` ve `/EP` Bu yönergeleri kaldırır.

**SON Microsoft 'a özgü**

## <a name="special-terminology"></a><a name="_predir_special_terminology"></a> Özel terminoloji

Önişlemci belgelerinde, "bağımsız değişken" terimi bir işleve geçirilen varlığa başvurur. Bazı durumlarda, işlev çağrısında belirtilen bağımsız değişken ifadesini ve sırasıyla işlev tanımında belirtilen bağımsız değişken bildirimini açıklayan "gerçek" veya "biçimsel" tarafından değiştirilir.

"Değişken" terimi basit bir C-Type veri nesnesine başvurur. "Object" terimi hem C++ nesneleri hem de değişkenleri anlamına gelir; Bu, kapsamlı bir terimdir.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Önişlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)\
[Çeviri aşamaları](../preprocessor/phases-of-translation.md)
