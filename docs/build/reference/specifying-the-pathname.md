---
title: Yol Adını Belirtme
ms.date: 11/04/2016
helpviewer_keywords:
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
ms.openlocfilehash: f83adcb87994d13edd1c1579183377a365e2051e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638366"
---
# <a name="specifying-the-pathname"></a>Yol Adını Belirtme

Çıktı dosyası seçeneğin kabul bir *pathname* bağımsız değişkeni bir konum ve çıktı dosyası için bir ad belirtebilirsiniz. Bağımsız değişken, bir sürücü adı, dizin ve dosya adını içerebilir. Boşluk seçenek ve bağımsız değişken arasında izin verilir.

Varsa *pathname* dosya adı içeren bir uzantı derleyici çıkışı bir varsayılan uzantı sağlar. Varsa *pathname* bir dizin hiçbir dosya adı içerir derleyici belirtilen dizindeki varsayılan ada sahip bir dosya oluşturur. Varsayılan adı temel kaynak dosyasının adını ve çıkış dosyasının türüne göre varsayılan bir uzantı temel alır. Devre dışı bırakırsanız *pathname* tamamen, derleyici varsayılan bir dizin içinde bir varsayılan ada sahip bir dosya oluşturur.

Alternatif olarak, *pathname* bağımsız değişkeni, bir cihaz adı (AUX, CON, PRN veya NUL) yerine bir dosya adı olabilir. Seçeneğini ve cihaz adını veya bir virgül arasına bir boşluk, cihaz adı bir parçası olarak kullanmayın.

|Cihaz adı|Temsil eder|
|-----------------|----------------|
|YEDEK|Yardımcı cihaz|
|ONAYLA|Konsol|
|PRN|Yazıcı|
|NUL|Null cihazı (dosyası oluşturuldu)|

## <a name="example"></a>Örnek

Aşağıdaki komut satırını bir eşlem yazıcıya gönderir:

```
CL /FmPRN HELLO.CPP
```

## <a name="see-also"></a>Ayrıca Bkz.

[Çıktı Dosyası (/F) Seçenekleri](../../build/reference/output-file-f-options.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)