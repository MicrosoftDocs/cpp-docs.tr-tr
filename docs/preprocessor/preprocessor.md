---
title: Ön işlemci
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
ms.openlocfilehash: b1443d88fdba470cb8ed5058c9a9012bfbdc5bc7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028580"
---
# <a name="preprocessor"></a>Ön işlemci
Önişlemci bir kaynak dosyasının metin çevirisi ilk aşamasının bir parçası yöneten bir metin işleyicisidir. Önişlemci kaynak metin ayrıştırılamadığından, ancak, bu belirteçleri makrosu çağrıları bulmak amacıyla halinde bölmek. Derleyici, normalde, ilk seferde önişlemci çağırır olsa da, önişlemci ayrıca ayrı olarak olmadan derleme metin işlemek için çağrılabilir.

Önişlemci ilgili başvuru malzemeleridir aşağıdaki bölümleri içerir:

- [Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)

- [Ön İşlemci işleçleri](../preprocessor/preprocessor-operators.md)

- [Önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md)

- [Pragmalar](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

**Microsoft'a özgü**

Kullanarak ön işleme sonra kaynak kodunuzda bir listesini alabilirsiniz [/E](../build/reference/e-preprocess-to-stdout.md) veya [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) derleyici seçeneği. İki seçenek de, önişlemci çağırın ve çoğu durumda, konsolu olan standart çıktı cihazına oluşturulan metin çıktısı. /E içerdiğini fark iki seçenek arasındaki `#line` yönergeleri ve /EP out bu yönergeler kaldırır.

**END Microsoft özgü**

##  <a name="_predir_special_terminology"></a> Özel terimleri

Önişlemci belgelerde, "değişken" terimi bir işleve geçirilen varlık anlamına gelir. Bazı durumlarda, "gerçek" veya "işlev çağrısında belirtilen bağımsız değişken ifadesi ve işlev tanımında sırasıyla belirtilen bağımsız değişken bildirimi açıklayan resmi," değiştirilir.

"Değişken" terimi, bir basit C türü veri nesnesine ifade eder. "Nesne" C++ nesnelerinin hem değişkenleri gösterir. Bu kapsamlı bir terimdir.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Ön İşlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)<br/>
[Çeviri Aşamaları](../preprocessor/phases-of-translation.md)