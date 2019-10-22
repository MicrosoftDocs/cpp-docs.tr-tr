---
title: '&lt;iterator &gt;'
ms.date: 11/04/2016
f1_keywords:
- <iterator>
- iterator/std::<iterator>
helpviewer_keywords:
- iterator header
ms.assetid: c61a3962-f3ed-411a-b5a3-e8b3c2b500bd
ms.openlocfilehash: 31854834c418c6d563a0306bd2cde404b3254a23
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687838"
---
# <a name="ltiteratorgt"></a>&lt;iterator &gt;

Yineleyici basit öğelerini, önceden tanımlanmış yineleyicileri ve akış yineleyicilerinin yanı sıra pek çok destek şablonunu da tanımlar. Ön tanımlı yineleyiciler ekleme ve tersine çevirme bağdaştırıcıları içerir. Ekleme yineleyici bağdaştırıcıların üç sınıfı vardır: ön, arka ve genel. Kapsayıcı üye işlevi yineleyicilerin sağladığı üzerine yaz semantiği yerine ekle semantiği sağlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<iterator >

**Ad alanı:** std

## <a name="remarks"></a>Açıklamalar

Yineleyiciler, C++ programının tek düzenli olarak farklı veri yapılarıyla çalışmasını sağlayacak şekilde kendi gereksinimlerini soyutlayan bir işaretçiler genelleştirmesidir. Yineleyiciler; kapsayıcılar ve genel algoritmalar arasındaki aracılar gibi davranır. Belirli veri türleri üzerinde çalışması yerine, yineleyici türüyle belirtilen aralıkta çalışması için algoritmalar tanımlanır. Yineleyici gereksinimlerini karşılayan veri yapıları algoritmaya göre çalıştırılabilir. Beş yineleyici türü veya kategorisi vardır; her biri kendi gereksinimler grubuna ve nihai işlevselliğe sahiptir:

- Çıkış: ileri taşıma, ostream ve inserter tarafından sağlanan değerleri depolayabilir ancak alamaz.

- Giriş: ileri taşıma, IStream tarafından sağlanan değerleri alabilir, ancak depolayamaz.

- İleri: ileri taşıma, değerleri depolayabilir ve alabilir.

- Çift yönlü: ileriye ve geriye taşıma; liste, küme, çoklu küme, eşleme ve birden çoklu eşleme tarafından sağlanan değerleri depolayabilir ve alabilir.

- Rastgele erişim: öğelere herhangi bir sırada erişilir; değerler depolanabilir ve alınabilir; vektör, deque, dize ve dizi tarafından sağlanır.

Daha az gereksinime sahip yineleyiciler yerine daha çok gereksinimi olan ve öğelere çok daha güçlü erişim sağlayan sahip yineleyiciler kullanılabilir. Örneğin, bir ileri yineleyici çağrılır, ardından bunun yerine bir rastgele erişim yineleyici kullanılabilir.

