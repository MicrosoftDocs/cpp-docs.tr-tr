---
description: 'Hakkında daha fazla bilgi edinin: yol adını belirtme'
title: Yol Adını Belirtme
ms.date: 11/04/2016
helpviewer_keywords:
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
ms.openlocfilehash: a8c55822bcb19864955ffa37ef2dd4cb18765ae5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224536"
---
# <a name="specifying-the-pathname"></a>Yol Adını Belirtme

Her çıkış dosyası seçeneği, çıkış dosyası için bir konum ve ad belirtebileceğiniz bir *PathName* bağımsız değişkeni kabul eder. Bağımsız değişken bir sürücü adı, dizin ve dosya adı içerebilir. Seçeneği ve bağımsız değişkeni arasında boşluk yapılmasına izin verilmez.

*Yol* adı uzantısı olmayan bir dosya adı içeriyorsa, derleyici çıktıyı varsayılan bir uzantı olarak verir. *Yol* adı bir dizin içeriyorsa ancak dosya adı yoksa, derleyici belirtilen dizinde varsayılan ada sahip bir dosya oluşturur. Varsayılan ad, kaynak dosyanın temel adına ve çıkış dosyasının türüne göre varsayılan bir uzantıya göre belirlenir. *Yol adını* tamamen devre dışı bırakırsanız, derleyici varsayılan bir dizinde varsayılan ada sahip bir dosya oluşturur.

Alternatif olarak, *PathName* bağımsız değişkeni bir dosya adı yerine bir cihaz adı (AUX, con, prn veya NUL) olabilir. Seçenek ile cihaz adı arasında bir boşluk ya da cihaz adının bir parçası olarak bir iki nokta üst üste kullanmayın.

|Cihaz adı|Temsil eder|
|-----------------|----------------|
|AUX|Yardımcı cihaz|
|CON|Konsol|
|PRN|Yazıcı|
|NUL|Null cihaz (dosya oluşturulmamış)|

## <a name="example"></a>Örnek

Aşağıdaki komut satırı, yazıcıya bir eşlem dosyası gönderir:

```
CL /FmPRN HELLO.CPP
```

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı dosyası (/F) seçenekleri](output-file-f-options.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
