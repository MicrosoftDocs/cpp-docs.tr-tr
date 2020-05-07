---
title: Köşeli Parantez İçindeki Dosya Adlarını Dahil Etme
ms.date: 11/04/2016
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
ms.openlocfilehash: 87de00814f58ed86ee33abdcf96dd210f418c5ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233105"
---
# <a name="including-bracketed-filenames"></a>Köşeli Parantez İçindeki Dosya Adlarını Dahil Etme

**ANSI 3.8.2 &** Includable kaynak dosyaları bulma yöntemi

Köşeli ayraçlar içine alınan dosya belirtimleri için, önişlemci ana dosyaların dizinlerinde arama yapmaz. Bir "üst" dosya, içinde [#include](../preprocessor/hash-include-directive-c-cpp.md) yönergesi olan dosyadır. Bunun yerine, derleyici komut satırında /I öğesinden sonra belirtilen dizinlerde dosyayı arayarak başlar. /I seçeneği yoksa veya başarısız olursa, ön işlemci, köşeli parantez içinde herhangi bir içerme dosyasını bulmak için ıNCLUDE ortam değişkenini kullanır. INCLUDE ortam değişkeni, noktalı virgülle (**;**) ayrılmış birden çok yol içerebilir. /I seçeneğinin bir parçası olarak birden fazla dizin görünürse veya ıNCLUDE ortam değişkeni içinde, Önişlemci bunları göründükleri sırada arar.

## <a name="see-also"></a>Ayrıca bkz.

[Ön işleme Yönergeleri](../c-language/preprocessing-directives.md)
