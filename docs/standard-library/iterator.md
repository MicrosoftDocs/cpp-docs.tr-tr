---
title: '&lt;Yineleyici&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <iterator>
- iterator/std::<iterator>
dev_langs: C++
helpviewer_keywords: iterator header
ms.assetid: c61a3962-f3ed-411a-b5a3-e8b3c2b500bd
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3f0918b5d4c222506173c03859cb74ec3fd13bdd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ltiteratorgt"></a>&lt;Yineleyici&gt;
Yineleyici basit öğelerini, önceden tanımlanmış yineleyicileri ve akış yineleyicilerinin yanı sıra pek çok destek şablonunu da tanımlar. Ön tanımlı yineleyiciler ekleme ve tersine çevirme bağdaştırıcıları içerir. Ekleme yineleyici bağdaştırıcıların üç sınıfı vardır: ön, arka ve genel. Kapsayıcı üye işlevi yineleyicilerin sağladığı üzerine yaz semantiği yerine ekle semantiği sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <iterator>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Yineleyiciler, C++ programının tek düzenli olarak farklı veri yapılarıyla çalışmasını sağlayacak şekilde kendi gereksinimlerini soyutlayan bir işaretçiler genelleştirmesidir. Yineleyiciler; kapsayıcılar ve genel algoritmalar arasındaki aracılar gibi davranır. Belirli veri türleri üzerinde çalışması yerine, yineleyici türüyle belirtilen aralıkta çalışması için algoritmalar tanımlanır. Yineleyici gereksinimlerini karşılayan veri yapıları algoritmaya göre çalıştırılabilir. Beş yineleyici türü veya kategorisi vardır; her biri kendi gereksinimler grubuna ve nihai işlevselliğe sahiptir:  
  
-   Çıkış: ileri taşıma, ostream ve inserter tarafından sağlanan değerleri depolayabilir ancak alamaz.  
  
-   Giriş: ileri taşıma, IStream tarafından sağlanan değerleri alabilir, ancak depolayamaz.  
  
-   İleri: ileri taşıma, değerleri depolayabilir ve alabilir.  
  
-   Çift yönlü: ileriye ve geriye taşıma; liste, küme, çoklu küme, eşleme ve birden çoklu eşleme tarafından sağlanan değerleri depolayabilir ve alabilir.  
  
-   Rastgele erişim: öğelere herhangi bir sırada erişilir; değerler depolanabilir ve alınabilir; vektör, deque, dize ve dizi tarafından sağlanır.  
  
 Daha az gereksinime sahip yineleyiciler yerine daha çok gereksinimi olan ve öğelere çok daha güçlü erişim sağlayan sahip yineleyiciler kullanılabilir. Örneğin, bir ileri yineleyici çağrılır, ardından bunun yerine bir rastgele erişim yineleyici kullanılabilir.  
  
 Visual Studio, denetlenmiş ve denetlenmemiş yineleyiciler için bir hata ayıklama modu çeşitliliğini desteklemek amacıyla Standart C++ Kitaplığı yineleyicilerine uzantılar eklemiştir. Daha fazla bilgi için bkz: [güvenli kitaplıklar: C++ Standart Kitaplığı](../standard-library/safe-libraries-cpp-standard-library.md).  
  
### <a name="functions"></a>İşlevler  
  
