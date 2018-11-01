---
title: Ortam Değişkeni Makroları
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
ms.openlocfilehash: 4691f89f1886b40637a0800ee8a6a94e4b4e06c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594304"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Özel NMAKE Makroları](../build/special-nmake-macros.md)