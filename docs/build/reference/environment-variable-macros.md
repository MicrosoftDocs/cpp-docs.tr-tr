---
title: Ortam Değişkeni Makroları
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
ms.openlocfilehash: a96b2de8469ace971d7fbc2707d3f786e873bb26
ms.sourcegitcommit: 6cb0670ca7d40e8ec55f162b8ce2847f5ae15f5c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67787337"
---
# <a name="environment-variable-macros"></a>Ortam Değişkeni Makroları

NMAKE oturumu başlamadan önce mevcut ortam değişkenleri için makro tanımlarını alır. İşletim sistemi ortamında bir değişken ayarlandıysa, NMAKE makrosu kullanılabilir. Devralınan adlarını büyük harfe dönüştürülür. Devralma, ön işleme önce gerçekleşir. Derleme görevleri dosyası içinde aynı ada sahip tüm makrolar geçersiz kılmak için ortam değişkenlerini devralınan makroları neden /E seçeneğini kullanın.

Ortam değişkeni makroları oturumda tanımlanabilir ve bu karşılık gelen ortam değişkenini değiştirir. Ayrıca, ortam değişkenleri KÜMESİ komutu değiştirebilirsiniz. Bir oturumda bir ortam değişkeni değiştirmek için Ayarla komutunu kullanarak karşılık gelen makrosu, ancak değiştirmez.

Örneğin:

```
PATH=$(PATH);\nonesuch

all:
    echo %%PATH%%
```

Bu örnekte, değiştirme `PATH` karşılık gelen ortam değişkenini değiştirir `PATH`; bunu ekler `\nonesuch` yolunuza.

Bir ortam değişkeni, bir derleme görevleri dosyasında sözdizimsel olarak yanlış olan dize olarak tanımlanırsa, makro oluşturulur ve herhangi bir uyarı oluşturulur. NMAKE bir değişken değerini bir dolar işareti ($) içeriyorsa, bir makro çağrısı başlangıcı olarak yorumlar. Makro kullanarak beklenmeyen davranışlara neden olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Özel NMAKE Makroları](special-nmake-macros.md)