|||  
|-|-|  
|[Gelişmiş](../standard-library/iterator-functions.md#advance)|Belirtilen bir konum sayısıyla yineleyiciyi artırır.|  
|[back_inserter](../standard-library/iterator-functions.md#back_inserter)|Belirtilen kapsayıcının arkasında öğeler ekleyebilen bir yineleyici oluşturur.|  
|[başlayın](../standard-library/iterator-functions.md#begin)|Belirtilen bir kapsayıcıdaki ilk öğe için bir yineleyici alır.|  
|[cbegin](../standard-library/iterator-functions.md#cbegin)|Belirtilen bir kapsayıcıdaki ilk öğe için sabit bir yineleyici alır.|  
|[cend](../standard-library/iterator-functions.md#cend)|Belirtilen kapsayıcıdaki son öğeyi izleyen öğe için sabit bir yineleyici alır.|  
|[uzaklık](../standard-library/iterator-functions.md#distance)|İki yineleyici tarafından ele alınan konumlar arasındaki artış sayısını belirler.|  
|[Bitiş](../standard-library/iterator-functions.md#end)|Belirtilen kapsayıcıdaki son öğeyi izleyen öğeye bir yineleyici alır.|  
|[front_inserter](../standard-library/iterator-functions.md#front_inserter)|Belirtilen kapsayıcının önünde öğeler ekleyebilen bir yineleyici oluşturur.|  
|[ekleyici](../standard-library/iterator-functions.md#inserter)|Bir kapsayıcıya belirli bir ekleme noktasında yeni bir öğe ekleyen bir yineleyici bağdaştırıcısı.|  
|[make_checked_array_iterator](../standard-library/iterator-functions.md#make_checked_array_iterator)|Oluşturur bir [checked_array_iterator](../standard-library/checked-array-iterator-class.md) diğer algoritmalar tarafından kullanılabilir. **Not:** bu işlev bir C++ Standart Kitaplığı Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.|  
|[make_move_iterator](../standard-library/iterator-functions.md#make_move_iterator)|Sağlanan yineleyiciyi depolanmış temel yineleyicisi olarak içeren bir taşıma yineleyicisi döndürür.|  
|[make_unchecked_array_iterator](../standard-library/iterator-functions.md#make_unchecked_array_iterator)|Oluşturur bir [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md) diğer algoritmalar tarafından kullanılabilir. **Not:** bu işlev bir C++ Standart Kitaplığı Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.|  
|[sonraki](../standard-library/iterator-functions.md#next)|Belirtilen sayıda yineler ve yeni yineleyici konumunu döndürür.|  
|[önceki](../standard-library/iterator-functions.md#prev)|Belirtilen sayıda geri yineler ve yeni yineleyici konumunu döndürür.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator!=](../standard-library/iterator-operators.md#op_neq)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesinden farklı olup olmadığını sınar.|  
|[operator ==](../standard-library/iterator-operators.md#op_eq_eq)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesine eşit olup olmadığını sınar.|  
|[operator <](../standard-library/iterator-operators.md#op_lt)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesinden küçük olup olmadığını sınar.|  
|[işleci\<=](../standard-library/iterator-operators.md#op_gt_eq)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesine eşit veya ondan küçük olup olmadığını sınar.|  
|[operator >](../standard-library/iterator-operators.md#op_gt)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesinden büyük olup olmadığını sınar.|  
|[operator>=](../standard-library/iterator-operators.md#op_gt_eq)|İşlecin sol tarafındaki yineleyici nesnesinin işlecin sağ tarafındaki yineleyici nesnesine eşit veya ondan büyük olup olmadığını sınar.|  
|[operator +](../standard-library/iterator-operators.md#op_add)|Yineleyici için uzaklık ekler ve yeni döndürür `reverse_iterator` yeni uzaklık konumunda eklenen öğesi adresleme.|  
|[operator-](../standard-library/iterator-operators.md#operator-)|Bir yineleyiciyi bir başkasından çıkarır ve farkı döndürür.|  
  
### <a name="classes"></a>Sınıflar  
  
|||  
|-|-|  
|[back_insert_iterator](../standard-library/back-insert-iterator-class.md)|Şablon sınıfı, bir çıkış yineleyici nesnesi tanımlar. Türünde bir kapsayıcıya öğeleri ekler **kapsayıcı**, hangi korumalı erişen **işaretçi** depoladığı nesnesi kapsayıcı olarak adlandırılır.|  
|[bidirectional_iterator_tag](../standard-library/bidirectional-iterator-tag-struct.md)|Dönüş türü için sağlayan bir sınıf bir **iterator_category** çift yönlü yineleyici temsil eden bir işlev.|  
|[checked_array_iterator](../standard-library/checked-array-iterator-class.md)|Bir rastgele erişim, denetlenmiş yineleyici kullanarak bir diziye erişen sınıf. **Not:** Bu sınıf bir C++ Standart Kitaplığı Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.|  
|[forward_iterator_tag](../standard-library/forward-iterator-tag-struct.md)|Dönüş türü için sağlayan bir sınıf bir **iterator_category** iletme yineleyici gösteren işlev.|  
|[front_insert_iterator](../standard-library/front-insert-iterator-class.md)|Şablon sınıfı, bir çıkış yineleyici nesnesi tanımlar. Türünde bir kapsayıcıya öğeleri ekler **kapsayıcı**, hangi korumalı erişen **işaretçi** depoladığı nesnesi kapsayıcı olarak adlandırılır.|  
|[input_iterator_tag](../standard-library/input-iterator-tag-struct.md)|Dönüş türü için sağlayan bir sınıf bir **iterator_category** giriş yineleyici temsil eden bir işlev.|  
|[insert_iterator](../standard-library/insert-iterator-class.md)|Şablon sınıfı, bir çıkış yineleyici nesnesi tanımlar. Türünde bir kapsayıcıya öğeleri ekler **kapsayıcı**, hangi korumalı erişen **işaretçi** depoladığı nesnesi kapsayıcı olarak adlandırılır. Ayrıca korumalı depolar **yineleyici** sınıfın bir nesnesi **Container::iterator**adlı **iter**.|  
|[istream_iterator](../standard-library/istream-iterator-class.md)|Şablon sınıfı, bir giriş yineleyici nesnesini açıklar. Sınıfın nesnelerini ayıklar **Ty** depoladığı, türü işaretçinin nesnesi aracılığıyla erişen bir giriş akışından `basic_istream` \< **Elem**, **Tr**>.|  
|[istreambuf_iterator](../standard-library/istreambuf-iterator-class.md)|Şablon sınıfı, bir giriş yineleyici nesnesini açıklar. Sınıfının öğeleri ekler **Elem** bir çıkış akışı arabelleğe hangi BT bir nesne türü depoları eriştiği **işaretçi** için `basic_streambuf` \< **Elem**, **Tr**>.|  
|[Yineleyici](../standard-library/iterator-struct.md)|Şablon sınıfı, tüm yineleyiciler için bir taban türü olarak kullanılır.|  
|[iterator_traits](../standard-library/iterator-traits-struct.md)|Aynı şekilde başvurulabilsinler diye farklı yineleyici türleriyle ilişkilendirilen kritik türleri sağlayan şablon yardımcı sınıfı.|  
|[move_iterator](../standard-library/move-iterator-class.md)|A `move_iterator` nesne türünde rasgele erişim yineleyici depolar `RandomIterator`. Başvurunun kaldırıldığı durum dışında, rastgele erişimli yineleyici gibi davranır. Sonucu `operator*` için örtük olarak cast `value_type&&:` yapmak için bir `rvalue reference`.|  
|[ostream_iterator](../standard-library/ostream-iterator-class.md)|Şablon sınıfı, bir çıkış yineleyici nesnesi tanımlar. Sınıfının nesneleri ekler **türü** bir çıkış akışı hangi BT bir nesne türü depoları eriştiği **işaretçi** için `basic_ostream` \< **Elem** , **Tr**>.|  
|[ostreambuf_iterator Sınıfı](../standard-library/ostreambuf-iterator-class.md)|Şablon sınıfı, bir çıkış yineleyici nesnesi tanımlar. Sınıfının öğeleri ekler **Elem** depoladığı, türü işaretçinin nesnesi aracılığıyla erişen bir çıkış akışı arabellek içine `basic_streambuf` \< **Elem**, **Tr**>.|  
|[output_iterator_tag](../standard-library/output-iterator-tag-struct.md)|Dönüş türü için sağlayan bir sınıf **iterator_category** çıkış yineleyici temsil eden bir işlev.|  
|[random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)|Dönüş türü için sağlayan bir sınıf **iterator_category** rasgele erişim yineleyici temsil eden bir işlev.|  
|[reverse_iterator](../standard-library/reverse-iterator-class.md)|Şablon sınıfı, rastgele erişim yineleyici olarak davranan bir nesneyi yalnızca tersten açıklar.|  
|[unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md)|Bir rastgele erişim, denetlenmemiş yineleyici kullanarak bir diziye erişen sınıf. **Not:** Bu sınıf bir C++ Standart Kitaplığı Microsoft uzantısıdır. Bu işlev kullanılarak uygulanan kod bu Microsoft uzantısını desteklemeyen C++ Standart yapı ortamları için taşınabilir değildir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)



