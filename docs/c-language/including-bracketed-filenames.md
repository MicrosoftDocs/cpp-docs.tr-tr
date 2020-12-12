---
description: 'Hakkında daha fazla bilgi edinin: köşeli parantez içine alınmış dosya adları'
title: Köşeli Parantez İçindeki Dosya Adlarını Dahil Etme
ms.date: 11/04/2016
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
ms.openlocfilehash: e54792b5feb7d5419896641c25a4367e97d80977
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182053"
---
# <a name="including-bracketed-filenames"></a>Köşeli Parantez İçindeki Dosya Adlarını Dahil Etme

**ANSI 3.8.2 &** Includable kaynak dosyaları bulma yöntemi

Köşeli ayraçlar içine alınan dosya belirtimleri için, önişlemci ana dosyaların dizinlerinde arama yapmaz. Bir "üst" dosya, içinde [#include](../preprocessor/hash-include-directive-c-cpp.md) yönergesi olan dosyadır. Bunun yerine, derleyici komut satırında /I öğesinden sonra belirtilen dizinlerde dosyayı arayarak başlar. /I seçeneği yoksa veya başarısız olursa, ön işlemci, köşeli parantez içinde herhangi bir içerme dosyasını bulmak için ıNCLUDE ortam değişkenini kullanır. INCLUDE ortam değişkeni, noktalı virgülle (**;**) ayrılmış birden çok yol içerebilir. /I seçeneğinin bir parçası olarak birden fazla dizin görünürse veya ıNCLUDE ortam değişkeni içinde, Önişlemci bunları göründükleri sırada arar.

## <a name="see-also"></a>Ayrıca bkz.

[Ön işleme yönergeleri](../c-language/preprocessing-directives.md)
