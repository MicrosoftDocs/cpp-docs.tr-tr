---
title: "multiset sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- set/std::multiset
- set/std::multiset::allocator_type
- set/std::multiset::const_iterator
- set/std::multiset::const_pointer
- set/std::multiset::const_reference
- set/std::multiset::const_reverse_iterator
- set/std::multiset::difference_type
- set/std::multiset::iterator
- set/std::multiset::key_compare
- set/std::multiset::key_type
- set/std::multiset::pointer
- set/std::multiset::reference
- set/std::multiset::reverse_iterator
- set/std::multiset::size_type
- set/std::multiset::value_compare
- set/std::multiset::value_type
- set/std::multiset::begin
- set/std::multiset::cbegin
- set/std::multiset::cend
- set/std::multiset::clear
- set/std::multiset::count
- set/std::multiset::crbegin
- set/std::multiset::crend
- set/std::multiset::emplace
- set/std::multiset::emplace_hint
- set/std::multiset::empty
- set/std::multiset::end
- set/std::multiset::equal_range
- set/std::multiset::erase
- set/std::multiset::find
- set/std::multiset::get_allocator
- set/std::multiset::insert
- set/std::multiset::key_comp
- set/std::multiset::lower_bound
- set/std::multiset::max_size
- set/std::multiset::rbegin
- set/std::multiset::rend
- set/std::multiset::size
- set/std::multiset::swap
- set/std::multiset::upper_bound
- set/std::multiset::value_comp
dev_langs:
- C++
helpviewer_keywords:
- std::multiset [C++]
- std::multiset [C++], allocator_type
- std::multiset [C++], const_iterator
- std::multiset [C++], const_pointer
- std::multiset [C++], const_reference
- std::multiset [C++], const_reverse_iterator
- std::multiset [C++], difference_type
- std::multiset [C++], iterator
- std::multiset [C++], key_compare
- std::multiset [C++], key_type
- std::multiset [C++], pointer
- std::multiset [C++], reference
- std::multiset [C++], reverse_iterator
- std::multiset [C++], size_type
- std::multiset [C++], value_compare
- std::multiset [C++], value_type
- std::multiset [C++], begin
- std::multiset [C++], cbegin
- std::multiset [C++], cend
- std::multiset [C++], clear
- std::multiset [C++], count
- std::multiset [C++], crbegin
- std::multiset [C++], crend
- std::multiset [C++], emplace
- std::multiset [C++], emplace_hint
- std::multiset [C++], empty
- std::multiset [C++], end
- std::multiset [C++], equal_range
- std::multiset [C++], erase
- std::multiset [C++], find
- std::multiset [C++], get_allocator
- std::multiset [C++], insert
- std::multiset [C++], key_comp
- std::multiset [C++], lower_bound
- std::multiset [C++], max_size
- std::multiset [C++], rbegin
- std::multiset [C++], rend
- std::multiset [C++], size
- std::multiset [C++], swap
- std::multiset [C++], upper_bound
- std::multiset [C++], value_comp
ms.assetid: 630e8c10-0ce9-4ad9-8d79-9e91a600713f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8953fd24b62784e36f12fb96e3005e21a86bc62
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="multiset-class"></a>multiset Sınıfı
C++ Standart multiset sınıfı, içerdiği öğelerin değerleri benzersiz olması gerekmez ve hangi göre verileri otomatik olarak sıralanır anahtar değerleri hangi verdikleri koleksiyondan verilerinin alınması ve depolama için kullanılan kitaplığı. Çoklu kümedeki bir öğenin anahtar değeri doğrudan değiştirilemez. Bunun yerine, eski değerlerin silinmesi ve yeni değerlerle sahip öğelerin eklenmesi gerekir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Key, class Compare =less <Key>, class Allocator =allocator <Key>>  
class multiset  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Key*  
 Çoklu kümede depolanacak öğe veri türü.  
  
 *Karşılaştırma*  
 İki öğenin değerlerini çoklu kümedeki kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. İkili karşılaştırma **daha az**\<anahtar > varsayılan değerdir.  
  
 C ++ 14'te belirterek heterojen arama etkinleştirebilirsiniz `std::less<>` veya `std::greater<>` tür parametresi yok koşulu. Daha fazla bilgi için bkz: [ilişkilendirilebilir kapsayıcılarında heterojen arama](../standard-library/stl-containers.md#sequence_containers)  
  
 `Allocator`  
 Çoklu küme için bellek ayırmayı ve ayırmayı kaldırma hakkındaki ayrıntıları içeren saklı ayırıcı nesnesini gösteren tür. Varsayılan değer **ayırıcısı ***\<anahtar >.*  
  
## <a name="remarks"></a>Açıklamalar  
 C++ Standart multiset sınıf kitaplığı:  
  
-   İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı.  
  
-   Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü yineleyiciler sağlar.  
  
-   Sıralıdır, çünkü öğeleri belirtilen karşılaştırma işlevine uygun olarak kapsayıcı içindeki anahtar değerlere göre sıralanır.  
  
-   Öğelerinin benzersiz anahtarlara ihtiyacı olmaması bakımından çokludur, böylece bir anahtar değer onunla ilişkili çok sayıda öğe değerine sahip olabilir.  
  
-   Basit bir ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerleridir.  
  
