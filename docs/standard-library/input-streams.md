---
title: Giriş Akışları
ms.date: 11/04/2016
helpviewer_keywords:
- reading data [C++], from input streams
- data [C++], reading from input stream
- input streams
- input stream objects
ms.assetid: f14d8954-8f8c-4c3c-8b99-14ddb3683f94
ms.openlocfilehash: 5dc3fa0af76f73897fe1181d944eb34c8d05bc64
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449321"
---
# <a name="input-streams"></a>Giriş Akışları

Giriş akışı nesnesi bayt kaynağıdır. En önemli üç giriş akışı sınıfı IStream [](../standard-library/basic-istream-class.md), [ifstream](../standard-library/basic-ifstream-class.md)ve [ıtringstream](../standard-library/basic-istringstream-class.md)' dir.

Sınıf `istream` , ardışık metin modu girişi için en iyi seçenektir. Ara belleğe alınmış veya arabelleğe alınmamış `istream` işlem için sınıfın nesnelerini yapılandırabilirsiniz. Temel sınıfının `ios`tüm işlevleri ' de `istream`bulunur. Sınıfından `istream`nadiren nesne oluşturacaksınız. Bunun yerine, genellikle [ostream](../standard-library/basic-ostream-class.md)sınıfının bir `cin` nesnesi olan önceden tanımlanmış nesneyi kullanırsınız. Bazı durumlarda, program başlatıldıktan sonra diğer `cin` Stream nesnelerine atayabilirsiniz.

Sınıfı `ifstream` , disk dosyası girişini destekler. Yalnızca giriş diski dosyası gerekiyorsa, sınıfının `ifstream`bir nesnesini oluşturun. İkili veya metin modu verileri belirtebilirsiniz. Oluşturucuda bir dosya adı belirtirseniz, nesne oluşturulduğunda dosya otomatik olarak açılır. Aksi takdirde, varsayılan oluşturucuyu çağırdıktan sonra `open` işlevi kullanabilirsiniz. Birçok biçimlendirme seçeneği ve üye işlevleri nesneler için `ifstream` geçerlidir. Temel sınıfların `ios` tüm işlevleri ve `istream` ' de `ifstream`bulunur.

Kitaplık işlevi `sscanf_s`gibi `istringstream` , sınıfı bellek içi dizelerdeki girişi destekler. Null Sonlandırıcı içeren bir karakter dizisindeki verileri ayıklamak için, dizeyi ayırıp başlatın ve sonra sınıfının `istringstream`bir nesnesini oluşturun.

## <a name="in-this-section"></a>Bu Bölümde

[Giriş Akışı Oluşturma Nesneleri](../standard-library/constructing-input-stream-objects.md)

[Ayıklama İşleçlerini Kullanma](../standard-library/using-extraction-operators.md)

[Ayıklama Hataları için Test Yapma](../standard-library/testing-for-extraction-errors.md)

[Giriş Akışı Manipülatörleri](../standard-library/input-stream-manipulators.md)

[Giriş Akışı Üye İşlevleri](../standard-library/input-stream-member-functions.md)

[Kendi Sınıflarınız İçin >> İşleci Aşırı Yükleme](../standard-library/overloading-the-input-operator-for-your-own-classes.md)

## <a name="see-also"></a>Ayrıca bkz.

[iostream Programlaması](../standard-library/iostream-programming.md)
