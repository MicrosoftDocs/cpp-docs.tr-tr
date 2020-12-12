---
description: Daha fazla bilgi için bkz. giriş akışları
title: Giriş Akışları
ms.date: 11/04/2016
helpviewer_keywords:
- reading data [C++], from input streams
- data [C++], reading from input stream
- input streams
- input stream objects
ms.assetid: f14d8954-8f8c-4c3c-8b99-14ddb3683f94
ms.openlocfilehash: f7e6d41b904b2d28893637681e3c751d24aef441
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323968"
---
# <a name="input-streams"></a>Giriş Akışları

Giriş akışı nesnesi bayt kaynağıdır. En önemli üç giriş akışı sınıfı [IStream](../standard-library/basic-istream-class.md), [ifstream](../standard-library/basic-ifstream-class.md)ve [ıtringstream](../standard-library/basic-istringstream-class.md)' dir.

`istream`Sınıf, ardışık metin modu girişi için en iyi seçenektir. `istream`Ara belleğe alınmış veya arabelleğe alınmamış işlem için sınıfın nesnelerini yapılandırabilirsiniz. Temel sınıfının tüm işlevleri ' `ios` de bulunur `istream` . Sınıfından nadiren nesne oluşturacaksınız `istream` . Bunun yerine, genellikle `cin` [ostream](../standard-library/basic-ostream-class.md)sınıfının bir nesnesi olan önceden tanımlanmış nesneyi kullanırsınız. Bazı durumlarda, `cin` Program başlatıldıktan sonra diğer Stream nesnelerine atayabilirsiniz.

`ifstream`Sınıfı, disk dosyası girişini destekler. Yalnızca giriş diski dosyası gerekiyorsa, sınıfının bir nesnesini oluşturun `ifstream` . İkili veya metin modu verileri belirtebilirsiniz. Oluşturucuda bir dosya adı belirtirseniz, nesne oluşturulduğunda dosya otomatik olarak açılır. Aksi takdirde, `open` varsayılan oluşturucuyu çağırdıktan sonra işlevi kullanabilirsiniz. Birçok biçimlendirme seçeneği ve üye işlevleri nesneler için geçerlidir `ifstream` . Temel sınıfların tüm işlevleri `ios` ve `istream` ' de bulunur `ifstream` .

Kitaplık işlevi gibi `sscanf_s` , `istringstream` sınıfı bellek içi dizelerdeki girişi destekler. Null Sonlandırıcı içeren bir karakter dizisindeki verileri ayıklamak için, dizeyi ayırıp başlatın ve sonra sınıfının bir nesnesini oluşturun `istringstream` .

## <a name="in-this-section"></a>Bu Bölümde

[Giriş akışı nesneleri oluşturma](../standard-library/constructing-input-stream-objects.md)

[Ayıklama Işleçlerini kullanma](../standard-library/using-extraction-operators.md)

[Ayıklama hataları için test etme](../standard-library/testing-for-extraction-errors.md)

[Giriş akışı düzenlemeleri](../standard-library/input-stream-manipulators.md)

[Giriş akışı üye Işlevleri](../standard-library/input-stream-member-functions.md)

[Kendi Sınıflarınız İçin >> İşleci Aşırı Yükleme](../standard-library/overloading-the-input-operator-for-your-own-classes.md)

## <a name="see-also"></a>Ayrıca bkz.

[iostream programlama](../standard-library/iostream-programming.md)
