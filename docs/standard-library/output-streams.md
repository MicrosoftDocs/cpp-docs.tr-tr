---
title: Çıkış akışları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- output streams
ms.assetid: b49410e3-5caa-4153-9d0d-c4266408dc83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dde86faf5a19cfe57e445814b75bb3c8b82efbc4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854119"
---
# <a name="output-streams"></a>Çıkış Akışları

Bir çıkış akışı bayt için bir hedef nesnesidir. Üç en önemli çıkış akışı sınıflardır `ostream`, `ofstream`, ve `ostringstream`.

`ostream` Sınıfı, türetilmiş sınıf üzerinden `basic_ostream`, önceden tanımlanmış akışı nesneleri destekler:

- `cout` Standart çıktı

- `cerr` Standart sınırlı arabelleğe alma ile hata

- `clog` benzer şekilde `cerr` ancak tam arabelleğe alma

Nesneleri gelen oluşturulur nadiren `ostream`; önceden tanımlanmış nesneleri genellikle kullanılır. Bazı durumlarda, önceden tanımlanmış nesneler program başlatma işleminden sonra atayabilirsiniz. `ostream` Arabelleğe alınan veya arabellekten çıkarılan işlemi için yapılandırılabilir, sınıf, sıralı metin modu çıktı için uygundur. Tüm temel sınıf işlevselliğini `ios`, yer aldığı `ostream`. Sınıfın bir nesnesi oluşturmak, `ostream`, belirtmeniz gerekir bir `streambuf` oluşturucuya nesnesi.

`ofstream` Sınıfı, disk dosya çıktısı destekler. Yalnızca çıktı disk gerekiyorsa, sınıfın bir nesnesi oluşturmak `ofstream`. Belirleyebileceğiniz olup olmadığını `ofstream` nesneleri oluşturulurken, ikili veya metin modu verileri kabul `ofstream` nesne veya çağrılırken `open` nesnenin üye işlevi. Birçok biçimlendirme seçenekleri ve üye işlevlerini uygulamak `ofstream` nesneleri ve temel sınıflarının tüm işlevleri `ios` ve `ostream` bulunur.

Oluşturucuda bir dosya adı belirtirseniz, nesne oluşturulduğunda bu dosyayı otomatik olarak açılır. Aksi takdirde, kullanabileceğiniz `open` varsayılan oluşturucu çağırma sonra üye işlevi.

Çalışma zamanı işlevi gibi `sprintf_s`, `ostringstream` sınıfı, bellek içi dizeleri çıkışı destekler. Akış g/ç biçimlendirme kullanarak bellekte bir dize oluşturmak için sınıfın bir nesnesi oluşturmak `ostringstream`.

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
