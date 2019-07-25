---
title: Çıkış Akışları
ms.date: 11/04/2016
helpviewer_keywords:
- output streams
ms.assetid: b49410e3-5caa-4153-9d0d-c4266408dc83
ms.openlocfilehash: e650f9fd0bbc7ad483363706e632686e8ec3749e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450169"
---
# <a name="output-streams"></a>Çıkış Akışları

Çıkış akışı nesnesi bayt için hedefdir. En önemli üç çıkış akışı sınıfı, `ostream` `ofstream`ve `ostringstream`' dir.

Türetilmiş sınıf`basic_ostream`aracılığıyla sınıfı, önceden tanımlanmış akış nesnelerini destekler: `ostream`

- `cout`Standart çıkış

- `cerr`sınırlı arabelleğe alma ile standart hata

- `clog``cerr` , ancak tam arabelleğe alma ile benzerdir

Nesneler nadiren oluşturulur `ostream`; önceden tanımlanmış nesneler genellikle kullanılır. Bazı durumlarda, program başlatıldıktan sonra önceden tanımlanmış nesneleri yeniden atayabilirsiniz. Ara belleğe alınmış veya arabelleğe alınmamış işlem için yapılandırılabilen sınıf,sıralımetinmoduçıktısınaenuygunseçenektir.`ostream` Temel sınıfının `ios`tüm işlevleri ' de `ostream`bulunur. Sınıfının `ostream`bir nesnesini oluşturursanız, oluşturucuya bir `streambuf` nesne belirtmeniz gerekir.

`ofstream` Sınıfı disk dosyası çıkışını destekler. Yalnızca çıkış diskine ihtiyacınız varsa, sınıfının `ofstream`bir nesnesini oluşturun. Nesne oluştururken ya da `ofstream` nesnenin `open` üye işlevini çağırırken nesnelerin ikili veya metin modu verilerini `ofstream` kabul edip etmeyeceğini belirtebilirsiniz. Birçok biçimlendirme seçeneği ve üye işlevleri nesneler için `ofstream` , temel `ostream` sınıfların `ios` tüm işlevleri ve dahil olmak üzere geçerlidir.

Oluşturucuda bir dosya adı belirtirseniz, nesne oluşturulduğunda bu dosya otomatik olarak açılır. Aksi takdirde, varsayılan oluşturucuyu çağırdıktan sonra `open` member işlevini kullanabilirsiniz.

Çalışma zamanı işlevi `sprintf_s`gibi `ostringstream` , sınıfı, bellek içi dizelerde çıktıyı destekler. G/ç akış biçimlendirmesini kullanarak bellekte bir dize oluşturmak için, sınıfının `ostringstream`bir nesnesini oluşturun.

## <a name="in-this-section"></a>Bu Bölümde

[Çıkış Akış Nesnelerini Oluşturma](../standard-library/constructing-output-stream-objects.md)

[Ekleme İşleçlerini Kullanma ve Biçimi Denetleme](../standard-library/using-insertion-operators-and-controlling-format.md)

[Çıkış Dosya Akışı Üye İşlevleri](../standard-library/output-file-stream-member-functions.md)

[Ara Belleğe Almanın Etkileri](../standard-library/effects-of-buffering.md)

[İkili Çıktı Dosyaları](../standard-library/binary-output-files.md)

[Kendi Sınıflarınız İçin << İşleci Aşırı Yükleme](../standard-library/overloading-the-output-operator-for-your-own-classes.md)

[Bağımsız Değişkenler Olmadan Kendi Manipülatörlerinizi Yazma](../standard-library/writing-your-own-manipulators-without-arguments.md)

## <a name="see-also"></a>Ayrıca bkz.

[ofstream](../standard-library/basic-ofstream-class.md)\
[ostringstream](../standard-library/basic-ostringstream-class.md)\
[iostream Programlaması](../standard-library/iostream-programming.md)
