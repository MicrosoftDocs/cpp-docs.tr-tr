---
title: Ön işlemci
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
ms.openlocfilehash: 883504810f1b659e28764a75ebc7cfda325920a5
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222239"
---
# <a name="preprocessor"></a>Ön işlemci

Önişlemci, bir kaynak dosyanın metnini, çeviri ilk aşamasının bir parçası olarak işleyen bir metin işlemcisidir. Ön işlemci, kaynak metni ayrıştırmaz, ancak makro çağrılarını bulmak için belirteçlerin ölçeğini keser. Derleyici ilk geçişinde önişlemcisi olağan şekilde çağırır ancak, Önişlemci, metni derlenmeden işlemek için ayrı olarak da çağrılabilir.

Ön işlemci üzerindeki başvuru malzemeleri aşağıdaki bölümleri içerir:

- [Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)

- [Önişlemci işleçleri](../preprocessor/preprocessor-operators.md)

- [Önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md)

- [Pragmalar](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

**Microsoft 'a özgü**

[/E](../build/reference/e-preprocess-to-stdout.md) veya [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) derleyici seçeneğini kullanarak, ön işlemden sonra kaynak kodunuzun bir listesini elde edebilirsiniz. Her iki seçenek de Önişlemci 'yi çağırır ve sonuçta elde edilen metni standart çıkış cihazına gönderir, bu da çoğu durumda konsoldur. İki seçenek `/E` arasındaki fark, yönergeleri de içerir `#line` ve `/EP` bu yönergeleri kaldırır.

**SON Microsoft 'a özgü**

##  <a name="_predir_special_terminology"></a>Özel terminoloji

Önişlemci belgelerinde, "bağımsız değişken" terimi bir işleve geçirilen varlığa başvurur. Bazı durumlarda, işlev çağrısında belirtilen bağımsız değişken ifadesini ve sırasıyla işlev tanımında belirtilen bağımsız değişken bildirimini açıklayan "gerçek" veya "biçimsel" tarafından değiştirilir.

"Değişken" terimi basit bir C-Type veri nesnesine başvurur. "Object" terimi hem nesneleri hem de C++ değişkenleri ifade eder; Bu, kapsamlı bir terimdir.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Önişlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)\
[Çeviri aşamaları](../preprocessor/phases-of-translation.md)
