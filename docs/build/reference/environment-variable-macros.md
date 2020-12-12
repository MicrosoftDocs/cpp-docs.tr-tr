---
description: 'Hakkında daha fazla bilgi edinin: Environment-Variable makrolar'
title: Ortam Değişkeni Makroları
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
ms.openlocfilehash: b7beaf8f3e98ea7447d798041f7531ed5da671ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192596"
---
# <a name="environment-variable-macros"></a>Ortam Değişkeni Makroları

NMAKE, oturum başlamadan önce var olan ortam değişkenlerine ait Makro tanımlarını devralır. İşletim sistemi ortamında bir değişken ayarlandıysa, bir NMAKE makrosu olarak kullanılabilir. Devralınan adlar büyük harfe dönüştürülür. Devralma, ön işlemden önce oluşur. Ortam değişkenlerinden devralınan makroların, derleme görevleri dosyası içindeki aynı ada sahip tüm makroları geçersiz kılmasını sağlamak için/E seçeneğini kullanın.

Ortam değişkeni makroları oturumunda yeniden tanımlanabilir ve bu, karşılık gelen ortam değişkenini değiştirir. Ayrıca, SET komutuyla ortam değişkenlerini de değiştirebilirsiniz. Bir oturumdaki ortam değişkenini değiştirmek için SET komutunu kullanmak, ilgili makroyu değiştirmez, ancak.

Örneğin:

```
PATH=$(PATH);\nonesuch

all:
    echo %%PATH%%
```

Bu örnekte, `PATH` karşılık gelen ortam değişkenini değiştirme,, `PATH` `\nonesuch` yolunuza ekler.

Bir ortam değişkeni, derleme görevleri dosyasında sözdizimsel olarak yanlış olacak bir dize olarak tanımlanmışsa, hiçbir makro oluşturulmaz ve hiçbir uyarı oluşturulmaz. Bir değişkenin değeri dolar işareti ($) içeriyorsa, NMAKE onu makro çağrısının başlangıcı olarak yorumlar. Makronun kullanılması beklenmeyen davranışlara neden olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Özel NMAKE makroları](special-nmake-macros.md)
