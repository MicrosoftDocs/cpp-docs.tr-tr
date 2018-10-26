---
title: Önişlemci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74cf3ff56f37375cd8f267e3541b78e2d76a18fa
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083314"
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

## <a name="see-also"></a>Ayrıca Bkz.

[C/C++ Ön İşlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)<br/>
[Çeviri Aşamaları](../preprocessor/phases-of-translation.md)