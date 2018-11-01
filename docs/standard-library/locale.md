---
title: '&lt;Yerel ayar&gt;'
ms.date: 11/04/2016
f1_keywords:
- <locale>
- locale/std::<locale>
- std::<locale>
helpviewer_keywords:
- locale header
ms.assetid: ca56f9d2-7128-44da-8df1-f4c78c17fbf2
ms.openlocfilehash: 54d6f5306f4517c6450f36051df51385d8d8f578
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494310"
---
# <a name="ltlocalegt"></a>&lt;Yerel ayar&gt;

C++ programlarının, karakter sınıflandırması ve dize harmanlama için uluslararası desteğin dahil olduğu sayısal, parasal ve takvimle ilgili verileri göz önüne alarak farklı kültürel dönüştürmeleri kapsüllemek ve yönetmek için kullanabildiği şablon sınıflarını ve işlevleri tanımlar.

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
|[tolower](../standard-library/locale-functions.md#tolower)|Bir karakteri küçük harfe dönüştürür.|
|[toupper](../standard-library/locale-functions.md#toupper)|Bir karakteri büyük harfe dönüştürür.|
|[use_facet](../standard-library/locale-functions.md#use_facet)|Bir başvuruyu yerel ayarda depolanan belirtilen türdeki bir modele döndürür.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[codecvt](../standard-library/codecvt-class.md)|Bir model sağlayan şablon sınıfı iç ve dış karakter kodlamaları arasından dönüştürme yapmak için kullanılır.|
|[codecvt_base](../standard-library/codecvt-base-class.md)|Bir numaralandırma türü tanımlamak için kullanılan codecvt sınıfının bir temel sınıf denir `result`bir dönüştürmenin sonucunu belirtmek için model üye işlevleri için dönüş türü olarak kullanılır.|
|[codecvt_byname](../standard-library/codecvt-byname-class.md)|Dönüştürmeyle ilgili kültürel bir alana özgü bilgilerin alınmasını sağlayan, verili yerel ayarın bir harmanlama modeli olarak hizmet verebilen bir nesneyi tanımlayan türetilmiş bir şablon sınıfı.|
|[COLLATE](../standard-library/collate-class.md)|Dize sıralama dönüştürmelerini işleyen model sağlayan bir harmanlama şablonu sınıfı.|
|[collate_byname](../standard-library/collate-byname-class.md)|Dize sıralama kurallarıyla ilgili kültürel bir alana özgü bilgilerin alınmasını sağlayan, verili yerel ayarın bir harmanlama modeli olarak hizmet verebilen bir nesneyi tanımlayan türetilmiş bir şablon sınıfı.|
|[CType](../standard-library/ctype-class.md)|Büyük küçük harflerden ve yerel karakter kümesiyle yerel ayar tarafından kullanılan küme arasında dönüştürme yapan, karakterleri sınıflandırmak için kullanılan model sağlayan bir şablon sınıfı.|
|[CType\<char >](../standard-library/ctype-char-class.md)|Şablon sınıfının açık uzmanlığı olan bir sınıf `ctype<CharType>` türüne **char**, türü bir karakterin çeşitli özelliklerini karakterize etmek için bir yerel ayar modeli hizmet verebilen bir nesneyi tanımlayan **char**.|
|[ctype_base](../standard-library/ctype-base-class.md)|Karakterleri tek tek veya aralığın tamamında sınıflandırmak veya sınamak için kullanılan numaralandırma türleri tanımlamak için kullanılan ctype sınıfı için temel sınıf.|
|[ctype_byname](../standard-library/ctype-byname-class.md)|Bir nesneyi tanımlayan türetilmiş bir şablon sınıfı, durum ve yerel ayara özgü karakter kümeleri arasında karakterlerin sınıflandırılmasını ve karakterlerin dönüşümünü sağlayarak verili bir yerel ayarın ctype modeli olarak hizmet verebilir.|
|[Yerel ayar](../standard-library/locale-class.md)|Kültüre özgü bilgileri depolayan bir yerel ayar nesnesini belirli bir yerelleştirilmiş ortamı toplu olarak kapsülleyen bir modeller kümesi olarak tanımlayan sınıf.|
|[İletileri](../standard-library/messages-class.md)|Verili bir yerel ayar için uluslararası iletilerin bir kataloğundan yerelleştirilmiş iletiler almak için bir yerel ayar olarak hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı.|
|[messages_base](../standard-library/messages-base-class.md)|Tanımlayan bir temel sınıfı bir **int** iletilerin kataloğu için türü.|
|[messages_byname](../standard-library/messages-byname-class.md)|Yerelleştirilmiş iletilerin alınmasını sağlayarak verili bir ileti modeli olarak hizmet verebilen bir nesne tanımlayan türetilmiş bir şablon sınıfı.|
|[money_base](../standard-library/money-base-class.md)|Karakterleri tek tek veya aralığın tamamında sınıflandırmak veya sınamak için kullanılan numaralandırma türleri tanımlamak için kullanılan ctype sınıfı için temel sınıf.|
|[money_get](../standard-library/money-get-class.md)|Tür dönüştürülmelerini denetlemek için bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı **CharType** parasal değerleri.|
|[money_put](../standard-library/money-put-class.md)|Türü dizilerin parasal değerlere denetim dönüştürme bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı **CharType**.|
|[moneypunct](../standard-library/moneypunct-class.md)|Türü dizileri tanımlamak için bir yerel ayar modeli hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı **CharType** bir parasal giriş alanını veya parasal çıkış alanını temsil etmek için kullanılır.|
|[moneypunct_byname](../standard-library/moneypunct-byname-class.md)|Parasal giriş veya çıkış alanlarının biçimlendirilmesini sağlayarak verili bir moneypunct modeli olarak hizmet verebilen bir nesne tanımlayan türetilmiş bir şablon sınıfı.|
|[num_get](../standard-library/num-get-class.md)|Tür dönüştürülmelerini denetlemek için bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı **CharType** sayısal değerleri.|
|[num_put](../standard-library/num-put-class.md)|Denetlemek için sayısal değerler türü için bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı **CharType**.|
|[numpunct](../standard-library/numpunct-class.md)|Türü dizileri tanımlamak için bir yerel ayar hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı **CharType** biçimlendirmesi ve noktalama işaretleri sayısal ve Boolean ifadelerin hakkında bilgi göstermek için kullanılır.|
|[numpunct_byname](../standard-library/numpunct-byname-class.md)|Sayısal ve Boolean ifadelerin biçimlendirilmesini ve noktalama işaretlerini sağlayarak verili bir moneypunct modeli olarak hizmet verebilen bir nesneyi tanımlayan türetilmiş bir şablon sınıfı.|
|[time_base](../standard-library/time-base-class.md)|Numaralı tarih düzenini ve bu türdeki çeşitli sabit değerleri tanımlayarak, şablon sınıfı time_get modelleri için temel bir sınıf olarak hizmet veren bir sınıf.|
|[time_get](../standard-library/time-get-class.md)|Tür dönüştürülmelerini denetlemek için bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı **CharType** saat değerlerine.|
|[time_get_byname](../standard-library/time-get-byname-class.md)|Türü time_get bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan türetilmiş bir şablon sınıfı\<**CharType**, **Inputıterator**>.|
|[time_put](../standard-library/time-put-class.md)|Denetlemek için saat değerleri türü dizilerin bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı **CharType**.|
|[time_put_byname](../standard-library/time-put-byname-class.md)|Türü bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan türetilmiş bir şablon sınıfı `time_put` \< **CharType**, **Outputıterator**>.|
|[wbuffer_convert Sınıfı](../standard-library/wbuffer-convert-class.md)|Bir bayt akış arabelleği gelen ve giden öğeleri aktarımını denetleyen bir akış arabelleğinin açıklar.|
|[wstring_convert Sınıfı](../standard-library/wstring-convert-class.md)|Bir geniş dize ve bir bayt dizesini arasında dönüştürme gerçekleştiren bir şablon sınıfı.|

## <a name="see-also"></a>Ayrıca bkz.

[Kod Sayfaları](../c-runtime-library/code-pages.md)<br/>
[Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
