---
title: Giriş Akışları
ms.date: 11/04/2016
helpviewer_keywords:
- reading data [C++], from input streams
- data [C++], reading from input stream
- input streams
- input stream objects
ms.assetid: f14d8954-8f8c-4c3c-8b99-14ddb3683f94
ms.openlocfilehash: 0f56f5ffc8e61c0881eddbbd65e1c431b9219674
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50504773"
---
# <a name="input-streams"></a>Giriş Akışları

Bir giriş akışı nesnesine bir bayt kaynağıdır. En önemli üç Giriş akışı sınıfları [istream](../standard-library/basic-istream-class.md), [ifstream](../standard-library/basic-ifstream-class.md), ve [istringstream](../standard-library/basic-istringstream-class.md).

`istream` Sınıfı sıralı metin modunda girişi için en iyi şekilde kullanılır. Sınıfın nesneleri yapılandırabileceğiniz `istream` için arabelleğe alınan veya arabellekten çıkarılan işlemi. Temel sınıfın tüm işlevselliği `ios`, dahildir `istream`. Sınıf nesneleri nadiren oluşturmak `istream`. Bunun yerine, genel olarak önceden tanımlanmış kullanacağınız `cin` gerçekten sınıfın bir nesnesi nesne [ostream](../standard-library/basic-ostream-class.md). Bazı durumlarda, atadığınız `cin` program başlatma sonra diğer akışı nesneleri için.

`ifstream` Sınıfı, disk dosyası girişini destekler. Gerekirse bir disk dosyası, sınıfın bir nesnesi oluşturmak yalnızca salt giriş `ifstream`. İkili veya metin modunda veri belirtebilirsiniz. Oluşturucuda bir filename belirtirseniz, bir nesne oluşturulduğunda dosya otomatik olarak açılır. Aksi takdirde, kullanabileceğiniz `open` sonra varsayılan oluşturucuyu çağırma işlevi. Çok sayıda biçimlendirme seçenekleri ve üye işlevler uygulamak `ifstream` nesneleri. Tüm temel sınıflar işlevselliğini `ios` ve `istream` dahil `ifstream`.

Kitaplığı işlev gibi `sscanf_s`, `istringstream` sınıfı, bellek içi dizeleri girişten destekler. Bir null Sonlandırıcı bir karakter dizisinden verileri ayıklamak için ayırmak ve dizesini başlatır ve ardından sınıfın bir nesnesi oluşturmak `istringstream`.

## <a name="in-this-section"></a>Bu Bölümde

[Giriş Akışı Oluşturma Nesneleri](../standard-library/constructing-input-stream-objects.md)

[Ayıklama İşleçlerini Kullanma](../standard-library/using-extraction-operators.md)

[Ayıklama Hataları için Test Yapma](../standard-library/testing-for-extraction-errors.md)

[Giriş Akışı Manipülatörleri](../standard-library/input-stream-manipulators.md)

[Giriş Akışı Üye İşlevleri](../standard-library/input-stream-member-functions.md)

[Kendi Sınıflarınız İçin >> İşleci Aşırı Yükleme](../standard-library/overloading-the-input-operator-for-your-own-classes.md)

## <a name="see-also"></a>Ayrıca bkz.

[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
