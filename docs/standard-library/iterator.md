---
title: '&lt;iden&gt;'
ms.date: 11/04/2016
f1_keywords:
- <iterator>
- iterator/std::<iterator>
helpviewer_keywords:
- iterator header
ms.assetid: c61a3962-f3ed-411a-b5a3-e8b3c2b500bd
ms.openlocfilehash: 5faf55eebecf473f45074f862ef64929df6f4374
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452978"
---
# <a name="ltiteratorgt"></a>&lt;iden&gt;

Yineleyici basit öğelerini, önceden tanımlanmış yineleyicileri ve akış yineleyicilerinin yanı sıra pek çok destek şablonunu da tanımlar. Ön tanımlı yineleyiciler ekleme ve tersine çevirme bağdaştırıcıları içerir. Ekleme yineleyici bağdaştırıcıların üç sınıfı vardır: ön, arka ve genel. Kapsayıcı üye işlevi yineleyicilerin sağladığı üzerine yaz semantiği yerine ekle semantiği sağlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<Yineleyici >

**Ad alanı:** std

## <a name="remarks"></a>Açıklamalar

Yineleyiciler, C++ programının tek düzenli olarak farklı veri yapılarıyla çalışmasını sağlayacak şekilde kendi gereksinimlerini soyutlayan bir işaretçiler genelleştirmesidir. Yineleyiciler; kapsayıcılar ve genel algoritmalar arasındaki aracılar gibi davranır. Belirli veri türleri üzerinde çalışması yerine, yineleyici türüyle belirtilen aralıkta çalışması için algoritmalar tanımlanır. Yineleyici gereksinimlerini karşılayan veri yapıları algoritmaya göre çalıştırılabilir. Beş yineleyici türü veya kategorisi vardır; her biri kendi gereksinimler grubuna ve nihai işlevselliğe sahiptir:

- Çıkış: ileri taşıma, ostream ve inserter tarafından sağlanan değerleri depolayabilir ancak alamaz.

- Giriş: ileri taşıma, IStream tarafından sağlanan değerleri alabilir, ancak depolayamaz.

- İleri: ileri taşıma, değerleri depolayabilir ve alabilir.

- Çift yönlü: ileriye ve geriye taşıma; liste, küme, çoklu küme, eşleme ve birden çoklu eşleme tarafından sağlanan değerleri depolayabilir ve alabilir.

- Rastgele erişim: öğelere herhangi bir sırada erişilir; değerler depolanabilir ve alınabilir; vektör, deque, dize ve dizi tarafından sağlanır.

Daha az gereksinime sahip yineleyiciler yerine daha çok gereksinimi olan ve öğelere çok daha güçlü erişim sağlayan sahip yineleyiciler kullanılabilir. Örneğin, bir ileri yineleyici çağrılır, ardından bunun yerine bir rastgele erişim yineleyici kullanılabilir.

Visual Studio, denetlenmiş ve denetlenmemiş yineleyiciler için bir hata ayıklama modu çeşitliliğini desteklemek amacıyla Standart C++ Kitaplığı yineleyicilerine uzantılar eklemiştir. Daha fazla bilgi için bkz [. Güvenli Kitaplıklar: C++Standart Kitaplık](../standard-library/safe-libraries-cpp-standard-library.md).

## <a name="members"></a>Üyeler

### <a name="functions"></a>İşlevler

