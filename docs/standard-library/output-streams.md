---
title: Çıkış Akışları
ms.date: 11/04/2016
helpviewer_keywords:
- output streams
ms.assetid: b49410e3-5caa-4153-9d0d-c4266408dc83
ms.openlocfilehash: c64c46acca405f948e8314fb23944682adf09c43
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511117"
---
# <a name="output-streams"></a>Çıkış Akışları

Bir çıkış akışı nesnesine bir hedef bayt var. En önemli üç çıkış akışı sınıfları `ostream`, `ofstream`, ve `ostringstream`.

`ostream` Sınıfı, türetilmiş sınıf aracılığıyla `basic_ostream`, önceden tanımlanmış akışı nesneleri destekler:

- `cout` Standart çıktı

- `cerr` sınırlı arabelleğe alma ile standart hata

- `clog` benzer şekilde `cerr` ancak tam arabelleğe alma

Gelen nadiren nesneleri özniteliklerden `ostream`; önceden tanımlanmış nesneler genellikle kullanılır. Bazı durumlarda, önceden tanımlanmış nesnelere program başlatma işleminden sonra yeniden atayabilirsiniz. `ostream` Arabelleğe alınan veya arabellekten çıkarılan işlemi için yapılandırılabilir, sınıf, sıralı metin modunda çıkış için idealdir. Temel sınıfın tüm işlevselliği `ios`, dahildir `ostream`. Sınıfın bir nesnesi oluşturursanız `ostream`, belirtmelisiniz bir `streambuf` oluşturucusuna.

`ofstream` Sınıfı, disk dosya çıktısını destekler. Yalnızca çıktı bir disk gerekiyorsa, sınıfın bir nesnesi oluşturmak `ofstream`. Belirtebileceğiniz olup olmadığını `ofstream` nesneleri diziden oluşturulurken ikili veya metin modunda veri kabul `ofstream` nesne veya çağrılırken `open` nesnesinin üye işlevi. Çok sayıda biçimlendirme seçenekleri ve üye işlevler uygulamak `ofstream` nesneleri ve tüm temel sınıflar işlevselliğini `ios` ve `ostream` dahildir.

Oluşturucuda bir filename belirtirseniz, bir nesne oluşturulduğunda bu dosya otomatik olarak açılır. Aksi takdirde, kullanabileceğiniz `open` varsayılan oluşturucusu çağrılırken sonra üye işlevi.

Çalışma zamanı işlev gibi `sprintf_s`, `ostringstream` sınıfı, bellek içi dizelere çıkış destekler. Akış g/ç biçimlendirme kullanarak bellekte bir dize oluşturmak için sınıfın bir nesnesi oluşturmak `ostringstream`.

## <a name="in-this-section"></a>Bu Bölümde

[Çıkış Akış Nesnelerini Oluşturma](../standard-library/constructing-output-stream-objects.md)

[Ekleme İşleçlerini Kullanma ve Biçimi Denetleme](../standard-library/using-insertion-operators-and-controlling-format.md)

[Çıkış Dosya Akışı Üye İşlevleri](../standard-library/output-file-stream-member-functions.md)

[Ara Belleğe Almanın Etkileri](../standard-library/effects-of-buffering.md)

[İkili Çıktı Dosyaları](../standard-library/binary-output-files.md)

[Kendi Sınıflarınız İçin << İşleci Aşırı Yükleme](../standard-library/overloading-the-output-operator-for-your-own-classes.md)

[Bağımsız Değişkenler Olmadan Kendi Manipülatörlerinizi Yazma](../standard-library/writing-your-own-manipulators-without-arguments.md)

## <a name="see-also"></a>Ayrıca bkz.

[ofstream](../standard-library/basic-ofstream-class.md)<br/>
[ostringstream](../standard-library/basic-ostringstream-class.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
