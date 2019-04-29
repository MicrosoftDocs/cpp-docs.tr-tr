---
title: Yol Adını Belirtme
ms.date: 11/04/2016
helpviewer_keywords:
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
ms.openlocfilehash: dcff3610255c40f4e06201e52a53eb5dd965a4be
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317945"
---
# <a name="specifying-the-pathname"></a>Yol Adını Belirtme

Çıktı dosyası seçeneğin kabul bir *pathname* bağımsız değişkeni bir konum ve çıktı dosyası için bir ad belirtebilirsiniz. Bağımsız değişken, bir sürücü adı, dizin ve dosya adını içerebilir. Boşluk seçenek ve bağımsız değişken arasında izin verilir.

Varsa *pathname* dosya adı içeren bir uzantı derleyici çıkışı bir varsayılan uzantı sağlar. Varsa *pathname* bir dizin hiçbir dosya adı içerir derleyici belirtilen dizindeki varsayılan ada sahip bir dosya oluşturur. Varsayılan adı temel kaynak dosyasının adını ve çıkış dosyasının türüne göre varsayılan bir uzantı temel alır. Devre dışı bırakırsanız *pathname* tamamen, derleyici varsayılan bir dizin içinde bir varsayılan ada sahip bir dosya oluşturur.

Alternatif olarak, *pathname* bağımsız değişkeni, bir cihaz adı (AUX, CON, PRN veya NUL) yerine bir dosya adı olabilir. Seçeneğini ve cihaz adını veya bir virgül arasına bir boşluk, cihaz adı bir parçası olarak kullanmayın.

|Cihaz adı|Temsil eder|
|-----------------|----------------|
|AUX|Yardımcı cihaz|
|ONAYLA|Konsol|
|PRN|Yazıcı|
|NUL|Null cihazı (dosyası oluşturuldu)|

## <a name="example"></a>Örnek

Aşağıdaki komut satırını bir eşlem yazıcıya gönderir:

```
CL /FmPRN HELLO.CPP
```

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı Dosyası (/F) Seçenekleri](output-file-f-options.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