|||
|-|-|
|[ilerler](../standard-library/iterator-functions.md#advance)|Belirtilen bir konum sayısıyla yineleyiciyi artırır.|
|[back_inserter](../standard-library/iterator-functions.md#back_inserter)|Belirtilen kapsayıcının arkasında öğeler ekleyebilen bir yineleyici oluşturur.|
|[başladı](../standard-library/iterator-functions.md#begin)|Belirtilen bir kapsayıcıdaki ilk öğe için bir yineleyici alır.|
|[cbegin](../standard-library/iterator-functions.md#cbegin)|Belirtilen bir kapsayıcıdaki ilk öğe için sabit bir yineleyici alır.|
|[cend](../standard-library/iterator-functions.md#cend)|Belirtilen kapsayıcıdaki son öğeyi izleyen öğe için sabit bir yineleyici alır.|
|[crbegin](../standard-library/iterator-functions.md#crbegin)||
|[crend](../standard-library/iterator-functions.md#crend)||
|[verileri](../standard-library/iterator-functions.md#data)||
|[Uzaklık](../standard-library/iterator-functions.md#distance)|İki yineleyici tarafından ele alınan konumlar arasındaki artış sayısını belirler.|
|[erer](../standard-library/iterator-functions.md#end)|Belirtilen kapsayıcıdaki son öğeyi izleyen öğeye bir yineleyici alır.|
|[empty](../standard-library/iterator-functions.md#empty)||
|[front_inserter](../standard-library/iterator-functions.md#front_inserter)|Belirtilen kapsayıcının önünde öğeler ekleyebilen bir yineleyici oluşturur.|
|[inserter](../standard-library/iterator-functions.md#inserter)|Bir kapsayıcıya belirli bir ekleme noktasında yeni bir öğe ekleyen bir yineleyici bağdaştırıcısı.|
|[make_checked_array_iterator](../standard-library/iterator-functions.md#make_checked_array_iterator)|Diğer algoritmalar tarafından kullanılabilen bir [checked_array_iterator](../standard-library/checked-array-iterator-class.md) oluşturur. **Not:**  Bu işlev, C++ standart kitaplığın Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.|
|[make_move_iterator](../standard-library/iterator-functions.md#make_move_iterator)|Sağlanan yineleyiciyi depolanmış temel yineleyicisi olarak içeren bir taşıma yineleyicisi döndürür.|
|[make_unchecked_array_iterator](../standard-library/iterator-functions.md#make_unchecked_array_iterator)|Diğer algoritmalar tarafından kullanılabilen bir [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md) oluşturur. **Not:**  Bu işlev, C++ standart kitaplığın Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.|
|[ileri](../standard-library/iterator-functions.md#next)|Belirtilen sayıda yineler ve yeni yineleyici konumunu döndürür.|
|[önceki](../standard-library/iterator-functions.md#prev)|Belirtilen sayıda geri yineler ve yeni yineleyici konumunu döndürür.|
|[rbegin](../standard-library/iterator-functions.md#rbegin)||
|[rend](../standard-library/iterator-functions.md#rend)||
|[boyutla](../standard-library/iterator-functions.md#size)||

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator!=](../standard-library/iterator-operators.md#op_neq)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesinden farklı olup olmadığını sınar.|
|[operator==](../standard-library/iterator-operators.md#op_eq_eq)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesine eşit olup olmadığını sınar.|
|[işleç <](../standard-library/iterator-operators.md#op_lt)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesinden küçük olup olmadığını sınar.|
|[işlecinde\<=](../standard-library/iterator-operators.md#op_gt_eq)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesine eşit veya ondan küçük olup olmadığını sınar.|
|[işleç >](../standard-library/iterator-operators.md#op_gt)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesinden büyük olup olmadığını sınar.|
|[operator>=](../standard-library/iterator-operators.md#op_gt_eq)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesine eşit veya ondan büyük olup olmadığını sınar.|
|[işleç +](../standard-library/iterator-operators.md#op_add)|Bir yineleyici için bir konum ekler ve yeni bir konum `reverse_iterator` konumundaki eklenen öğeyi yeni adreslemeyi döndürür.|
|[işlecinde](../standard-library/iterator-operators.md#operator-)|Bir yineleyiciyi bir başkasından çıkarır ve farkı döndürür.|

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[back_insert_iterator](../standard-library/back-insert-iterator-class.md)|Şablon sınıfı, bir çıkış yineleyici nesnesi tanımlar. Öğeleri türünde `Container`bir kapsayıcıya ekler ve bu, kapsayıcı olarak adlandırılan korunan `pointer` nesne üzerinden erişir.|
|[bidirectional_iterator_tag](../standard-library/bidirectional-iterator-tag-struct.md)|Çift yönlü yineleyiciyi temsil eden bir `iterator_category` işlev için dönüş türü sağlayan bir sınıf.|
|[checked_array_iterator](../standard-library/checked-array-iterator-class.md)|Bir rastgele erişim, denetlenmiş yineleyici kullanarak bir diziye erişen sınıf. **Not:**  Bu sınıf, C++ standart kitaplığın Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.|
|[forward_iterator_tag](../standard-library/forward-iterator-tag-struct.md)|İleri Yineleyici temsil eden bir `iterator_category` işlev için dönüş türü sağlayan bir sınıf.|
|[front_insert_iterator](../standard-library/front-insert-iterator-class.md)|Şablon sınıfı, bir çıkış yineleyici nesnesi tanımlar. Öğeleri türünde `Container`bir kapsayıcıya ekler ve bu, kapsayıcı olarak adlandırılan korunan `pointer` nesne üzerinden erişir.|
|[input_iterator_tag](../standard-library/input-iterator-tag-struct.md)|Bir giriş yineleyicisini temsil eden bir `iterator_category` işlev için dönüş türü sağlayan bir sınıf.|
|[insert_iterator](../standard-library/insert-iterator-class.md)|Şablon sınıfı, bir çıkış yineleyici nesnesi tanımlar. Öğeleri türünde `Container`bir kapsayıcıya ekler ve bu, kapsayıcı olarak adlandırılan korunan `pointer` nesne üzerinden erişir. Ayrıca, olarak adlandırılan `iterator` `iter`korunan nesneyi `Container::iterator`de depolar.|
|[istream_iterator](../standard-library/istream-iterator-class.md)|Şablon sınıfı, bir giriş yineleyici nesnesini açıklar. Bir giriş akışından sınıfının `Ty` nesnelerini ayıklar. Bu, bir girdi akışından, **Elet**, **tr**> `basic_istream` \<işaretçisinin türü olan bir nesne üzerinden erişir.|
|[istreambuf_iterator](../standard-library/istreambuf-iterator-class.md)|Şablon sınıfı, bir giriş yineleyici nesnesini açıklar. Sınıf `Elem` öğelerini, depoladığı bir nesne üzerinden eriştiği bir çıkış akışı arabelleğine ekler ve bu `basic_streambuf` \<tür `pointer` **eled**, **tr**>.|
|[iden](../standard-library/iterator-struct.md)|Şablon sınıfı, tüm yineleyiciler için bir taban türü olarak kullanılır.|
|[iterator_traits](../standard-library/iterator-traits-struct.md)|Aynı şekilde başvurulabilsinler diye farklı yineleyici türleriyle ilişkilendirilen kritik türleri sağlayan şablon yardımcı sınıfı.|
|[move_iterator](../standard-library/move-iterator-class.md)|Bir `move_iterator` nesne, türünde `RandomIterator`bir rastgele erişim yineleyici depolar. Başvurunun kaldırıldığı durum dışında, rastgele erişimli yineleyici gibi davranır. Sonucu `operator*` , `value_type&&:` yapmak`rvalue reference`için örtük olarak öğesine dönüştürüldü.|
|[ostream_iterator](../standard-library/ostream-iterator-class.md)|Şablon sınıfı, bir çıkış yineleyici nesnesi tanımlar. Bir çıkış `Type` akışına sınıfının nesnelerini ekler ve bu da, ' ın **eled**, **tr**> `pointer` `basic_ostream` \<türünden oluşturduğu bir nesne üzerinden erişir.|
|[ostreambuf_iterator Sınıfı](../standard-library/ostreambuf-iterator-class.md)|Şablon sınıfı, bir çıkış yineleyici nesnesi tanımlar. Sınıf `Elem` öğelerini, bir çıkış akışı arabelleğine ekler ve bu da, **eled**, **tr**> `basic_streambuf` \<işaretçisi türünde, depoladığı bir nesne üzerinden erişir.|
|[output_iterator_tag](../standard-library/output-iterator-tag-struct.md)|Bir çıkış yineleyicisini temsil eden işlev için `iterator_category` dönüş türü sağlayan bir sınıf.|
|[random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)|Rastgele erişim yineleyicisini temsil eden işlev için `iterator_category` dönüş türü sağlayan bir sınıf.|
|[reverse_iterator](../standard-library/reverse-iterator-class.md)|Şablon sınıfı, rastgele erişim yineleyici olarak davranan bir nesneyi yalnızca tersten açıklar.|
|[unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md)|Bir rastgele erişim, denetlenmemiş yineleyici kullanarak bir diziye erişen sınıf. **Not:**  Bu sınıf, C++ standart kitaplığın Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
