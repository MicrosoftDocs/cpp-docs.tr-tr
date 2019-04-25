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

**ANSI 3.8.2** dahil edilebilecek kaynak dosyalarını bulma yöntemi

Köşeli ayraçlar içine alınan dosya belirtimleri için, önişlemci ana dosyaların dizinlerinde arama yapmaz. "Üst" dosya içeren dosyadır [#include](../preprocessor/hash-include-directive-c-cpp.md) da yönergesi. Bunun yerine, derleyici komut satırında /I öğesinden sonra belirtilen dizinlerde dosyayı arayarak başlar. /I seçeneği mevcut değil veya başarısız olursa önişlemci açılı ayraç içindeki içerik dosyalarını bulmak için Include ortam değişkeni kullanır. INCLUDE ortam değişkeni, noktalı virgülle ayırarak birden fazla yol içerebilir (**;**). /I seçeneği veya INCLUDE ortam değişkeni içinde bir parçası olarak birden fazla dizin görünüyorsa önişlemci bunları göründükleri sırayla arar.

## <a name="see-also"></a>Ayrıca bkz.

[Ön işleme Yönergeleri](../c-language/preprocessing-directives.md)