Visual Studio, denetlenmiş ve denetlenmemiş yineleyiciler için bir hata ayıklama modu çeşitliliğini desteklemek amacıyla Standart C++ Kitaplığı yineleyicilerine uzantılar eklemiştir. Daha fazla bilgi için bkz. [Güvenli Kitaplıklar C++ : standart kitaplık](../standard-library/safe-libraries-cpp-standard-library.md).

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
|[olmamalıdır](../standard-library/iterator-functions.md#empty)||
|[front_inserter](../standard-library/iterator-functions.md#front_inserter)|Belirtilen kapsayıcının önünde öğeler ekleyebilen bir yineleyici oluşturur.|
|[inserter](../standard-library/iterator-functions.md#inserter)|Bir kapsayıcıya belirli bir ekleme noktasında yeni bir öğe ekleyen bir yineleyici bağdaştırıcısı.|
|[make_checked_array_iterator](../standard-library/iterator-functions.md#make_checked_array_iterator)|Diğer algoritmalar tarafından kullanılabilen bir [checked_array_iterator](../standard-library/checked-array-iterator-class.md) oluşturur. **Note:**  Bu işlev, C++ standart kitaplığın Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.|
|[make_move_iterator](../standard-library/iterator-functions.md#make_move_iterator)|Sağlanan yineleyiciyi depolanmış temel yineleyicisi olarak içeren bir taşıma yineleyicisi döndürür.|
|[make_unchecked_array_iterator](../standard-library/iterator-functions.md#make_unchecked_array_iterator)|Diğer algoritmalar tarafından kullanılabilen bir [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md) oluşturur. **Note:**  Bu işlev, C++ standart kitaplığın Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.|
|[ileri](../standard-library/iterator-functions.md#next)|Belirtilen sayıda yineler ve yeni yineleyici konumunu döndürür.|
|[önceki](../standard-library/iterator-functions.md#prev)|Belirtilen sayıda geri yineler ve yeni yineleyici konumunu döndürür.|
|[rbegin](../standard-library/iterator-functions.md#rbegin)||
|[rend](../standard-library/iterator-functions.md#rend)||
|[boyutla](../standard-library/iterator-functions.md#size)||

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator!=](../standard-library/iterator-operators.md#op_neq)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesinden farklı olup olmadığını sınar.|
|[işleç = =](../standard-library/iterator-operators.md#op_eq_eq)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesine eşit olup olmadığını sınar.|
|[işleç <](../standard-library/iterator-operators.md#op_lt)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesinden küçük olup olmadığını sınar.|
|[işleç \< =](../standard-library/iterator-operators.md#op_gt_eq)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesine eşit veya ondan küçük olup olmadığını sınar.|
|[işleç >](../standard-library/iterator-operators.md#op_gt)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesinden büyük olup olmadığını sınar.|
|[operator>=](../standard-library/iterator-operators.md#op_gt_eq)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesine eşit veya ondan büyük olup olmadığını sınar.|
|[işleç +](../standard-library/iterator-operators.md#op_add)|Bir yineleyici için bir konum ekler ve eklenen öğeyi yeni bir konum konumuna adresleyen yeni `reverse_iterator` döndürür.|
|[işlecinde](../standard-library/iterator-operators.md#operator-)|Bir yineleyiciyi bir başkasından çıkarır ve farkı döndürür.|

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[back_insert_iterator](../standard-library/back-insert-iterator-class.md)|Sınıf şablonu, bir çıkış yineleyici nesnesini açıklar. Öğe, kapsayıcı olarak adlandırılan korunan `pointer` nesnesinden eriştiği `Container` türünde bir kapsayıcıya öğeler ekler.|
|[bidirectional_iterator_tag](../standard-library/bidirectional-iterator-tag-struct.md)|Çift yönlü yineleyiciyi temsil eden bir `iterator_category` işlevi için dönüş türü sağlayan bir sınıf.|
|[checked_array_iterator](../standard-library/checked-array-iterator-class.md)|Bir rastgele erişim, denetlenmiş yineleyici kullanarak bir diziye erişen sınıf. **Note:**  Bu sınıf, C++ standart kitaplığın Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.|
|[forward_iterator_tag](../standard-library/forward-iterator-tag-struct.md)|İleri Yineleyici temsil eden bir `iterator_category` işlevi için dönüş türü sağlayan bir sınıf.|
|[front_insert_iterator](../standard-library/front-insert-iterator-class.md)|Sınıf şablonu, bir çıkış yineleyici nesnesini açıklar. Öğe, kapsayıcı olarak adlandırılan korunan `pointer` nesnesinden eriştiği `Container` türünde bir kapsayıcıya öğeler ekler.|
|[input_iterator_tag](../standard-library/input-iterator-tag-struct.md)|Bir giriş yineleyicisini temsil eden bir `iterator_category` işlevi için dönüş türü sağlayan bir sınıf.|
|[insert_iterator](../standard-library/insert-iterator-class.md)|Sınıf şablonu, bir çıkış yineleyici nesnesini açıklar. Öğe, kapsayıcı olarak adlandırılan korunan `pointer` nesnesinden eriştiği `Container` türünde bir kapsayıcıya öğeler ekler. Ayrıca, `iter` adlı `Container::iterator` sınıfının korunan `iterator` nesnesini de depolar.|
|[istream_iterator](../standard-library/istream-iterator-class.md)|Sınıf şablonu, bir giriş Yineleyici nesnesini açıklar. @No__t_0, `basic_istream` \<**eled**, **tr**> işaretçisinin tür işaretçisi olan, depoladığı bir nesneden eriştiği bir giriş akışından sınıfının nesnelerini ayıklar.|
|[istreambuf_iterator](../standard-library/istreambuf-iterator-class.md)|Sınıf şablonu, bir giriş Yineleyici nesnesini açıklar. @No__t_0 sınıf öğelerini, depoladığı bir nesne üzerinden eriştiği bir çıkış akışı arabelleğine ekler; `basic_streambuf` \<**Eled**, **tr**> `pointer` türü.|
|[iden](../standard-library/iterator-struct.md)|Sınıf şablonu, tüm yineleyiciler için temel tür olarak kullanılır.|
|[iterator_traits](../standard-library/iterator-traits-struct.md)|Aynı şekilde başvurulabilsinler diye farklı yineleyici türleriyle ilişkilendirilen kritik türleri sağlayan şablon yardımcı sınıfı.|
|[move_iterator](../standard-library/move-iterator-class.md)|@No__t_0 nesnesi, `RandomIterator` türünde bir rastgele erişim yineleyicisini depolar. Başvurunun kaldırıldığı durum dışında, rastgele erişimli yineleyici gibi davranır. @No__t_0 sonucu, `rvalue reference` yapmak için örtük olarak `value_type&&:` olarak dönüştürüldü.|
|[ostream_iterator](../standard-library/ostream-iterator-class.md)|Sınıf şablonu, bir çıkış yineleyici nesnesini açıklar. @No__t_0 sınıf nesnelerini, depoladığı bir nesne üzerinden eriştiği bir çıkış akışına ekler; `basic_ostream` \<**Eled**, **tr**> `pointer`.|
|[ostreambuf_iterator Sınıfı](../standard-library/ostreambuf-iterator-class.md)|Sınıf şablonu, bir çıkış yineleyici nesnesini açıklar. @No__t_0 sınıf öğelerini, depoladığı bir nesne üzerinden eriştiği bir çıkış akışı arabelleğine ekler; `basic_streambuf` \<**Elet**, **tr**> için işaretçi türü.|
|[output_iterator_tag](../standard-library/output-iterator-tag-struct.md)|Bir çıkış yineleyicisini temsil eden `iterator_category` işlevi için dönüş türü sağlayan bir sınıf.|
|[random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)|Rastgele erişim yineleyicisini temsil eden `iterator_category` işlevi için dönüş türü sağlayan bir sınıf.|
|[reverse_iterator](../standard-library/reverse-iterator-class.md)|Sınıf şablonu, yalnızca ters erişimli bir rastgele erişim Yineleyici gibi davranan bir nesneyi tanımlar.|
|[unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md)|Bir rastgele erişim, denetlenmemiş yineleyici kullanarak bir diziye erişen sınıf. **Note:**  Bu sınıf, C++ standart kitaplığın Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md) \
[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