-   Bir şablon sınıfıdır, çünkü sağladığı işlevsellik geneldir ve böylece öğeler olarak kapsanan belirli veri türünden bağımsızdır. Kullanılacak veri türü, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda bir parametre olarak belirtilir.  
  
 Multiset sınıfı tarafından sağlanan yineleyici sınıf üyesi işlevleri ancak bir çift yönlü yineleyici olan [Ekle](#insert) ve [multiset](#multiset) daha zayıf bir giriş yineleyici şablonu parametreleri olarak ele sürümlerde çift yönlü yineleyiciler sınıfı tarafından garanti olandan daha az olan işlevselliği gereksinimleridir. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Her yineleyici kavramının kendi gereksinimler kümesi vardır ve bunlarla çalışan algoritmaların kendi varsayımlarını yineleyici türü tarafından sağlanan gereksinimlerle sınırlaması gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu en az işlevselliği kümesidir, ancak anlamlı yineleyiciler çeşitli hakkında iletişim kurabilmesi için yeterlidir [ `First`, `Last`) sınıfının üye işlevleri bağlamında.  
  
 Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. İlişkilendirilebilir kapsayıcılar, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Bu işlemleri açıkça destekleyen üye işlevleri, işlevlerini kapsayıcıdaki öğelerin sayısının logaritmasına ortalama orantılı bir sürede gerçekleştirir ve verimlidir. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.  
  
 Çoklu küme, değerleri onların kendi anahtarlarıyla ilişkilendiren koşullar uygulama tarafından karşılandığında seçimin ilişkili kapsayıcısı olmalıdır. Bir çoklu kümenin öğeleri birden çok olabilir ve anahtarlar benzersiz olmadıklarından kendi sıralama anahtarları olarak hizmet verebilir. Bu tür bir yapı modeli, sözcüklerin birden çok defa geçebildiği sıralı bir sözcükler listesindedir. Sözcüklerin birden çok defa geçmelerine izin verilmediğinde, bir küme uygun bir kapsayıcı yapısı olacaktır. Benzersiz tanımlar benzersiz anahtar sözcükler listesine değerler olarak eklendiyse, bir eşlem verileri kapsayacak uygun bir yapı olacaktır. Bunun yerine tanımlar benzersiz değilse, seçilecek kapsayıcı bir çoklu eşlem olurdu.  
  
 Multiset denetimleri saklı işlev nesnesi türü çağırarak dizisi siparişleri `Compare`. Üye işlevini çağırarak erişilebilir bir karşılaştırma işlevi bu saklı nesnesidir [key_comp](#key_comp). Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. İkili karşılaştırma *f*( *x*, *y*) iki bağımsız değişken nesnelere sahip bir işlev nesnesidir *x* ve *y* dönüş değerini **true** veya **false**. İkili karşılaştırma dönüşsüz, ters ve geçişli ve burada iki nesneleri eşdeğer geçişli ise, sıralama katı bir zayıf bir kümesi üzerinde uygulanan sıralama olduğu x ve y ne zaman eşdeğer olarak tanımlanan her ikisi de *f*( *x, y*) ve *f*( *y, x*) yanlış ise. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.  
  
 C ++ 14'te belirterek heterojen arama etkinleştirebilirsiniz `std::less<>` veya `std::greater<>` tür parametresi yok koşulu. Daha fazla bilgi için bkz: [ilişkilendirilebilir kapsayıcılarında heterojen arama](../standard-library/stl-containers.md#sequence_containers)  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[Multiset](#multiset)|Oluşturan bir `multiset` diğer bir deyişle boş veya diğer bir deyişle tüm kopyasını veya belirtilen bir parçası `multiset`.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|Typedef için `allocator` için sınıf `multiset` nesnesi.|  
|[const_iterator](#const_iterator)|Typedef okuyabilir çift yönlü yineleyici için bir `const` öğesinde `multiset`.|  
|[const_pointer](#const_pointer)|Typedef için bir işaretçi bir `const` öğesinde bir `multiset`.|  
|[const_reference](#const_reference)|Typedef başvuru için bir `const` öğesi saklanan bir `multiset` okumak ve gerçekleştirmek için `const` işlemleri.|  
|[const_reverse_iterator](#const_reverse_iterator)|Typedef herhangi okuyabilir çift yönlü yineleyici için `const` öğesinde `multiset`.|  
|[difference_type](#difference_type)|İmzalı tamsayı typedef öğelerinin sayısı için bir `multiset` yineleyiciler tarafından işaret öğeler arasındaki bir aralıkta.|  
|[iterator](#iterator)|Typedef okumak veya herhangi bir öğeyi değiştirmek için bir çift yönlü yineleyici için bir `multiset`.|  
|[key_compare](#key_compare)|Typedef göreli içinde iki öğe sırasını belirlemek için iki anahtar karşılaştırabilirsiniz bir işlev nesnesi için `multiset`.|  
|[key_type](#key_type)|Typedef göreli içinde iki öğe sırasını belirlemek için iki sıralama anahtarları karşılaştırabilirsiniz bir işlev nesnesi için `multiset`.|  
|[pointer](#pointer)|Typedef bir işaretçi bir öğe için bir `multiset`.|  
|[reference](#reference)|Typedef depolanan bir öğe başvurusu için bir `multiset`.|  
|[reverse_iterator](#reverse_iterator)|Typedef okuma veya bir öğedeki bir ters değiştirmek için bir çift yönlü yineleyici için `multiset`.|  
|[size_type](#size_type)|Öğe sayısı gösterebilir bir işaretsiz tamsayı türü bir `multiset`.|  
|[value_compare](#value_compare)|İki öğe içindeki göreli sıralarına belirlemek için sıralama anahtarları olarak karşılaştırabilirsiniz bir işlev nesnesi typedef `multiset`.|  
|[value_type](#value_type)|Bir öğe saklanan bir nesneyi tanımlayan bir typedef bir `multiset` kapasitesi değeri olarak içinde.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[Başlangıç](#begin)|İlk öğe işaret yineleyici döndürür `multiset`.|  
|[cbegin](#cbegin)|İlk öğe adresleri const bir yineleyici döndürür `multiset`.|  
|[cend](#cend)|Son öğesi başarılı konumu adresleri const bir yineleyici döndüren bir `multiset`.|  
|[Temizle](#clear)|Tüm öğeleri sildiği bir `multiset`.|  
|[Sayısı](#count)|Öğelerin sayısını döndürür bir `multiset` olan anahtarıyla eşleşen bir parametre olarak belirtilen anahtar.|  
|[crbegin](#crbegin)|Ters çevrilen kümedeki ilk öğeyi ele alan bir sabit yineleyici döndürür.|  
|[crend](#crend)|Ters çevrilen kümedeki son öğeden sonra gelen konumu ele alan bir sabit yineleyici döndürür.|  
|[emplace](#emplace)|Yerinde oluşturulan bir öğe ekler bir `multiset`.|  
|[emplace_hint](#emplace_hint)|Yerinde oluşturulan bir öğe ekler bir `multiset`, yerleştirme İpucu ile.|  
|[empty](#empty)|Testleri bir `multiset` boş.|  
|[Bitiş](#end)|Son öğesi sonra konumuna işaret yineleyici döndüren bir `multiset`.|  
|[equal_range](#equal_range)|Yineleyicilerin bir çiftini döndürür. İlk öğe çifti işaret ilk yineleyici bir `multiset` belirtilen anahtar daha büyük bir anahtar. İlk öğe çifti işaret ikinci yineleyici `multiset` eşit veya bundan büyük anahtarı bir anahtara sahip.|  
|[silme](#erase)|Bir öğenin veya bir dizi öğeleri kaldırır bir `multiset` belirtilen konumları veya belirtilen anahtar eşleşen kaldırır öğeleri.|  
|[find](#find)|Bir öğenin ilk konumuna işaret eden bir yineleyici döndüren bir `multiset` anahtarın belirtilen anahtara sahip.|  
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` oluşturmak için kullanılan nesne `multiset`.|  
|[insert](#insert)|Bir öğenin veya bir dizi elemanlara ekler bir `multiset`.|  
|[key_comp](#key_comp)|Göreli içinde iki öğe sırasını belirlemek için iki sıralama anahtarları karşılaştırabilirsiniz bir işlev nesnesi sağlar `multiset`.|  
|[lower_bound](#lower_bound)|Yineleyici ilk öğe döndürür bir `multiset` eşit veya bundan büyük belirtilen anahtar bir anahtara sahip.|  
|[max_size](#max_size)|En büyük uzunluğunu döndürür `multiset`.|  
|[rbegin](#rbegin)|İlk öğe bir ters işaret yineleyici döndürür `multiset`.|  
|[rend](#rend)|Son öğesi bir ters başarılı konumuna işaret eden bir yineleyici döndürür `multiset`.|  
|[Boyutu](#size)|Öğelerin sayısını döndürür bir `multiset`.|  
|[Değiştirme](#swap)|İki öğelerini alış verişleri `multiset`s.|  
|[upper_bound](#upper_bound)|Yineleyici ilk öğe döndürür bir `multiset` belirtilen anahtar daha büyük bir anahtar.|  
|[value_comp](#value_comp)|Sipariş öğesi değerleri için kullanılan karşılaştırma nesnesinin bir kopyasını alır bir `multiset`.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator=](#op_eq)|Öğeleri değiştirir bir `multiset` başka bir kopyasına sahip `multiset`.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<ayarlamak >  
  
 **Namespace:** std  
  
##  <a name="allocator_type"></a>  multiset::allocator_type  
 Allocator sınıfı multiset nesnesinin temsil eden bir tür  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `allocator_type` Şablon parametresi için bir eş anlamlı olduğundan `Allocator`.  
  
 Daha fazla bilgi için `Allocator`, Açıklamalar bölümüne bakın [multiset sınıfı](../standard-library/multiset-class.md) konu.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [get_allocator](#get_allocator) bir örnek kullanmak için `allocator_type`  
  
##  <a name="begin"></a>  multiset::Begin  
 Multiset ilk öğe adresleme yineleyici döndürür.  
  
```  
const_iterator begin() const;

iterator begin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Multiset veya boş multiset başarılı konumu ilk öğe adresleme çift yönlü yineleyici.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_begin.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   multiset <int> ms1;  
   multiset <int>::iterator ms1_Iter;  
   multiset <int>::const_iterator ms1_cIter;  
  
   ms1.insert( 1 );  
   ms1.insert( 2 );  
   ms1.insert( 3 );  
  
   ms1_Iter = ms1.begin( );  
   cout << "The first element of ms1 is " << *ms1_Iter << endl;  
  
   ms1_Iter = ms1.begin( );  
   ms1.erase( ms1_Iter );  
  
   // The following 2 lines would err as the iterator is const  
   // ms1_cIter = ms1.begin( );  
   // ms1.erase( ms1_cIter );  
  
   ms1_cIter = ms1.begin( );  
   cout << "The first element of ms1 is now " << *ms1_cIter << endl;  
}  
```  
  
```Output  
The first element of ms1 is 1  
The first element of ms1 is now 2  
```  
  
##  <a name="cbegin"></a>  multiset::cbegin  
 Döndürür bir `const` aralığın ilk öğe adresleri yineleyici.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `const` ilk öğede aralığı ya da yalnızca boş bir aralığın ötesinde konumunu işaret çift yönlü erişim yineleyici (boş bir aralığın için `cbegin() == cend()`).  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri ile `cbegin`, öğeleri aralığında değiştirilemez.  
  
 Bu üye işlevi yerine kullanabileceğiniz `begin()` üye işlevi dönüş değeri garanti `const_iterator`. Genellikle, ile birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` bir değiştirilebilir için (olmayan `const`) destekleyen herhangi bir türde kapsayıcı `begin()` ve `cbegin()`.  
  
```cpp  
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator  
```  
  
##  <a name="cend"></a>  multiset::cend  
 Döndürür bir `const` konumun yalnızca bir aralıkta son öğenin ötesinde adresleri yineleyici.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `const` yalnızca aralığın sonunu aşan işaret çift yönlü erişim yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 `cend` Yineleyici kendi aralığının sonunu geçti olup olmadığını test etmek için kullanılır.  
  
 Bu üye işlevi yerine kullanabileceğiniz `end()` üye işlevi dönüş değeri garanti `const_iterator`. Genellikle, ile birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` bir değiştirilebilir için (olmayan `const`) destekleyen herhangi bir türde kapsayıcı `end()` ve `cend()`.  
  
```cpp  
auto i1 = Container.end();
// i1 is Container<T>::iterator   
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator  
```  
  
 Tarafından döndürülen değer `cend` değil başvuru yapıldı.  
  
##  <a name="clear"></a>  multiset::Clear  
 Bir çoklu küme tüm öğeleri siler.  
  
```  
void clear();
```  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_clear.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   multiset <int> ms1;  
  
   ms1.insert( 1 );  
   ms1.insert( 2 );  
  
   cout << "The size of the multiset is initially "  
        << ms1.size( ) << "." << endl;  
  
   ms1.clear( );  
   cout << "The size of the multiset after clearing is "   
        << ms1.size( ) << "." << endl;  
}  
```  
  
```Output  
The size of the multiset is initially 2.  
The size of the multiset after clearing is 0.  
```  
  
##  <a name="const_iterator"></a>  multiset::const_iterator  
 Çift yönlü yineleyici bu can sağlayan bir türü okuma bir **const** multiset öğe.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [başlamak](#begin) kullanarak bir örnek için `const_iterator`.  
  
##  <a name="const_pointer"></a>  multiset::const_pointer  
 Bir işaretçi sağlayan bir türü bir **const** bir multiset öğe.  
  
```  
typedef typename allocator_type::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.  
  
 Çoğu durumda, bir [yineleyici](#iterator) çok kümeli nesnesindeki öğelerin erişmek için kullanılmalıdır.  
  
##  <a name="const_reference"></a>  multiset::const_reference  
 Bir başvuru sağlayan bir türü bir **const** okumak ve gerçekleştirmek için bir çoklu küme depolanan öğesi **const** işlemleri.  
  
```  
typedef typename allocator_type::const_reference const_reference;  
```  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_const_ref.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int> ms1;  
  
   ms1.insert( 10 );  
   ms1.insert( 20 );  
  
   // Declare and initialize a const_reference &Ref1   
   // to the 1st element  
   const int &Ref1 = *ms1.begin( );  
  
   cout << "The first element in the multiset is "  
        << Ref1 << "." << endl;  
  
   // The following line would cause an error because the   
   // const_reference cannot be used to modify the multiset  
   // Ref1 = Ref1 + 5;  
}  
```  
  
```Output  
The first element in the multiset is 10.  
```  
  
##  <a name="const_reverse_iterator"></a>  multiset::const_reverse_iterator  
 Herhangi bir çift yönlü yineleyici bu can sağlayan bir türü okuma **const** multiset öğe.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_reverse_iterator` bir öğenin değerini değiştiremez ve kullanın ters multiset yinelemek için.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [rend](#rend) bildirme ve kullanma konusunda bir örnek için `const_reverse_iterator`.  
  
##  <a name="count"></a>  multiset::Count  
 Parametresi belirtilen bir anahtarı olan anahtarla eşleşen bir multiset öğe sayısını döndürür.  
  
```  
size_type count(const Key& key) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Öğeleri multiset eşleştirilmesi için anahtar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Parametre anahtarı olan sıralama anahtarı eşleşen multiset öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini öğe sayısını döndürür *x* aralığında  
  
 [ `lower_bound` (_ *Key* ), `upper_bound` (\_ *Key* ) ).  
  
### <a name="example"></a>Örnek  
  Aşağıdaki örnek multiset::count üye fonksiyonu kullanımını göstermektedir.  
  
```  
// multiset_count.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    multiset<int> ms1;  
    multiset<int>::size_type i;  
  
    ms1.insert(1);  
    ms1.insert(1);  
    ms1.insert(2);  
  
    // Elements do not need to be unique in multiset,  
    // so duplicates are allowed and counted.  
    i = ms1.count(1);  
    cout << "The number of elements in ms1 with a sort key of 1 is: "  
         << i << "." << endl;  
  
    i = ms1.count(2);  
    cout << "The number of elements in ms1 with a sort key of 2 is: "  
         << i << "." << endl;  
  
    i = ms1.count(3);  
    cout << "The number of elements in ms1 with a sort key of 3 is: "  
         << i << "." << endl;  
}  
```  
  
```Output  
The number of elements in ms1 with a sort key of 1 is: 2.  
The number of elements in ms1 with a sort key of 2 is: 1.  
The number of elements in ms1 with a sort key of 3 is: 0.  
```  
  
##  <a name="crbegin"></a>  multiset::crbegin  
 İlk öğe ters multiset adresleme const yineleyici döndürür.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir const ilk öğe ters multiset adresleme veya ne son öğe içinde unreversed multiset olsaydı adresleme çift yönlü yineleyici ters çevrilir.  
  
### <a name="remarks"></a>Açıklamalar  
 `crbegin` ile birlikte kullanılan ters multiset başlatmak gibi bir çoklu küme ile kullanılır.  
  
 Dönüş değeri ile `crbegin`, birden çok küme nesnesi değiştirilemez.  
  
 `crbegin` multiset geriye doğru yinelemek için kullanılabilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_crbegin.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   multiset <int> ms1;  
   multiset <int>::const_reverse_iterator ms1_crIter;  
  
   ms1.insert( 10 );  
   ms1.insert( 20 );  
   ms1.insert( 30 );  
  
   ms1_crIter = ms1.crbegin( );  
   cout << "The first element in the reversed multiset is "  
        << *ms1_crIter << "." << endl;  
}  
```  
  
```Output  
The first element in the reversed multiset is 30.  
```  
  
##  <a name="crend"></a>  multiset::crend  
 Son öğe ters bir çoklu küme içinde başarılı konumu adresleri const bir yineleyici döndürür.  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir const ters multiset (ilk öğe unreversed multiset öncesinde konum), son öğe başarılı konumu adresleri çift yönlü yineleyici ters çevrilir.  
  
### <a name="remarks"></a>Açıklamalar  
 `crend` Ters multiset ile kullanılan gibi [son](#end) multiset ile kullanılır.  
  
 Dönüş değeri ile `crend`, birden çok küme nesnesi değiştirilemez.  
  
 `crend` Ters yineleyici kendi multiset sonuna olup ulaştı için test etmek için kullanılabilir.  
  
 Tarafından döndürülen değer `crend` değil başvuru yapıldı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_crend.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main() {  
   using namespace std;     
   multiset <int> ms1;  
   multiset <int>::const_reverse_iterator ms1_crIter;  
  
   ms1.insert( 10 );  
   ms1.insert( 20 );  
   ms1.insert( 30 );  
  
   ms1_crIter = ms1.crend( ) ;  
   ms1_crIter--;  
   cout << "The last element in the reversed multiset is "  
        << *ms1_crIter << "." << endl;  
}  
```  
  
##  <a name="difference_type"></a>  multiset::difference_type  
 Yineleyiciler tarafından işaret öğeler arasındaki bir aralıkta multiset öğe sayısını temsil etmek için kullanılan bir imzalı tamsayı türü.  
  
```  
typedef typename allocator_type::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `difference_type` Türü çıkarılmasıyla veya kapsayıcı yineleyiciler artırma döndürülür. `difference_type` Genellikle aralığında öğe sayısını temsil etmek için kullanılan [ `first`, `last`) yineleyiciler arasında `first` ve `last`, gösterdiği öğesi içerir `first` ve öğeleri kadar aralığı , ancak değil de dahil olmak üzere, gösterdiği öğesi `last`.  
  
 Ancak unutmayın `difference_type` çıkarma yineleyiciler arasında yalnızca kümesidir gibi ters çevrilebilir kapsayıcıları tarafından desteklenen çift yönlü yineleyiciler sınıfı içeren bir giriş yineleyici gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir rasgele erişim kapsayıcı vektör gibi tarafından sağlanan rasgele erişim yineleyiciler tarafından desteklenir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <set>  
#include <algorithm>  
  
int main( )  
{  
   using namespace std;  
  
   multiset <int> ms1;  
   multiset <int>::iterator ms1_Iter, ms1_bIter, ms1_eIter;  
  
   ms1.insert( 20 );  
   ms1.insert( 10 );  
   ms1.insert( 20 );  
  
   ms1_bIter = ms1.begin( );  
   ms1_eIter = ms1.end( );  
  
   multiset <int>::difference_type   df_typ5, df_typ10, df_typ20;  
  
   df_typ5 = count( ms1_bIter, ms1_eIter, 5 );  
   df_typ10 = count( ms1_bIter, ms1_eIter, 10 );  
   df_typ20 = count( ms1_bIter, ms1_eIter, 20 );  
  
   // The keys, and hence the elements, of a multiset are not unique  
   cout << "The number '5' occurs " << df_typ5  
        << " times in multiset ms1.\n";  
   cout << "The number '10' occurs " << df_typ10  
        << " times in multiset ms1.\n";  
   cout << "The number '20' occurs " << df_typ20  
        << " times in multiset ms1.\n";  
  
   // Count the number of elements in a multiset   
   multiset <int>::difference_type  df_count = 0;  
   ms1_Iter = ms1.begin( );  
   while ( ms1_Iter != ms1_eIter)  
   {  
      df_count++;  
      ms1_Iter++;  
   }  
  
   cout << "The number of elements in the multiset ms1 is: "   
        << df_count << "." << endl;  
}  
```  
  
```Output  
The number '5' occurs 0 times in multiset ms1.  
The number '10' occurs 1 times in multiset ms1.  
The number '20' occurs 2 times in multiset ms1.  
The number of elements in the multiset ms1 is: 3.  
```  
  
##  <a name="emplace"></a>  multiset::emplace  
 Yerinde (hiçbir kopyalama veya taşıma işlemler gerçekleştirilir), yerleştirme İpucu ile oluşturulan bir öğe ekler.  
  
```  
template <class... Args>  
iterator emplace(Args&&... args);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`args`|Multiset eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici yeni eklenen öğesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kapsayıcı öğeleri için başvuru bu işlev tarafından geçersiz kılınır, ancak tüm yineleyiciler kapsayıcısı için geçersiz kılabilir.  
  
 Bir özel durum, emplacement sırasında kapsayıcının durumu değiştirilemez.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_emplace.cpp  
// compile with: /EHsc  
#include <set>  
#include <string>  
#include <iostream>  
  
using namespace std;  
  
template <typename S> void print(const S& s) {  
    cout << s.size() << " elements: ";  
  
    for (const auto& p : s) {  
        cout << "(" << p << ") ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    multiset<string> s1;  
  
    s1.emplace("Anna");  
    s1.emplace("Bob");  
    s1.emplace("Carmine");  
  
    cout << "multiset modified, now contains ";  
    print(s1);  
    cout << endl;  
  
    s1.emplace("Bob");  
  
    cout << "multiset modified, now contains ";  
    print(s1);  
    cout << endl;  
}  
  
```  
  
##  <a name="emplace_hint"></a>  multiset::emplace_hint  
 Yerinde (hiçbir kopyalama veya taşıma işlemler gerçekleştirilir), yerleştirme İpucu ile oluşturulan bir öğe ekler.  
  
```  
template <class... Args>  
iterator emplace_hint(
    const_iterator where,  
    Args&&... args);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`args`|Multiset eklenecek bir öğe oluşturmak için iletilen bağımsız değişkenler.|  
|`where`|Ekleme için doğru noktası aramaya başlamak için koyun. (O noktadan hemen önceyse `where`, ekleme Logaritmik zaman yerine amortized sabit zaman meydana gelebilir.)|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyici yeni eklenen öğesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kapsayıcı öğeleri için başvuru bu işlev tarafından geçersiz kılınır, ancak tüm yineleyiciler kapsayıcısı için geçersiz kılabilir.  
  
 Bir özel durum, emplacement sırasında kapsayıcının durumu değiştirilemez.  
  
 Kod örneği için bkz: [set::emplace_hint](../standard-library/set-class.md#emplace_hint).  
  
##  <a name="empty"></a>  multiset::empty  
 Bir çoklu küme boşsa, testleri.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** multiset boşsa; **false** multiset boş olmayan ise.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_empty.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int> ms1, ms2;  
   ms1.insert ( 1 );  
  
   if ( ms1.empty( ) )  
      cout << "The multiset ms1 is empty." << endl;  
   else  
      cout << "The multiset ms1 is not empty." << endl;  
  
   if ( ms2.empty( ) )  
      cout << "The multiset ms2 is empty." << endl;  
   else  
      cout << "The multiset ms2 is not empty." << endl;  
}  
```  
  
```Output  
The multiset ms1 is not empty.  
The multiset ms2 is empty.  
```  
  
##  <a name="end"></a>  multiset::End  
 past-the-end yineleyici döndürür.  
  
```  
const_iterator end() const;

 
 
iterator end();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçmiş--end yineleyici. Multiset boş ise, `multiset::end() == multiset::begin()`.  
  
### <a name="remarks"></a>Açıklamalar  
 **Son** yineleyici kendi multiset sonunu geçti olup olmadığını test etmek için kullanılır.  
  
 Tarafından döndürülen değer **son** değil başvuru yapıldı.  
  
 Kod örneği için bkz: [multiset::find](#find).  
  
##  <a name="equal_range"></a>  multiset::equal_range  
 Yineleyiciler çifti sırasıyla multiset belirtilen anahtar daha büyük bir anahtarla ilk öğe ve eşit veya bundan büyük anahtarı bir anahtarla multiset ilk öğe döndürür.  
  
```  
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Aranmakta multiset öğeden sıralama anahtarı ile Karşılaştırılacak bağımsız değişkeni anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyiciler çifti ilk olacak şekilde, [lower_bound](#lower_bound) anahtarı ve ikincisi [upper_bound](#upper_bound) anahtarı.  
  
 İlk yineleyici çiftinin erişmek için `pr` üye işlevi tarafından döndürülen, kullanmak `pr`. **İlk**ve alt sınır yineleyici başvurulacak kullanmak \*( `pr`. **first**). İkinci yineleyici çiftinin erişmek için `pr` üye işlevi tarafından döndürülen, kullanmak `pr`. **İkinci**ve üst sınır yineleyici başvurulacak kullanmak \*( `pr`. **İkinci**).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_equal_range.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;      
   typedef multiset<int, less<int> > IntSet;  
   IntSet ms1;  
   multiset <int> :: const_iterator ms1_RcIter;  
  
   ms1.insert( 10 );  
   ms1.insert( 20 );  
   ms1.insert( 30 );  
  
   pair <IntSet::const_iterator, IntSet::const_iterator> p1, p2;  
   p1 = ms1.equal_range( 20 );  
  
   cout << "The upper bound of the element with "  
        << "a key of 20 in the multiset ms1 is: "  
        << *( p1.second ) << "." << endl;  
  
   cout << "The lower bound of the element with "  
        << "a key of 20 in the multiset ms1 is: "  
        << *( p1.first ) << "." << endl;  
  
   // Compare the upper_bound called directly   
   ms1_RcIter = ms1.upper_bound( 20 );  
   cout << "A direct call of upper_bound( 20 ) gives "  
        << *ms1_RcIter << "," << endl  
        << "matching the 2nd element of the pair"  
        << " returned by equal_range( 20 )." << endl;  
  
   p2 = ms1.equal_range( 40 );  
  
   // If no match is found for the key,  
   // both elements of the pair return end( )  
   if ( ( p2.first == ms1.end( ) ) && ( p2.second == ms1.end( ) ) )  
      cout << "The multiset ms1 doesn't have an element "  
              << "with a key less than 40." << endl;  
   else  
      cout << "The element of multiset ms1 with a key >= 40 is: "  
                << *( p1.first ) << "." << endl;  
}  
```  
  
```Output  
The upper bound of the element with a key of 20 in the multiset ms1 is: 30.  
The lower bound of the element with a key of 20 in the multiset ms1 is: 20.  
A direct call of upper_bound( 20 ) gives 30,  
matching the 2nd element of the pair returned by equal_range( 20 ).  
The multiset ms1 doesn't have an element with a key less than 40.  
```  
  
##  <a name="erase"></a>  multiset::ERASE  
 Bir öğenin veya öğe aralığını belirtilen konumdan bir multiset kaldırır veya belirtilen anahtar eşleşen öğeleri kaldırır.  
  
```  
iterator erase(
    const_iterator Where);

iterator erase(
    const_iterator First,  
    const_iterator Last);

size_type erase(
    const key_type& Key);
```  
  
### <a name="parameters"></a>Parametreler  
 `Where`  
 Kaldırılacak öğe konumu.  
  
 `First`  
 Kaldırılacak ilk öğe konumu.  
  
 `Last`  
 Kaldırılacak yalnızca son öğenin ötesinde konumu.  
  
 `Key`  
 Kaldırılacak öğe anahtar değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk iki üye işlevleri için çift yönlü Yineleyici, kaldırılan öğelerin ya da böyle bir öğe varsa multiset sonuna olan bir öğeyi dışında kalan ilk öğe belirler.  
  
 Üye işlevi için üçüncü multiset kaldırılmış olan öğe sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Kod örneği için bkz: [set::erase](../standard-library/set-class.md#erase).  
  
##  <a name="find"></a>  multiset::Find  
 Belirtilen anahtar için eşdeğer bir anahtara sahip bir çoklu küme içinde bir öğe konuma başvuruyor yineleyici döndürür.  
  
```  
iterator find(const Key& key);

 
const_iterator find(const Key& key) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Aranmakta multiset öğeden sıralama anahtarı tarafından eşleştirilmesini anahtar değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen bir anahtarı olan bir öğe konumu ya da son öğe multiset başarılı konumu başvurduğu yineleyici ( `multiset::end()`) anahtar için bir eşleşme varsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi bağımsız değişkeninin bir multiset anahtar öğesiyle yineleyici eşdeğerdir döndürür `key` bir comparability ilişkisi küçüktür göre sıralama uygulanmasını ikili bir koşul altında.  
  
 Varsa dönüş değerini **Bul** atanmış bir **const_iterator**, multiset nesnesi değiştirilemez. Varsa dönüş değerini **Bul** atanmış bir **yineleyici**, çok kümeli nesne değiştirilebilir  
  
### <a name="example"></a>Örnek  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
#include <set>  
#include <iostream>  
#include <vector>  
#include <string>  
  
using namespace std;  
  
template <typename T> void print_elem(const T& t) {  
    cout << "(" << t << ") ";  
}  
  
template <typename T> void print_collection(const T& t) {  
    cout << t.size() << " elements: ";  
  
    for (const auto& p : t) {  
        print_elem(p);  
    }  
    cout << endl;  
}  
  
template <typename C, class T> void findit(const C& c, T val) {  
    cout << "Trying find() on value " << val << endl;  
    auto result = c.find(val);  
    if (result != c.end()) {  
        cout << "Element found: "; print_elem(*result); cout << endl;  
    } else {  
        cout << "Element not found." << endl;  
    }  
}  
  
int main()  
{  
    multiset<int> s1({ 40, 45 });  
    cout << "The starting multiset s1 is: " << endl;  
    print_collection(s1);  
  
    vector<int> v;  
    v.push_back(43);  
    v.push_back(41);  
    v.push_back(46);  
    v.push_back(42);  
    v.push_back(44);  
    v.push_back(44); // attempt a duplicate  
  
    cout << "Inserting the following vector data into s1: " << endl;  
    print_collection(v);  
  
    s1.insert(v.begin(), v.end());  
  
    cout << "The modified multiset s1 is: " << endl;  
    print_collection(s1);  
    cout << endl;  
    findit(s1, 45);  
    findit(s1, 6);  
}  
```  
  
##  <a name="get_allocator"></a>  multiset::get_allocator  
 Multiset oluşturmak için kullanılan ayırıcısı nesnesinin bir kopyasını döndürür.  
  
```  
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çoklu küme tarafından kullanılan ayırıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Allocators multiset sınıfı için sınıf depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan allocators çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak ileri düzeyde C++ bir konudur.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_get_allocator.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int>::allocator_type ms1_Alloc;  
   multiset <int>::allocator_type ms2_Alloc;  
   multiset <double>::allocator_type ms3_Alloc;  
   multiset <int>::allocator_type ms4_Alloc;  
  
   // The following lines declare objects  
   // that use the default allocator.  
   multiset <int> ms1;  
   multiset <int, allocator<int> > ms2;  
   multiset <double, allocator<double> > ms3;  
  
   cout << "The number of integers that can be allocated"  
        << endl << "before free memory is exhausted: "  
        << ms2.max_size( ) << "." << endl;  
  
   cout << "The number of doubles that can be allocated"  
        << endl << "before free memory is exhausted: "  
        << ms3.max_size( ) <<  "." << endl;  
  
   // The following lines create a multiset ms4  
   // with the allocator of multiset ms1  
   ms1_Alloc = ms1.get_allocator( );  
   multiset <int> ms4( less<int>( ), ms1_Alloc );  
   ms4_Alloc = ms4.get_allocator( );  
  
   // Two allocators are interchangeable if  
   // storage allocated from each can be  
   // deallocated with the other  
   if( ms1_Alloc == ms4_Alloc )     
   {  
      cout << "Allocators are interchangeable."  
           << endl;     
   }  
   else     
   {  
      cout << "Allocators are not interchangeable."  
           << endl;     
   }  
}  
```  
  
##  <a name="insert"></a>  multiset::insert  
 Bir öğenin veya bir dizi öğeleri multiset ekler.  
  
```  
// (1) single element  
pair<iterator, bool> insert(
    const value_type& Val);

 
// (2) single element, perfect forwarded  
template <class ValTy>  
pair<iterator, bool>  
insert(
    ValTy&& Val);

 
// (3) single element with hint  
iterator insert(
    const_iterator Where,  
    const value_type& Val);

 
// (4) single element, perfect forwarded, with hint  
template <class ValTy>  
iterator insert(
    const_iterator Where,  
    ValTy&& Val);

 
// (5) range   
template <class InputIterator>   
void insert(
    InputIterator First,  
    InputIterator Last);

 
// (6) initializer list  
void insert(
    initializer_list<value_type>  
IList);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Val`|Multiset Eklenecek öğenin değeri.|  
|`Where`|Ekleme için doğru noktası aramaya başlamak için koyun. (O noktadan hemen önceyse `Where`, ekleme Logaritmik zaman yerine amortized sabit zaman meydana gelebilir.)|  
|`ValTy`|Multiset öğesi oluşturmak için kullanabileceğiniz bağımsız değişken türünü belirten bir şablon parametresi [value_type](../standard-library/map-class.md#value_type)ve mükemmel ileten `Val` bağımsız değişken olarak.|  
|`First`|Kopyalanacak ilk öğe konumu.|  
|`Last`|Kopyalanacak yalnızca son öğenin ötesinde konumu.|  
|`InputIterator`|Gereksinimlerini karşılayan şablon işlevi bağımsız değişken bir [giriş yineleyici](../standard-library/input-iterator-tag-struct.md) oluşturmak için kullanılan bir türü öğelerine işaret [value_type](../standard-library/map-class.md#value_type) nesneleri.|  
|`IList`|[İnitializer_list](../standard-library/initializer-list.md) öğeleri kopyalanacak.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tek öğe Ekle üye işlevleri (1) ve (2), yineleyici yeni öğe multiset burada eklenmiş konumuna döndürür.  
  
 İpucu ile tek öğe üye işlevleri (3) ve (4), yeni öğe multiset eklenir burada konumuna işaret eden bir yineleyici döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İşaretçileri veya başvuruları olmadığından bu işlev tarafından geçersiz kılınır, ancak tüm yineleyiciler kapsayıcısı için geçersiz kılabilir.  
  
 Bir özel durum, yalnızca bir öğe ekleme sırasında kapsayıcının durumu değiştirilemez. Bir özel durum, birden çok öğe ekleme sırasında kapsayıcı belirtilmeyen ancak geçerli bir durumda bırakılır.  
  
 [Value_type](../standard-library/map-class.md#value_type) , bir kapsayıcı ve, küme ait bir typedef kapsayıcısıdır `multiset<V>::value_type` türü `const V`.  
  
 Aralık üye işlevi (5) aralığında bir yineleyici tarafından ele her öğesine karşılık gelen bir çoklu küme bir dizi öğesi değerlerini ekler `[First, Last)`; bu nedenle, `Last` takılı. Kapsayıcı üye fonksiyonu `end()` kapsayıcı son öğesi hemen sonra konuma başvuruyor — Örneğin, deyim `s.insert(v.begin(), v.end());` tüm öğeleri ekler `v` içine `s`.  
  
 Başlatıcı listesi üye işlevi (6) kullanan bir [initializer_list](../standard-library/initializer-list.md) öğeleri multiset kopyalamak için.  
  
 Yerinde oluşturulan bir öğe eklemeye — diğer bir deyişle, kopyalama veya taşıma işlemi yok gerçekleştirilen — bkz [multiset::emplace](#emplace) ve [multiset::emplace_hint](#emplace_hint).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_insert.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
#include <string>  
#include <vector>  
  
using namespace std;  
  
template <typename S> void print(const S& s) {  
    cout << s.size() << " elements: ";  
  
    for (const auto& p : s) {  
        cout << "(" << p << ") ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
  
    // insert single values   
    multiset<int> s1;  
    // call insert(const value_type&) version  
    s1.insert({ 1, 10 });  
    // call insert(ValTy&&) version   
    s1.insert(20);  
  
    cout << "The original multiset values of s1 are:" << endl;  
    print(s1);  
  
    // intentionally attempt a duplicate, single element  
    s1.insert(1);  
    cout << "The modified multiset values of s1 are:" << endl;  
    print(s1);  
    cout << endl;  
  
    // single element, with hint  
    s1.insert(s1.end(), 30);  
    cout << "The modified multiset values of s1 are:" << endl;  
    print(s1);  
    cout << endl;  
  
    // The templatized version inserting a jumbled range  
    multiset<int> s2;  
    vector<int> v;  
    v.push_back(43);  
    v.push_back(294);  
    v.push_back(41);  
    v.push_back(330);  
    v.push_back(42);  
    v.push_back(45);  
  
    cout << "Inserting the following vector data into s2:" << endl;  
    print(v);  
  
    s2.insert(v.begin(), v.end());  
  
    cout << "The modified multiset values of s2 are:" << endl;  
    print(s2);  
    cout << endl;  
  
    // The templatized versions move-constructing elements  
    multiset<string>  s3;  
    string str1("blue"), str2("green");  
  
    // single element  
    s3.insert(move(str1));  
    cout << "After the first move insertion, s3 contains:" << endl;  
    print(s3);  
  
    // single element with hint  
    s3.insert(s3.end(), move(str2));  
    cout << "After the second move insertion, s3 contains:" << endl;  
    print(s3);  
    cout << endl;  
  
    multiset<int> s4;  
    // Insert the elements from an initializer_list  
    s4.insert({ 4, 44, 2, 22, 3, 33, 1, 11, 5, 55 });  
    cout << "After initializer_list insertion, s4 contains:" << endl;  
    print(s4);  
    cout << endl;  
}  
  
```  
  
##  <a name="iterator"></a>  multiset::iterator  
 Bir sabit sağlayan bir türü [çift yönlü yineleyici](../standard-library/bidirectional-iterator-tag-struct.md) okuyabilen herhangi bir öğe bir multiset.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [başlamak](#begin) bildirme ve kullanma konusunda bir örnek için bir **yineleyici**.  
  
##  <a name="key_comp"></a>  multiset::key_comp  
 Bir multiset sipariş anahtarları için kullanılan karşılaştırma nesnesinin bir kopyasını alır.  
  
```  
key_compare key_comp() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şablon parametresi olan öğeleri, sipariş için bir çoklu küme kullanan işlevi nesnesi döndüren `Compare`.  
  
 Daha fazla bilgi için `Compare`, Açıklamalar bölümüne bakın [multiset sınıfı](../standard-library/multiset-class.md) konu.  
  
### <a name="remarks"></a>Açıklamalar  
 Saklanan nesne üye işlevini tanımlar:  
  
 **bool işleci**( **const anahtar &** *x*, **const anahtar &** *y*);  
  
 hangi döndürür ise true *x* kesinlikle önündeki *y* sıralama düzeninde.  
  
 Unutmayın her ikisi de [key_compare](#key_compare) ve [value_compare](#value_compare) şablon parametresi için eş anlamlı sözcükleri olan `Compare`. Her iki tür sınıfları harita ve burada ayrı multimap ile uyumluluk için aynı oldukları, multiset ve sınıfları kümesi için sağlanır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_key_comp.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   multiset <int, less<int> > ms1;  
   multiset <int, less<int> >::key_compare kc1 = ms1.key_comp( ) ;  
   bool result1 = kc1( 2, 3 ) ;  
   if( result1 == true )     
   {  
      cout << "kc1( 2,3 ) returns value of true, "  
           << "where kc1 is the function object of s1."  
           << endl;  
   }  
   else     
   {  
      cout << "kc1( 2,3 ) returns value of false "  
           << "where kc1 is the function object of ms1."  
           << endl;  
   }  
  
   multiset <int, greater<int> > ms2;  
   multiset <int, greater<int> >::key_compare kc2 = ms2.key_comp( ) ;  
   bool result2 = kc2( 2, 3 ) ;  
   if( result2 == true )     
   {  
      cout << "kc2( 2,3 ) returns value of true, "  
           << "where kc2 is the function object of ms2."  
           << endl;  
   }  
   else     
   {  
      cout << "kc2( 2,3 ) returns value of false, "  
           << "where kc2 is the function object of ms2."  
           << endl;  
   }  
}  
```  
  
```Output  
kc1( 2,3 ) returns value of true, where kc1 is the function object of s1.  
kc2( 2,3 ) returns value of false, where kc2 is the function object of ms2.  
```  
  
##  <a name="key_compare"></a>  multiset::key_compare  
 İşlev nesnesi sağlayan bir tür multiset göreli iki öğe sırasını belirlemek için iki sıralama anahtarları karşılaştırabilirsiniz.  
  
```  
typedef Compare key_compare;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 **key_compare** şablon parametresi için bir eş anlamlı olduğundan `Compare`.  
  
 Daha fazla bilgi için `Compare`, Açıklamalar bölümüne bakın [multiset sınıfı](../standard-library/multiset-class.md) konu.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [key_comp](#key_comp) bildirme ve kullanma konusunda bir örnek için `key_compare`.  
  
##  <a name="key_type"></a>  multiset::key_type  
 İşlev nesnesi sağlayan bir tür multiset göreli iki öğe sırasını belirlemek için sıralama anahtarları karşılaştırabilirsiniz.  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `key_type` Şablon parametresi için bir eş anlamlı olduğundan `Key`.  
  
 Daha fazla bilgi için `Key`, Açıklamalar bölümüne bakın [multiset sınıfı](../standard-library/multiset-class.md) konu.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.  
  
##  <a name="lower_bound"></a>  multiset::lower_bound  
 Yineleyici ilk öğesine eşit veya bundan büyük belirtilen anahtar bir anahtarı olan bir multiset döndürür.  
  
```  
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Aranmakta multiset öğeden sıralama anahtarı ile Karşılaştırılacak bağımsız değişkeni anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir **yineleyici** veya `const_iterator` eşit veya bundan büyük bağımsız değişkeni anahtar ya da son öğe yoksa multiset başarılı konumu adresleri bir anahtarla eşleşen bir multiset öğenin konumunu adresleri için anahtar bulunamadı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_lower_bound.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   multiset <int> ms1;  
   multiset <int> :: const_iterator ms1_AcIter, ms1_RcIter;  
  
   ms1.insert( 10 );  
   ms1.insert( 20 );  
   ms1.insert( 30 );  
  
   ms1_RcIter = ms1.lower_bound( 20 );  
   cout << "The element of multiset ms1 with a key of 20 is: "  
        << *ms1_RcIter << "." << endl;  
  
   ms1_RcIter = ms1.lower_bound( 40 );  
  
   // If no match is found for the key, end( ) is returned  
   if ( ms1_RcIter == ms1.end( ) )  
      cout << "The multiset ms1 doesn't have an element "  
           << "with a key of 40." << endl;  
   else  
      cout << "The element of multiset ms1 with a key of 40 is: "  
           << *ms1_RcIter << "." << endl;  
  
   // The element at a specific location in the multiset can be   
   // found using a derefenced iterator addressing the location  
   ms1_AcIter = ms1.end( );  
   ms1_AcIter--;  
   ms1_RcIter = ms1.lower_bound( *ms1_AcIter );  
   cout << "The element of ms1 with a key matching "  
        << "that of the last element is: "  
        << *ms1_RcIter << "." << endl;  
}  
```  
  
```Output  
The element of multiset ms1 with a key of 20 is: 20.  
The multiset ms1 doesn't have an element with a key of 40.  
The element of ms1 with a key matching that of the last element is: 30.  
```  
  
##  <a name="max_size"></a>  multiset::max_size  
 Multiset en büyük uzunluğunu döndürür.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Multiset en fazla olası uzunluğu.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_max_size.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   multiset <int> ms1;  
   multiset <int>::size_type i;  
  
   i = ms1.max_size( );     
   cout << "The maximum possible length "  
        << "of the multiset is " << i << "." << endl;  
}  
```  
  
##  <a name="multiset"></a>  multiset::multiset  
 Boş veya tüm kopyalama veya başka bir multiset parçası olan bir çoklu küme oluşturur.  
  
```  
multiset();

explicit multiset (
    const Compare& Comp);

multiset (
    const Compare& Comp,  
    const Allocator& Al);

multiset(
    const multiset& Right);

multiset(
    multiset&& Right);

multiset(
    initializer_list<Type> IList);

multiset(
    initializer_list<Type> IList,   
    const Compare& Comp);

multiset(
    initializer_list<Type> IList,   
    const Compare& Comp,   
    const Allocator& Al);

 
template <class InputIterator>  
multiset (
    InputIterator First,  
    InputIterator Last);

template <class InputIterator>  
multiset (
    InputIterator First,  
    InputIterator Last,  
    const Compare& Comp);

template <class InputIterator>  
multiset (
    InputIterator First,  
    InputIterator Last,  
    const Compare& Comp,  
    const Allocator& Al);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Al`|Varsayılan olarak bu çok kümeli nesne için kullanılacak depolama allocator sınıfı `Allocator`.|  
|`Comp`|Türü karşılaştırma işlevinden `const Compare` öğeler için varsayılanları çoklu küme içinde sıralamak için kullanılan `Compare`.|  
|`Right`|Oluşturulan multiset kopyasını olmasını olduğu multiset.|  
|`First`|Kopyalanacak öğe aralığını ilk öğe konumu.|  
|`Last`|Kopyalanacak öğeleri aralık ötesinde ilk öğe konumu.|  
|`IList`|Öğelerin kopyalanacağı initializer_list.|  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm Oluşturucular, bellek depolama için multiset yönetir ve, daha sonra döndürülüp döndürülmediğini çağırarak ayırıcısı nesne türünü depolamak [get_allocator](#get_allocator). Allocator parametresi, sınıf bildirimleri ve diğer allocators yerine kullanılacak önişlem makroları genellikle atlanır.  
  
 Tüm oluşturucular kendi multiset başlatır.  
  
 Bir işlev nesnesi bir sipariş multiset anahtarlar oluşturmak için kullanılan ve, daha sonra döndürülüp döndürülmediğini çağırarak karşılaştırma türü tüm oluşturucular deposu [key_comp](#key_comp).  
  
 İlk üç oluşturucular belirtin boş ilk multiset, ikinci karşılaştırma işlev türünü belirtme ( `Comp`) öğeleri ve üçüncü sırasını oluşturmada kullanılacak ayırıcı açıkça belirtilmesi yazın ( `Al`) için kullanılabilir. Anahtar sözcüğü `explicit` otomatik tür dönüştürme belirli türdeki gizler.  
  
 Multiset bir kopyasını dördüncü Oluşturucusu belirtir `Right`.  
  
 Beşinci Oluşturucusu taşıyarak multiset kopyasını belirtir `Right`.  
  
 Altıncı, yedinci ve sekizinci oluşturucular bir initializer_list öğeleri kopyalama kaynağı belirtin.  
  
 Sonraki üç oluşturucular aralığı kopyalayın `[First, Last)` türü karşılaştırma işlevinden ve ayırıcısı belirtme içinde explicitness artan bir çoklu küme.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_ctor.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    //multiset <int>::iterator ms1_Iter, ms2_Iter, ms3_Iter;  
    multiset <int>::iterator ms4_Iter, ms5_Iter, ms6_Iter, ms7_Iter;  
  
    // Create an empty multiset ms0 of key type integer  
    multiset <int> ms0;  
  
    // Create an empty multiset ms1 with the key comparison  
    // function of less than, then insert 4 elements  
    multiset <int, less<int> > ms1;  
    ms1.insert(10);  
    ms1.insert(20);  
    ms1.insert(20);  
    ms1.insert(40);  
  
    // Create an empty multiset ms2 with the key comparison  
    // function of geater than, then insert 2 elements  
    multiset <int, less<int> > ms2;  
    ms2.insert(10);  
    ms2.insert(20);  
  
    // Create a multiset ms3 with the   
    // allocator of multiset ms1  
    multiset <int>::allocator_type ms1_Alloc;  
    ms1_Alloc = ms1.get_allocator();  
    multiset <int> ms3(less<int>(), ms1_Alloc);  
    ms3.insert(30);  
  
    // Create a copy, multiset ms4, of multiset ms1  
    multiset <int> ms4(ms1);  
  
    // Create a multiset ms5 by copying the range ms1[ first,  last)  
    multiset <int>::const_iterator ms1_bcIter, ms1_ecIter;  
    ms1_bcIter = ms1.begin();  
    ms1_ecIter = ms1.begin();  
    ms1_ecIter++;  
    ms1_ecIter++;  
    multiset <int> ms5(ms1_bcIter, ms1_ecIter);  
  
    // Create a multiset ms6 by copying the range ms4[ first,  last)  
    // and with the allocator of multiset ms2  
    multiset <int>::allocator_type ms2_Alloc;  
    ms2_Alloc = ms2.get_allocator();  
    multiset <int> ms6(ms4.begin(), ++ms4.begin(), less<int>(), ms2_Alloc);  
  
    cout << "ms1 =";  
    for (auto i : ms1)  
        cout << " " << i;  
    cout << endl;  
  
    cout << "ms2 =";  
    for (auto i : ms2)  
        cout << " " << i;  
   cout << endl;  
  
   cout << "ms3 =";  
   for (auto i : ms3)  
       cout << " " << i;  
    cout << endl;  
  
    cout << "ms4 =";  
    for (auto i : ms4)  
        cout << " " << i;  
    cout << endl;  
  
    cout << "ms5 =";  
    for (auto i : ms5)  
        cout << " " << i;  
    cout << endl;  
  
    cout << "ms6 =";  
    for (auto i : ms6)  
        cout << " " << i;  
    cout << endl;  
  
    // Create a multiset by moving ms5  
    multiset<int> ms7(move(ms5));  
    cout << "ms7 =";  
    for (auto i : ms7)  
        cout << " " << i;  
    cout << endl;  
  
    // Create a multiset with an initializer_list  
    multiset<int> ms8({1, 2, 3, 4});  
    cout << "ms8=";  
    for (auto i : ms8)  
        cout << " " << i;  
    cout << endl;  
}  
```  
  
##  <a name="op_eq"></a>  multiset::operator=  
 Bu öğeleri değiştirir `multiset` kullanan başka bir öğeler `multiset`.  
  
```  
multiset& operator=(const multiset& right);

multiset& operator=(multiset&& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`right`|`multiset` Hangi öğelerin kopyaladığınız veya taşındı.|  
  
### <a name="remarks"></a>Açıklamalar  
 `operator=` kopyalar veya öğeleri taşır `right` kopyalayıp bu `multiset`bağlı olarak kullanılan bir başvuru türü (lvalue veya rvalue). Bu öğeleri `multiset` önce `operator=` yürütür atılır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_operator_as.cpp  
// compile with: /EHsc  
#include <multiset>  
#include <iostream>  
  
int main( )  
   {  
   using namespace std;  
   multiset<int> v1, v2, v3;  
   multiset<int>::iterator iter;  
  
   v1.insert(10);  
  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
   v2 = v1;  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
// move v1 into v2  
   v2.clear();  
   v2 = move(v1);  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
   }  
```  
  
##  <a name="pointer"></a>  multiset::pointer  
 Bir öğe için bir işaretçi bir multiset sağlayan türü.  
  
```  
typedef typename allocator_type::pointer pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür **işaretçi** bir öğenin değerini değiştirmek için kullanılabilir.  
  
 Çoğu durumda, bir [yineleyici](#iterator) çok kümeli nesnesindeki öğelerin erişmek için kullanılmalıdır.  
  
##  <a name="rbegin"></a>  multiset::rbegin  
 İlk öğe ters multiset adresleme yineleyici döndürür.  
  
```  
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk öğe ters multiset adresleme veya ne adresleme ters çift yönlü yineleyici son öğe içinde unreversed multiset eklenmiştir.  
  
### <a name="remarks"></a>Açıklamalar  
 `rbegin` rbegin multiset ile yalnızca kullanılan ters multiset ile kullanılır.  
  
 Varsa dönüş değerini `rbegin` atandığı bir `const_reverse_iterator`, sonra da multiset nesnesi değiştirilemez. Varsa dönüş değerini `rbegin` atanmış bir `reverse_iterator`, birden çok küme nesnesi değiştirilebilir sonra.  
  
 `rbegin` multiset geriye doğru yinelemek için kullanılabilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_rbegin.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   multiset <int> ms1;  
   multiset <int>::iterator ms1_Iter;  
   multiset <int>::reverse_iterator ms1_rIter;  
  
   ms1.insert( 10 );  
   ms1.insert( 20 );  
   ms1.insert( 30 );  
  
   ms1_rIter = ms1.rbegin( );  
   cout << "The first element in the reversed multiset is "  
        << *ms1_rIter << "." << endl;  
  
   // begin can be used to start an interation   
   // throught a multiset in a forward order  
   cout << "The multiset is:";  
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )  
      cout << " " << *ms1_Iter;  
   cout << endl;  
  
   // rbegin can be used to start an interation   
   // throught a multiset in a reverse order  
   cout << "The reversed multiset is:";  
   for ( ms1_rIter = ms1.rbegin( ) ; ms1_rIter != ms1.rend( ); ms1_rIter++ )  
      cout << " " << *ms1_rIter;  
   cout << endl;  
  
   // A multiset element can be erased by dereferencing to its key   
   ms1_rIter = ms1.rbegin( );  
   ms1.erase ( *ms1_rIter );  
  
   ms1_rIter = ms1.rbegin( );  
   cout << "After the erasure, the first element "  
        << "in the reversed multiset is "<< *ms1_rIter << "."   
        << endl;  
}  
```  
  
```Output  
The first element in the reversed multiset is 30.  
The multiset is: 10 20 30  
The reversed multiset is: 30 20 10  
After the erasure, the first element in the reversed multiset is 20.  
```  
  
##  <a name="reference"></a>  multiset::reference  
 Bir çoklu küme içinde depolanan bir öğe için bir başvuru sağlar türü.  
  
```  
typedef typename allocator_type::reference reference;  
```  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_ref.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   multiset <int> ms1;  
  
   ms1.insert( 10 );  
   ms1.insert( 20 );  
  
   // Declare and initialize a reference &Ref1 to the 1st element  
   const int &Ref1 = *ms1.begin( );  
  
   cout << "The first element in the multiset is "  
        << Ref1 << "." << endl;  
}  
```  
  
```Output  
The first element in the multiset is 10.  
```  
  
##  <a name="rend"></a>  multiset::rend  
 Son öğe ters bir çoklu küme içinde başarılı konumu adresleri yineleyici döndürür.  
  
```  
const_reverse_iterator rend() const;

reverse_iterator rend();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ters multiset (ilk öğe unreversed multiset öncesinde konum), son öğe başarılı konumu adresleri ters çift yönlü yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 `rend` Ters multiset ile kullanılan gibi [son](#end) multiset ile kullanılır.  
  
 Varsa dönüş değerini `rend` atandığı bir `const_reverse_iterator`, sonra da multiset nesnesi değiştirilemez. Varsa dönüş değerini `rend` atanmış bir `reverse_iterator`, birden çok küme nesnesi değiştirilebilir sonra.  
  
 `rend` Ters yineleyici kendi multiset sonuna olup ulaştı için test etmek için kullanılabilir.  
  
 Tarafından döndürülen değer `rend` değil başvuru yapıldı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_rend.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main() {  
   using namespace std;     
   multiset <int> ms1;  
   multiset <int>::iterator ms1_Iter;  
   multiset <int>::reverse_iterator ms1_rIter;  
   multiset <int>::const_reverse_iterator ms1_crIter;  
  
   ms1.insert( 10 );  
   ms1.insert( 20 );  
   ms1.insert( 30 );  
  
   ms1_rIter = ms1.rend( ) ;  
   ms1_rIter--;  
   cout << "The last element in the reversed multiset is "  
        << *ms1_rIter << "." << endl;  
  
   // end can be used to terminate an interation   
   // throught a multiset in a forward order  
   cout << "The multiset is: ";  
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )  
      cout << *ms1_Iter << " ";  
   cout << "." << endl;  
  
   // rend can be used to terminate an interation   
   // throught a multiset in a reverse order  
   cout << "The reversed multiset is: ";  
   for ( ms1_rIter = ms1.rbegin( ) ; ms1_rIter != ms1.rend( ); ms1_rIter++ )  
      cout << *ms1_rIter << " ";  
   cout << "." << endl;  
  
   ms1_rIter = ms1.rend( );  
   ms1_rIter--;  
   ms1.erase ( *ms1_rIter );  
  
   ms1_rIter = ms1.rend( );  
   --ms1_rIter;  
   cout << "After the erasure, the last element in the "  
        << "reversed multiset is " << *ms1_rIter << "." << endl;  
}  
```  
  
##  <a name="reverse_iterator"></a>  multiset::reverse_iterator  
 Okuma veya bir öğenin içinde ters multiset değiştirmek için bir çift yönlü yineleyici sağlayan türü.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `reverse_iterator` kullanın ters multiset yinelemek için.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [rbegin](#rbegin) bildirme ve kullanma konusunda bir örnek için `reverse_iterator`.  
  
##  <a name="size"></a>  multiset::size  
 Multiset öğe sayısını döndürür.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Multiset geçerli uzunluğu.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_size.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   multiset <int> ms1;  
   multiset <int> :: size_type i;  
  
   ms1.insert( 1 );  
   i = ms1.size( );  
   cout << "The multiset length is " << i << "." << endl;  
  
   ms1.insert( 2 );  
   i = ms1.size( );  
   cout << "The multiset length is now " << i << "." << endl;  
}  
```  
  
```Output  
The multiset length is 1.  
The multiset length is now 2.  
```  
  
##  <a name="size_type"></a>  multiset::size_type  
 Bir multiset öğe sayısını gösterebilir bir işaretsiz tamsayı türü.  
  
```  
typedef typename allocator_type::size_type size_type;  
```  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [boyutu](#size) bildirme ve kullanma örneği `size_type`  
  
##  <a name="swap"></a>  multiset::Swap  
 İki multisets öğelerini değiş tokuş eder.  
  
```  
void swap(
    multiset<Key, Compare, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Bağımsız değişken multiset öğeleri ile hedef multiset takas için sağlama.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini hiçbir başvuruları, işaretçileri veya öğeleri arasında alınıp verilen iki multisets içinde öğeleri tanımladığınız yineleyiciler geçersiz kılar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_swap.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int> ms1, ms2, ms3;  
   multiset <int>::iterator ms1_Iter;  
  
   ms1.insert( 10 );  
   ms1.insert( 20 );  
   ms1.insert( 30 );  
   ms2.insert( 100 );  
   ms2.insert( 200 );  
   ms3.insert( 300 );  
  
   cout << "The original multiset ms1 is:";  
   for ( ms1_Iter = ms1.begin( ); ms1_Iter != ms1.end( ); ms1_Iter++ )  
      cout << " " << *ms1_Iter;  
   cout << "." << endl;  
  
   // This is the member function version of swap  
   ms1.swap( ms2 );  
  
   cout << "After swapping with ms2, list ms1 is:";  
   for ( ms1_Iter = ms1.begin( ); ms1_Iter != ms1.end( ); ms1_Iter++ )  
      cout << " " << *ms1_Iter;  
   cout << "." << endl;  
  
   // This is the specialized template version of swap  
   swap( ms1, ms3 );  
  
   cout << "After swapping with ms3, list ms1 is:";  
   for ( ms1_Iter = ms1.begin( ); ms1_Iter != ms1.end( ); ms1_Iter++ )  
      cout << " " << *ms1_Iter;  
   cout   << "." << endl;  
}  
```  
  
```Output  
The original multiset ms1 is: 10 20 30.  
After swapping with ms2, list ms1 is: 100 200.  
After swapping with ms3, list ms1 is: 300.  
```  
  
##  <a name="upper_bound"></a>  multiset::upper_bound  
 Yineleyici ilk öğe belirtilen anahtar daha büyük bir anahtara sahip bir multiset döndürür.  
  
```  
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Aranmakta multiset öğeden sıralama anahtarı ile Karşılaştırılacak bağımsız değişkeni anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir **yineleyici** veya `const_iterator` adresleri konumu, bir öğenin bir multiset bağımsız değişkeni anahtarından daha büyük ya da eşleşme için bulunursa, son öğe multiset başarılı konumu adresleri bir anahtarla anahtar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_upper_bound.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   multiset <int> ms1;  
   multiset <int> :: const_iterator ms1_AcIter, ms1_RcIter;  
  
   ms1.insert( 10 );  
   ms1.insert( 20 );  
   ms1.insert( 30 );  
  
   ms1_RcIter = ms1.upper_bound( 20 );  
   cout << "The first element of multiset ms1 with a key greater "  
           << "than 20 is: " << *ms1_RcIter << "." << endl;  
  
   ms1_RcIter = ms1.upper_bound( 30 );  
  
   // If no match is found for the key, end( ) is returned  
   if ( ms1_RcIter == ms1.end( ) )  
      cout << "The multiset ms1 doesn't have an element "  
              << "with a key greater than 30." << endl;  
   else  
      cout << "The element of multiset ms1 with a key > 40 is: "  
           << *ms1_RcIter << "." << endl;  
  
   // The element at a specific location in the multiset can be   
   // found using a dereferenced iterator addressing the location  
   ms1_AcIter = ms1.begin( );  
   ms1_RcIter = ms1.upper_bound( *ms1_AcIter );  
   cout << "The first element of ms1 with a key greater than"  
        << endl << "that of the initial element of ms1 is: "  
        << *ms1_RcIter << "." << endl;  
}  
```  
  
```Output  
The first element of multiset ms1 with a key greater than 20 is: 30.  
The multiset ms1 doesn't have an element with a key greater than 30.  
The first element of ms1 with a key greater than  
that of the initial element of ms1 is: 20.  
```  
  
##  <a name="value_comp"></a>  multiset::value_comp  
 Sipariş öğesi değerleri için bir çoklu küme içinde kullanılan karşılaştırma nesnesinin bir kopyasını alır.  
  
```  
value_compare value_comp() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şablon parametresi olan öğeleri, sipariş için bir çoklu küme kullanan işlevi nesnesi döndüren `Compare`.  
  
 Daha fazla bilgi için `Compare`, Açıklamalar bölümüne bakın [multiset sınıfı](../standard-library/multiset-class.md) konu.  
  
### <a name="remarks"></a>Açıklamalar  
 Saklanan nesne üye işlevini tanımlar:  
  
 **bool işleci**( **const anahtar &**`_xVal`, **const anahtar &**`_yVal`);  
  
 hangi döndürür ise true `_xVal` önündeki ve eşit değil `_yVal` sıralama düzeninde.  
  
 Unutmayın her ikisi de [key_compare](#key_compare) ve [value_compare](#value_compare) şablon parametresi için eş anlamlı sözcükleri olan `Compare`. Her iki tür sınıfları harita ve burada ayrı multimap ile uyumluluk için aynı oldukları, multiset ve sınıfları kümesi için sağlanır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_value_comp.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   multiset <int, less<int> > ms1;  
   multiset <int, less<int> >::value_compare vc1 = ms1.value_comp( );  
   bool result1 = vc1( 2, 3 );  
   if( result1 == true )     
   {  
      cout << "vc1( 2,3 ) returns value of true, "  
           << "where vc1 is the function object of ms1."  
           << endl;  
   }  
   else     
   {  
      cout << "vc1( 2,3 ) returns value of false, "  
           << "where vc1 is the function object of ms1."  
           << endl;  
   }  
  
   set <int, greater<int> > ms2;  
   set<int, greater<int> >::value_compare vc2 = ms2.value_comp( );  
   bool result2 = vc2( 2, 3 );  
   if( result2 == true )     
   {  
      cout << "vc2( 2,3 ) returns value of true, "  
           << "where vc2 is the function object of ms2."  
           << endl;  
   }  
   else     
   {  
      cout << "vc2( 2,3 ) returns value of false, "  
           << "where vc2 is the function object of ms2."  
           << endl;  
   }  
}  
```  
  
```Output  
vc1( 2,3 ) returns value of true, where vc1 is the function object of ms1.  
vc2( 2,3 ) returns value of false, where vc2 is the function object of ms2.  
```  
  
##  <a name="value_compare"></a>  multiset::value_compare  
 İşlev nesnesi sağlayan türü göreli sıralarına multiset belirlemek için iki sıralama anahtarları karşılaştırabilirsiniz.  
  
```  
typedef key_compare value_compare;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `value_compare` Şablon parametresi için bir eş anlamlı olduğundan `Compare`.  
  
 Unutmayın her ikisi de [key_compare](#key_compare) ve **value_compare** şablon parametresi için eş anlamlı sözcükleri olan `Compare`. Her iki tür sınıfları harita ve burada ayrı multimap ile uyumluluk için aynı oldukları, multiset ve sınıfları kümesi için sağlanır.  
  
 Daha fazla bilgi için `Compare`, Açıklamalar bölümüne bakın [multiset sınıfı](../standard-library/multiset-class.md) konu.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [value_comp](#value_comp) bildirme ve kullanma konusunda bir örnek için `value_compare`.  
  
##  <a name="value_type"></a>  multiset::value_type  
 Kapasitesi değer olarak, çoklu küme olarak bir öğe olarak saklanan bir nesneyi tanımlayan bir türü.  
  
```  
typedef Key value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `value_type` Şablon parametresi için bir eş anlamlı olduğundan `Key`.  
  
 Unutmayın her ikisi de [key_type](#key_type) ve `value_type` şablon parametresi için eş anlamlı sözcükleri olan **anahtar**. Her iki tür sınıfları harita ve burada ayrı multimap ile uyumluluk için aynı oldukları, multiset ve sınıfları kümesi için sağlanır.  
  
 Daha fazla bilgi için `Key`, konunun Açıklamalar bölümüne bakın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_value_type.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int> ms1;  
   multiset <int>::iterator ms1_Iter;  
  
   multiset <int> :: value_type svt_Int;   // Declare value_type  
   svt_Int = 10;             // Initialize value_type  
  
   multiset <int> :: key_type skt_Int;   // Declare key_type  
   skt_Int = 20;             // Initialize key_type  
  
   ms1.insert( svt_Int );         // Insert value into s1  
   ms1.insert( skt_Int );         // Insert key into s1  
  
   // A multiset accepts key_types or value_types as elements  
   cout << "The multiset has elements:";  
   for ( ms1_Iter = ms1.begin( ) ; ms1_Iter != ms1.end( ); ms1_Iter++ )  
      cout << " " << *ms1_Iter;  
   cout << "." << endl;  
}  
```  
  
```Output  
The multiset has elements: 10 20.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Ayarlama > üyeleri](http://msdn.microsoft.com/en-us/0c2d57c0-173f-4204-b579-c5f06aad8b95)   
 [Kapsayıcıları](../cpp/containers-modern-cpp.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

