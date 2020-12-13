---
description: 'Daha fazla bilgi edinin: çıkış akışları'
title: Çıkış Akışları
ms.date: 11/04/2016
helpviewer_keywords:
- output streams
ms.assetid: b49410e3-5caa-4153-9d0d-c4266408dc83
ms.openlocfilehash: ec09a6bee1bcd2f329522b61950f3d051fb57889
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340872"
---
# <a name="output-streams"></a>Çıkış Akışları

Çıkış akışı nesnesi bayt için hedefdir. En önemli üç çıkış akışı sınıfı `ostream` , ve ' dir `ofstream` `ostringstream` .

`ostream`Türetilmiş sınıf aracılığıyla sınıfı, `basic_ostream` önceden tanımlanmış akış nesnelerini destekler:

- `cout` Standart çıkış

- `cerr` sınırlı arabelleğe alma ile standart hata

- `clog``cerr`, ancak tam arabelleğe alma ile benzerdir

Nesneler nadiren oluşturulur `ostream` ; önceden tanımlanmış nesneler genellikle kullanılır. Bazı durumlarda, program başlatıldıktan sonra önceden tanımlanmış nesneleri yeniden atayabilirsiniz. `ostream`Ara belleğe alınmış veya arabelleğe alınmamış işlem için yapılandırılabilen sınıf, sıralı metin modu çıktısına en uygun seçenektir. Temel sınıfının tüm işlevleri ' `ios` de bulunur `ostream` . Sınıfının bir nesnesini oluşturursanız `ostream` , oluşturucuya bir nesne belirtmeniz gerekir `streambuf` .

`ofstream`Sınıfı disk dosyası çıkışını destekler. Yalnızca çıkış diskine ihtiyacınız varsa, sınıfının bir nesnesini oluşturun `ofstream` . Nesne oluştururken ya da `ofstream` `ofstream` nesnenin üye işlevini çağırırken nesnelerin ikili veya metin modu verilerini kabul edip etmeyeceğini belirtebilirsiniz `open` . Birçok biçimlendirme seçeneği ve üye işlevleri nesneler için `ofstream` , temel sınıfların tüm işlevleri ve dahil olmak üzere `ios` geçerlidir `ostream` .

Oluşturucuda bir dosya adı belirtirseniz, nesne oluşturulduğunda bu dosya otomatik olarak açılır. Aksi takdirde, `open` varsayılan oluşturucuyu çağırdıktan sonra member işlevini kullanabilirsiniz.

Çalışma zamanı işlevi gibi `sprintf_s` , `ostringstream` sınıfı, bellek içi dizelerde çıktıyı destekler. G/ç akış biçimlendirmesini kullanarak bellekte bir dize oluşturmak için, sınıfının bir nesnesini oluşturun `ostringstream` .

## <a name="in-this-section"></a>Bu Bölümde

[Çıkış akış nesnelerini oluşturma](../standard-library/constructing-output-stream-objects.md)

[Ekleme Işleçlerini kullanma ve biçimi denetleme](../standard-library/using-insertion-operators-and-controlling-format.md)

[Çıkış dosyası akışı üye Işlevleri](../standard-library/output-file-stream-member-functions.md)

[Arabelleğe alma etkileri](../standard-library/effects-of-buffering.md)

[İkili çıktı dosyaları](../standard-library/binary-output-files.md)

[Kendi sınıflarınız için << Işlecini aşırı yükleme](../standard-library/overloading-the-output-operator-for-your-own-classes.md)

[Bağımsız değişkenler olmadan kendi Işleicinizi yazma](../standard-library/writing-your-own-manipulators-without-arguments.md)

## <a name="see-also"></a>Ayrıca bkz.

[ofstream](../standard-library/basic-ofstream-class.md)\
[ostringstream](../standard-library/basic-ostringstream-class.md)\
[iostream programlama](../standard-library/iostream-programming.md)
