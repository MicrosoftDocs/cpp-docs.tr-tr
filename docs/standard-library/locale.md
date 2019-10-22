---
title: '&lt;locale &gt;'
ms.date: 11/04/2016
f1_keywords:
- <locale>
- locale/std::<locale>
- std::<locale>
helpviewer_keywords:
- locale header
ms.assetid: ca56f9d2-7128-44da-8df1-f4c78c17fbf2
ms.openlocfilehash: 71182f4a527fba0ef2c91dc84be5a8faad9fc99f
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687807"
---
# <a name="ltlocalegt"></a>&lt;locale &gt;

Uluslararası duruma getirme desteği de dahil C++ olmak üzere sayısal, parasal ve takvim verilerinin temsili ve formatlaması ile ilgili farklı kültürel kurallarını kapsüllemek ve işlemek için programların kullanabileceği sınıf şablonlarını ve işlevleri tanımlar karakter sınıflandırması ve dize harmanlama için.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <locale>
```

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[has_facet](../standard-library/locale-functions.md#has_facet)|Belirli bir modelin belirtilen yerel ayarda depolanıp depolanmadığını sınar.|
|[isalnum](../standard-library/locale-functions.md#isalnum)|Bir yerel ayardaki öğenin alfabetik bir karakter mi yoksa sayısal bir karakter mi olduğunu sınar.|
|[isalpha](../standard-library/locale-functions.md#isalpha)|Bir yerel ayardaki bir öğenin alfabetik bir karakter olup olmadığını sınar.|
|[iscntrl](../standard-library/locale-functions.md#iscntrl)|Bir yerel ayardaki bir öğenin bir denetim karakteri olup olmadığını sınar.|
|[isdigit](../standard-library/locale-functions.md#isdigit)|Bir yerel ayardaki bir öğenin sayısal bir karakter olup olmadığını sınar.|
|[isgraph](../standard-library/locale-functions.md#isgraph)|Bir yerel ayardaki öğenin alfasayısal bir karakter mi yoksa noktalama işareti mi olduğunu sınar.|
|[islower](../standard-library/locale-functions.md#islower)|Bir yerel ayardaki bir öğenin küçük harf olup olmadığını sınar.|
|[isprint](../standard-library/locale-functions.md#isprint)|Bir yerel ayardaki bir öğenin yazdırılabilir bir karakter olup olmadığını sınar.|
|[ispunct](../standard-library/locale-functions.md#ispunct)|Bir yerel ayardaki bir öğenin bir noktalama işareti olup olmadığını sınar.|
|[isspace](../standard-library/locale-functions.md#isspace)|Bir yerel ayardaki bir öğenin bir boşluk olup olmadığını sınar.|
|[isupper](../standard-library/locale-functions.md#isupper)|Bir yerel ayardaki bir öğenin büyük harf olup olmadığını sınar.|
|[isxdigit](../standard-library/locale-functions.md#isxdigit)|Bir yerel ayardaki bir öğenin onaltılık bir sayıyı temsil etmek için kullanılan bir karakter olup olmadığını sınar.|
|[ToLower](../standard-library/locale-functions.md#tolower)|Bir karakteri küçük harfe dönüştürür.|
|[ToUpper](../standard-library/locale-functions.md#toupper)|Bir karakteri büyük harfe dönüştürür.|
|[use_facet](../standard-library/locale-functions.md#use_facet)|Bir başvuruyu yerel ayarda depolanan belirtilen türdeki bir modele döndürür.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[codecvt](../standard-library/codecvt-class.md)|İç ve dış karakter kodlamaları arasında dönüştürme yapmak için kullanılan bir model sağlayan bir sınıf şablonu.|
|[codecvt_base](../standard-library/codecvt-base-class.md)|Bir dönüştürme sonucunu göstermek için model üye işlevleri için dönüş türü olarak kullanılan, `result` olarak adlandırılan bir numaralandırma türünü tanımlamak için kullanılan codecvt sınıfı için temel sınıf.|
|[codecvt_byname](../standard-library/codecvt-byname-class.md)|Dönüşümlere ilişkin bir kültürel alanına özgü bilgilerin alınmasını sağlayan, verili bir yerel ayarın harmanlama modeli olarak işlev yapabilecek bir nesneyi tanımlayan türetilmiş bir sınıf şablonu.|
|[harman](../standard-library/collate-class.md)|Dize sıralama kurallarını işleyen bir model sağlayan bir COLLATE sınıfı şablonu.|
|[collate_byname](../standard-library/collate-byname-class.md)|Belirli bir yerel ayarın bir harmanlama modeli olarak işlev yapabilecek bir nesneyi tanımlayan, dize sıralama kurallarıyla ilgili bir kültürel alanına özgü bilgilerin alınmasını sağlayan türetilmiş bir sınıf şablonu.|
|[CType](../standard-library/ctype-class.md)|Karakterleri sınıflandırmak için kullanılan bir model sağlayan, büyük ve küçük harf ve yerel karakter kümesi arasında ve yerel ayar tarafından kullanılan küme arasında dönüştürme yapan bir sınıf şablonu.|
|[CType \<char >](../standard-library/ctype-char-class.md)|**Char**türünde bir karakterin çeşitli özelliklerini niteleyen bir yerel ayar modeli olarak kullanılabilecek bir nesneyi **açıklayan, sınıf**`ctype<CharType>` şablonunun açık bir özelleştirmesi olan sınıf.|
|[ctype_base](../standard-library/ctype-base-class.md)|Karakterleri tek tek veya aralığın tamamında sınıflandırmak veya sınamak için kullanılan numaralandırma türleri tanımlamak için kullanılan ctype sınıfı için temel sınıf.|
|[ctype_byname](../standard-library/ctype-byname-class.md)|Belirli bir yerel ayarın CType modeli olarak işlev görebilecek, karakter sınıflandırmasını ve büyük/küçük harf ve yerel olarak belirtilen karakter kümeleri arasında karakterlerin dönüştürülmesini sağlayan bir nesneyi tanımlayan türetilmiş bir sınıf şablonu.|
|[ayarlar](../standard-library/locale-class.md)|Kültüre özgü bilgileri depolayan bir yerel ayar nesnesini belirli bir yerelleştirilmiş ortamı toplu olarak kapsülleyen bir modeller kümesi olarak tanımlayan sınıf.|
|[iletilerine](../standard-library/messages-class.md)|Belirli bir yerel ayar için uluslararası iletilerin bir kataloğundan yerelleştirilmiş iletiler almak için bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlayan bir sınıf şablonu.|
|[messages_base](../standard-library/messages-base-class.md)|İleti Kataloğu için bir **int** türü tanımlayan temel sınıf.|
|[messages_byname](../standard-library/messages-byname-class.md)|Yerelleştirilmiş iletilerin alınmasını etkinleştirerek, belirli bir yerel ayarın ileti modeli olarak işlev yapabilecek bir nesneyi tanımlayan türetilmiş bir sınıf şablonu.|
|[money_base](../standard-library/money-base-class.md)|Karakterleri tek tek veya aralığın tamamında sınıflandırmak veya sınamak için kullanılan numaralandırma türleri tanımlamak için kullanılan ctype sınıfı için temel sınıf.|
|[money_get](../standard-library/money-get-class.md)|**CharType** türündeki dizilerin parasal değerlere dönüştürmelerini denetlemek için bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlayan bir sınıf şablonu.|
|[money_put](../standard-library/money-put-class.md)|Parasal değerlerin **CharType**türündeki sıralara dönüştürülmesine yönelik bir yerel ayar modeli olarak görev yapabilecek bir nesne tanımlayan bir sınıf şablonu.|
|[moneypunct](../standard-library/moneypunct-class.md)|Bir parasal giriş alanını veya parasal çıkış alanını temsil etmek için kullanılan **CharType** türündeki dizileri açıklayan bir yerel ayar modeli olarak işlev görebilecek bir nesne tanımlayan sınıf şablonu.|
|[moneypunct_byname](../standard-library/moneypunct-byname-class.md)|Parasal giriş veya çıkış alanlarını biçimlendirmeyi etkinleştirerek, belirtilen yerel ayarın moneypunct modeli olarak işlev görebilecek bir nesneyi tanımlayan türetilmiş bir sınıf şablonu.|
|[num_get](../standard-library/num-get-class.md)|**CharType** türündeki dizilerin sayısal değerlere dönüştürmelerini denetlemek için bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlayan bir sınıf şablonu.|
|[num_put](../standard-library/num-put-class.md)|Sayısal değerlerin **CharType**türündeki sıralara dönüştürülmesine yönelik bir yerel ayar modeli olarak görev yapabilecek bir nesne tanımlayan bir sınıf şablonu.|
|[numpunct](../standard-library/numpunct-class.md)|Sayısal ve Boolean ifadelerin biçimlendirme ve noktalama bilgileri hakkında bilgi temsil etmek için kullanılan **CharType** türündeki dizileri açıklayan bir nesneyi tanımlayan bir sınıf şablonu.|
|[numpunct_byname](../standard-library/numpunct-byname-class.md)|Belirtilen bir yerel ayarın moneypunct modeli olarak işlev gösteren ve sayısal ve Boolean ifadelerin biçimlendirmesini ve noktalama işaretlerini etkinleştiren bir nesneyi tanımlayan türetilmiş bir sınıf şablonu.|
|[time_base](../standard-library/time-base-class.md)|Yalnızca numaralandýrýlmýþ tür dateorder ve bu türden birkaç sabiti tanımlayarak, sınıf şablonu time_get modelleri için temel sınıf olarak hizmet veren bir sınıf.|
|[time_get](../standard-library/time-get-class.md)|**CharType** türündeki dizilerin zaman değerlerine dönüştürülmesine yönelik bir yerel ayar modeli olarak görev yapabilecek bir nesne tanımlayan bir sınıf şablonu.|
|[time_get_byname](../standard-library/time-get-byname-class.md)|Time_get \<**CharType**, **InputIterator**> türünde bir yerel ayar modeli olarak hizmeti alabilen bir nesneyi açıklayan türetilmiş bir sınıf şablonu.|
|[time_put](../standard-library/time-put-class.md)|Zaman değerlerinin **CharType**türündeki sıralara dönüştürülmesine yönelik bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlayan bir sınıf şablonu.|
|[time_put_byname](../standard-library/time-put-byname-class.md)|@No__t_0 \<**CharType**, **OutputIterator**> türünde bir yerel ayar modeli olarak işlev görebilecek bir nesneyi tanımlayan türetilmiş bir sınıf şablonu.|
|[wbuffer_convert Sınıfı](../standard-library/wbuffer-convert-class.md)|Bir bayt akışı arabelleğine ve bu öğeden öğelerin aktarılmasını denetleyen bir akış arabelleği tanımlar.|
|[wstring_convert Sınıfı](../standard-library/wstring-convert-class.md)|Geniş bir dize ve bir bayt dizesi arasında dönüştürme gerçekleştiren bir sınıf şablonu.|

## <a name="see-also"></a>Ayrıca bkz.

[Kod sayfaları](../c-runtime-library/code-pages.md) \
[Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md) \
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
