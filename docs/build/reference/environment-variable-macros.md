---
title: Ortam Değişkeni Makroları
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
ms.openlocfilehash: 7f7f8a05545658142001b75ac78975251185a033
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823495"
---
# <a name="environment-variable-macros"></a>Ortam Değişkeni Makroları

NMAKE oturumu başlamadan önce mevcut ortam değişkenleri için makro tanımlarını alır. İşletim sistemi ortamında bir değişken ayarlandıysa, NMAKE makrosu kullanılabilir. Devralınan adlarını büyük harfe dönüştürülür. Devralma, ön işleme önce gerçekleşir. Derleme görevleri dosyası içinde aynı ada sahip tüm makrolar geçersiz kılmak için ortam değişkenlerini devralınan makroları neden /E seçeneğini kullanın.

Ortam değişkeni makroları oturumda tanımlanabilir ve bu karşılık gelen ortam değişkenini değiştirir. Ayrıca, ortam değişkenleri KÜMESİ komutu değiştirebilirsiniz. Bir oturumda bir ortam değişkeni değiştirmek için Ayarla komutunu kullanarak karşılık gelen makrosu, ancak değiştirmez.

Örneğin:

```
PATH=$(PATH);\nonesuch

all:
    echo %PATH%
```

Bu örnekte, değiştirme `PATH` karşılık gelen ortam değişkenini değiştirir `PATH`; bunu ekler `\nonesuch` yolunuza.

Bir ortam değişkeni, bir derleme görevleri dosyasında sözdizimsel olarak yanlış olan dize olarak tanımlanırsa, makro oluşturulur ve herhangi bir uyarı oluşturulur. NMAKE bir değişken değerini bir dolar işareti ($) içeriyorsa, bir makro çağrısı başlangıcı olarak yorumlar. Makro kullanarak beklenmeyen davranışlara neden olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Özel NMAKE Makroları](special-nmake-macros.md)
