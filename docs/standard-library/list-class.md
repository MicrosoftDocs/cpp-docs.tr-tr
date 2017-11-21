---
title: "list sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- list/std::list
- list/std::list::allocator_type
- list/std::list::const_iterator
- list/std::list::const_pointer
- list/std::list::const_reference
- list/std::list::const_reverse_iterator
- list/std::list::difference_type
- list/std::list::iterator
- list/std::list::pointer
- list/std::list::reference
- list/std::list::reverse_iterator
- list/std::list::size_type
- list/std::list::value_type
- list/std::list::assign
- list/std::list::back
- list/std::list::begin
- list/std::list::cbegin
- list/std::list::cend
- list/std::list::clear
- list/std::list::crbegin
- list/std::list::crend
- list/std::list::emplace
- list/std::list::emplace_back
- list/std::list::emplace_front
- list/std::list::empty
- list/std::list::end
- list/std::list::erase
- list/std::list::front
- list/std::list::get_allocator
- list/std::list::insert
- list/std::list::max_size
- list/std::list::merge
- list/std::list::pop_back
- list/std::list::pop_front
- list/std::list::push_back
- list/std::list::push_front
- list/std::list::rbegin
- list/std::list::remove
- list/std::list::remove_if
- list/std::list::rend
- list/std::list::resize
- list/std::list::reverse
- list/std::list::size
- list/std::list::sort
- list/std::list::splice
- list/std::list::swap
- list/std::list::unique
dev_langs: C++
helpviewer_keywords:
- std::list [C++]
- std::list [C++], allocator_type
- std::list [C++], const_iterator
- std::list [C++], const_pointer
- std::list [C++], const_reference
- std::list [C++], const_reverse_iterator
- std::list [C++], difference_type
- std::list [C++], iterator
- std::list [C++], pointer
- std::list [C++], reference
- std::list [C++], reverse_iterator
- std::list [C++], size_type
- std::list [C++], value_type
- std::list [C++], assign
- std::list [C++], back
- std::list [C++], begin
- std::list [C++], cbegin
- std::list [C++], cend
- std::list [C++], clear
- std::list [C++], crbegin
- std::list [C++], crend
- std::list [C++], emplace
- std::list [C++], emplace_back
- std::list [C++], emplace_front
- std::list [C++], empty
- std::list [C++], end
- std::list [C++], erase
- std::list [C++], front
- std::list [C++], get_allocator
- std::list [C++], insert
- std::list [C++], max_size
- std::list [C++], merge
- std::list [C++], pop_back
- std::list [C++], pop_front
- std::list [C++], push_back
- std::list [C++], push_front
- std::list [C++], rbegin
- std::list [C++], remove
- std::list [C++], remove_if
- std::list [C++], rend
- std::list [C++], resize
- std::list [C++], reverse
- std::list [C++], size
- std::list [C++], sort
- std::list [C++], splice
- std::list [C++], swap
- std::list [C++], unique
ms.assetid: d3707f4a-10fd-444f-b856-f9ca2077c1cd
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f22a8ac8c1d20bb6f972b8674c344db7c8a5ce60
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="list-class"></a>list Sınıfı
C++ Standart Kitaplığı liste öğelerini doğrusal bir düzende korumak ve verimli eklemeler ve silmeler dizisi içindeki herhangi bir konumdaki izin veren dizisi kapsayıcıların bir şablon sınıfı sınıftır. Sıralı her bazı türünün bir üyesi içeren öğe, çift yönlü bağlantılı liste olarak depolanan *türü*.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <class Type, class Allocator= allocator<Type>>  
class list  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Türü*  
 Listede depolanması için öğe veri türü.  
  
 `Allocator`  
 Listenin ayırma ve bellek ayırmayı kaldırma hakkında ayrıntılar yalıtan saklı ayırıcısı nesneyi temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **ayırıcısı**\<*türü*>.  
  
## <a name="remarks"></a>Açıklamalar  
 Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Vektörler herhangi bir öğeye rasgele erişim olduğunda premium ve eklemeleri ya da silme işlemleri öğelerinin, yalnızca bir sıralı yönetmek için tercih edilen kapsayıcı olmalıdır bir dizi sonunda gerekli. Sınıf deque kapsayıcı performansını eklemeler ve silmeler başında ve dizinin sonuna rasgele erişim gereklidir ve premium üstündedir.  
  
 Liste üye işlevleri [birleştirme](#merge), [ters](#reverse), [benzersiz](#unique), [kaldırmak](#remove), ve [remove_if](#remove_if) bırakıldı list nesneleri ve teklif genel dekiler yüksek performanslı alternatifi üzerinde işlem için en iyi duruma getirilmiş.  
  
 Liste yeniden ayırma üye işlevi ekleme veya listenin öğelerini silme oluşur. Böyle durumlarda, yalnızca yineleyiciler veya üzerine başvuru geçersiz hale denetimli dizisi bölümlerini silinebilir.  
  
 C++ Standart Kitaplığı standart üstbilgisini \<listesi > tanımlamak için [kapsayıcı](../standard-library/stl-containers.md) şablon sınıf listesi ve çeşitli destekleyici şablonlar.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[Liste](#list)|Belirli bir boyutta veya belirli bir değere öğelerini veya belirli bir liste oluşturur `allocator` veya bir kopyasını başka bir liste olarak.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|Temsil eden bir tür `allocator` bir liste nesnesi için sınıf.|  
|[const_iterator](#const_iterator)|Çift yönlü yineleyici bu can sağlayan bir türü okuma bir `const` bir liste öğesi.|  
|[const_pointer](#const_pointer)|Bir işaretçi sağlayan bir türü bir `const` bir liste öğesi.|  
|[const_reference](#const_reference)|Bir başvuru sağlayan bir türü bir `const` okuma ve gerçekleştirmek için bir liste depolanan öğesi `const` işlemleri.|  
|[const_reverse_iterator](#const_reverse_iterator)|Herhangi bir çift yönlü yineleyici bu can sağlayan bir türü okuma `const` bir liste öğesi.|  
|[difference_type](#difference_type)|Aynı liste içinde öğelerin başvurmak iki yineleyiciler arasındaki farkı sağlayan türü.|  
|[Yineleyici](#iterator)|Okuma veya herhangi bir öğe listesini değiştirmek için bir çift yönlü yineleyici sağlayan türü.|  
|[İşaretçi](#pointer)|Bir listedeki bir öğe için bir işaretçi sağlayan türü.|  
|[başvuru](#reference)|Bir başvuru sağlayan bir türü bir `const` okuma ve gerçekleştirmek için bir liste depolanan öğesi `const` işlemleri.|  
|[reverse_iterator](#reverse_iterator)|Okuma veya ters listesindeki bir öğeyi değiştirmek için bir çift yönlü yineleyici sağlayan türü.|  
|[size_type](#size_type)|Listedeki öğeleri sayar türü.|  
|[value_type](#value_type)|Bir listede depolanan veri türünü temsil eden tür.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[Ata](#assign)|Öğeleri bir listeden siler ve yeni bir öğe kümesi hedef listeye kopyalar.|  
|[Geri](#back)|Son öğe listesinin bir başvuru döndürür.|  
|[başlayın](#begin)|Yineleyici listesindeki ilk öğeyi adresleme döndürür.|  
|[cbegin](#cbegin)|Listesindeki ilk öğeyi adresleme const yineleyici döndürür.|  
|[cend](#cend)|Listesindeki son öğeyi başarılı konumu adresleri const bir yineleyici döndürür.|  
|[Temizle](#clear)|Tüm öğeleri listesini siler.|  
|[crbegin](#crbegin)|Ters listesindeki ilk öğeyi adresleme const yineleyici döndürür.|  
|[crend](#crend)|Ters listesindeki son öğeyi başarılı konumu adresleri const bir yineleyici döndürür.|  
|[emplace](#emplace)|Belirtilen konumda Listeye yerinde oluşturulan bir öğe ekler.|  
|[emplace_back](#emplace_back)|Bir liste sonuna yerinde oluşturulan bir öğe ekler.|  
|[emplace_front](#emplace_front)|Bir liste başlangıcına yerinde oluşturulan bir öğe ekler.|  
|[boş](#empty)|Liste boşsa, testleri.|  
|[Bitiş](#end)|Listesindeki son öğeyi başarılı konumu adresleri yineleyici döndürür.|  
|[silme](#erase)|Bir öğenin veya öğe aralığını belirtilen konumları listesinden kaldırır.|  
|[Ön](#front)|Bir listedeki ilk öğeye bir başvuru döndürür.|  
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` listesini oluşturmak için kullanılan nesne.|  
|[Ekle](#insert)|Bir öğenin veya öğe sayısı veya bir dizi öğeleri listesini belirtilen konumda ekler.|  
|[max_size](#max_size)|Uzunluk listesini döndürür.|  
|[Birleştirme](#merge)|Öğeleri bağımsız değişkeni listeden kaldırır, bunları hedef listesine ekler ve öğeleri artan düzende veya başka bir belirtilen sırayla yeni, birleştirilmiş kümesini sıralar.|  
|[pop_back](#pop_back)|Öğe listesinin sonunda siler.|  
|[pop_front](#pop_front)|Öğe listesinin başında siler.|  
|[push_back](#push_back)|Bir öğe listesinin sonuna ekler.|  
|[push_front](#push_front)|Bir öğe listesini başlangıcına ekler.|  
|[rbegin](#rbegin)|Yineleyici ters listesindeki ilk öğeyi adresleme döndürür.|  
|[Kaldır](#remove)|Belirtilen değerle eşleşen listedeki öğeleri siler.|  
|[remove_if](#remove_if)|Öğeleri belirtilen bir koşulu karşılanıp listeden siler.|  
|[rend](#rend)|Ters listesindeki son öğeyi başarılı konumu adresleri yineleyici döndürür.|  
|[yeniden boyutlandırma](#resize)|Bir liste için yeni bir boyutunu belirtir.|  
|[geriye doğru](#reverse)|Öğeleri listede ortaya sırasını tersine çevirir.|  
|[boyutu](#size)|Bir listedeki öğe sayısını döndürür.|  
|[Sıralama](#sort)|Öğeleri listesini artan düzende veya başka bir sipariş ilişkisi göre düzenler.|  
|[splice](#splice)|Öğeleri bağımsız değişkeni listeden kaldırır ve hedef listesine ekler.|  
|[değiştirme](#swap)|İki liste öğelerini değiş tokuş eder.|  
|[benzersiz](#unique)|Bitişik yinelenen öğeler veya listeden bazı diğer ikili koşulu karşılayan bitişik öğeleri kaldırır.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[List::operator =](#op_eq)|Liste öğelerini, başka bir listesinin bir kopyasını yerini alır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: \<listesi >  
  
##  <a name="allocator_type"></a>List::allocator_type  
 Allocator sınıfı bir liste nesnesi için temsil eden tür.  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `allocator_type`Şablon parametresi için bir eş anlamlı olduğundan **ayırıcısı.**  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [get_allocator](#get_allocator).  
  
##  <a name="assign"></a>List::Assign  
 Öğeleri bir listeden siler ve bir hedef listesine yeni bir öğeleri kümesini kopyalar.  
  
```  
void assign(
    size_type Count,  
    const Type& Val);

void assign  
    initializer_list<Type> IList);

template <class InputIterator>  
void assign(
    InputIterator First,  
    InputIterator Last);
```  
  
### <a name="parameters"></a>Parametreler  
 `First`  
 Bağımsız değişken listeden kopyalanacak öğe aralığını ilk öğe konumu.  
  
 `Last`  
 Yalnızca bağımsız değişken listeden kopyalanmasını öğelerinin aralık ötesinde ilk öğe konumu.  
  
 `Count`  
 Listeye eklenen bir öğenin kopya sayısı.  
  
 `Val`  
 Listeye eklenen öğesinin değeri.  
  
 `IList`  
 Eklenecek öğeleri içeren initializer_list.  
  
### <a name="remarks"></a>Açıklamalar  
 Hedef listedeki var olan öğeleri silme sonra Ata öğeleri belirtilen bir dizi özgün listesinden veya başka bir liste hedef listesine ekler ya da yeni bir öğesi belirtilen kopyalarını hedef listesine ekler  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_assign.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    list<int> c1, c2;  
    list<int>::const_iterator cIter;  
  
    c1.push_back(10);  
    c1.push_back(20);  
    c1.push_back(30);  
    c2.push_back(40);  
    c2.push_back(50);  
    c2.push_back(60);  
  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    c1.assign(++c2.begin(), c2.end());  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    c1.assign(7, 4);  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    c1.assign({ 10, 20, 30, 40 });  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
}  
```  
  
```Output  
c1 = 10 20 30c1 = 50 60c1 = 4 4 4 4 4 4 4c1 = 10 20 30 40  
```  
  
##  <a name="back"></a>List::Back  
 Son öğe listesinin bir başvuru döndürür.  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listenin son öğesi. Liste boşsa, dönüş değeri tanımlanmamıştır.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa dönüş değerini **geri** atanmış bir `const_reference`, liste nesnesi değiştirilemez. Varsa dönüş değerini **geri** atanmış bir **başvuru**, liste nesnesi değiştirilebilir.  
  
 Kullanarak derlendiğinde [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) boş bir liste öğesi erişmeyi denerseniz, 1 veya 2 olarak tanımlanan, bir çalışma zamanı hatası meydana gelir.  Bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md) daha fazla bilgi için.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_back.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 11 );  
  
   int& i = c1.back( );  
   const int& ii = c1.front( );  
  
   cout << "The last integer of c1 is " << i << endl;  
   i--;  
   cout << "The next-to-last integer of c1 is " << ii << endl;  
}  
```  
  
```Output  
The last integer of c1 is 11  
The next-to-last integer of c1 is 10  
```  
  
##  <a name="begin"></a>List::Begin  
 Yineleyici listesindeki ilk öğeyi adresleme döndürür.  
  
```  
const_iterator begin() const;

iterator begin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk öğe listesinde ya da boş bir liste başarılı konuma adresleme çift yönlü yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa dönüş değerini **başlamak** atanmış bir `const_iterator`, liste nesnesinde öğeler değiştirilemez. Varsa dönüş değerini **başlamak** atanmış bir **yineleyici**, liste nesnesindeki öğelerin değiştirilebilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_begin.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
   list <int>::const_iterator c1_cIter;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
  
   c1_Iter = c1.begin( );  
   cout << "The first element of c1 is " << *c1_Iter << endl;  
  
 *c1_Iter = 20;  
   c1_Iter = c1.begin( );  
   cout << "The first element of c1 is now " << *c1_Iter << endl;  
  
   // The following line would be an error because iterator is const  
   // *c1_cIter = 200;  
}  
```  
  
```Output  
The first element of c1 is 1  
The first element of c1 is now 20  
```  
  
##  <a name="cbegin"></a>List::cbegin  
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
  
##  <a name="cend"></a>List::cend  
 Döndürür bir `const` konumun yalnızca bir aralıkta son öğenin ötesinde adresleri yineleyici.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `const` yalnızca aralığın sonunu aşan işaret çift yönlü erişim yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 `cend`Yineleyici kendi aralığının sonunu geçti olup olmadığını test etmek için kullanılır.  
  
 Bu üye işlevi yerine kullanabileceğiniz `end()` üye işlevi dönüş değeri garanti `const_iterator`. Genellikle, ile birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` bir değiştirilebilir için (olmayan `const`) destekleyen herhangi bir türde kapsayıcı `end()` ve `cend()`.  
  
```cpp  
auto i1 = Container.end();
// i1 is Container<T>::iterator   
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator  
```  
  
 Tarafından döndürülen değer `cend` değil başvuru yapıldı.  
  
##  <a name="clear"></a>List::Clear  
 Tüm öğeleri listesini siler.  
  
```  
void clear();
```  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_clear.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main() {  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   cout << "The size of the list is initially " << c1.size( ) << endl;  
   c1.clear( );  
   cout << "The size of list after clearing is " << c1.size( ) << endl;  
}  
```  
  
```Output  
The size of the list is initially 3  
The size of list after clearing is 0  
```  
  
##  <a name="const_iterator"></a>List::const_iterator  
 Çift yönlü yineleyici bu can sağlayan bir türü okuma bir **const** bir liste öğesi.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [geri](#back).  
  
##  <a name="const_pointer"></a>List::const_pointer  
 Bir işaretçi sağlayan bir `const` bir liste öğesi.  
  
``` 
typedef typename Allocator::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.  
  
 Çoğu durumda, bir [yineleyici](#iterator) bir liste nesnesi öğelerinde erişmek için kullanılmalıdır.  
  
##  <a name="const_reference"></a>List::const_reference  
 Bir başvuru sağlayan bir türü bir **const** okuma ve gerçekleştirmek için bir liste depolanan öğesi **const** işlemleri.  
  
```  
typedef typename Allocator::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_reference` bir öğenin değerini değiştirmek için kullanılamaz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_const_ref.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const list <int> c2 = c1;  
   const int &i = c2.front( );  
   const int &j = c2.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
  
   // The following line would cause an error because c2 is const  
   // c2.push_back( 30 );  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="const_reverse_iterator"></a>List::const_reverse_iterator  
 Herhangi bir çift yönlü yineleyici bu can sağlayan bir türü okuma **const** bir liste öğesi.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_reverse_iterator` bir öğenin değerini değiştiremez ve geriye doğru listesinde yinelemek için kullanılır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [rbegin](#rbegin).  
  
##  <a name="crbegin"></a>List::crbegin  
 Ters listesindeki ilk öğeyi adresleme const yineleyici döndürür.  
  
```  
const_reverse_iterator rbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir const ters ters listesindeki ilk öğeyi adresleme çift yönlü yineleyici (veya ne son öğesi unreversed olsaydı adresleme `list`).  
  
### <a name="remarks"></a>Açıklamalar  
 `crbegin`Ters listesiyle kullanılan gibi [list::begin](#begin) ile kullanılan bir `list`.  
  
 Dönüş değeri ile `crbegin`, liste nesnesi değiştirilemez. [List::rbegin](#rbegin) listesini geriye doğru yinelemek için kullanılabilecek.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_crbegin.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::const_reverse_iterator c1_crIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1_crIter = c1.crbegin( );  
   cout << "The last element in the list is " << *c1_crIter << "." << endl;  
}  
```  
  
```Output  
The last element in the list is 30.  
```  
  
##  <a name="crend"></a>List::crend  
 Ters listesindeki son öğeyi başarılı konumu adresleri const bir yineleyici döndürür.  
  
```  
const_reverse_iterator rend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir const ters son öğesi bir ters başarılı konumu adresleri çift yönlü yineleyici [listesi](../standard-library/list-class.md) (ilk öğe unreversed öncesinde konumu `list`).  
  
### <a name="remarks"></a>Açıklamalar  
 `crend`Ters listesiyle kullanılan gibi [list::end](#end) ile kullanılan bir `list`.  
  
 Dönüş değeri ile `crend`, `list` nesnesi değiştirilemez.  
  
 `crend`Ters yineleyici sonuna olup ulaştı için test etmek için kullanılan kendi `list`.  
  
 Tarafından döndürülen değer `crend` değil başvuru yapıldı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_crend.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::const_reverse_iterator c1_crIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_crIter = c1.crend( );  
   c1_crIter --;  // Decrementing a reverse iterator moves it forward in   
                 // the list (to point to the first element here)  
   cout << "The first element in the list is: " << *c1_crIter << endl;  
}  
```  
  
```Output  
The first element in the list is: 10  
```  
  
##  <a name="difference_type"></a>List::difference_type  
 Yineleyiciler tarafından işaret öğeler arasındaki bir aralıkta bir liste öğelerinin sayısını temsil etmek için kullanılan bir imzalı tamsayı türü.  
  
```  
typedef typename Allocator::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `difference_type` Türü çıkarılmasıyla veya kapsayıcı yineleyiciler artırma döndürülür. `difference_type` Genellikle aralığında öğe sayısını temsil etmek için kullanılan [ `first`, `last`) yineleyiciler arasında `first` ve `last`, gösterdiği öğesi içerir `first` ve öğeleri kadar aralığı , ancak değil de dahil olmak üzere, gösterdiği öğesi `last`.  
  
 Ancak unutmayın `difference_type` çıkarma yineleyiciler arasında yalnızca kümesidir gibi ters çevrilebilir kapsayıcıları tarafından desteklenen çift yönlü yineleyiciler sınıfı içeren bir giriş yineleyici gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir rasgele erişim kapsayıcı tarafından sağlanan gibi rasgele erişim yineleyiciler tarafından desteklenen [vector sınıfı](../standard-library/vector-class.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <list>  
#include <algorithm>  
  
int main( )   
{  
   using namespace std;  
  
   list <int> c1;  
   list <int>::iterator   c1_Iter, c2_Iter;  
  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 10 );  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
  
   c1_Iter = c1.begin( );  
   c2_Iter = c1.end( );  
  
    list <int>::difference_type df_typ1, df_typ2, df_typ3;  
  
   df_typ1 = count( c1_Iter, c2_Iter, 10 );  
   df_typ2 = count( c1_Iter, c2_Iter, 20 );  
   df_typ3 = count( c1_Iter, c2_Iter, 30 );  
   cout << "The number '10' is in c1 collection " << df_typ1 << " times.\n";  
   cout << "The number '20' is in c1 collection " << df_typ2 << " times.\n";  
   cout << "The number '30' is in c1 collection " << df_typ3 << " times.\n";  
}  
```  
  
```Output  
The number '10' is in c1 collection 1 times.  
The number '20' is in c1 collection 2 times.  
The number '30' is in c1 collection 3 times.  
```  
  
##  <a name="emplace"></a>List::emplace  
 Belirtilen konumda Listeye yerinde oluşturulan bir öğe ekler.  
  
```  
void emplace(iterator Where, Type&& val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Where`|Hedef konumda [listesi](../standard-library/list-class.md) burada ilk öğesine eklenir.|  
|`val`|Sonuna eklenen öğesi `list`.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bir özel durum, `list` sol değiştirilmemiş ve özel durum işlenemezse.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_emplace.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   list <string> c2;  
   string str("a");  
  
   c2.emplace(c2.begin(), move( str ) );  
   cout << "Moved first element: " << c2.back( ) << endl;  
}  
```  
  
```Output  
Moved first element: a  
```  
  
##  <a name="emplace_back"></a>List::emplace_back  
 Bir liste sonuna yerinde oluşturulan bir öğe ekler.  
  
```  
void emplace_back(Type&& val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`val`|Sonuna eklenen öğesi [listesi](../standard-library/list-class.md).|  
  
### <a name="remarks"></a>Açıklamalar  
 Bir özel durum, `list` sol değiştirilmemiş ve özel durum işlenemezse.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_emplace_back.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   list <string> c2;  
   string str("a");  
  
   c2.emplace_back( move( str ) );  
   cout << "Moved first element: " << c2.back( ) << endl;  
}  
```  
  
```Output  
Moved first element: a  
```  
  
##  <a name="emplace_front"></a>List::emplace_front  
 Bir liste başlangıcına yerinde oluşturulan bir öğe ekler.  
  
```  
void emplace_front(Type&& val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`val`|Başlangıcına eklenen öğesi [listesi](../standard-library/list-class.md).|  
  
### <a name="remarks"></a>Açıklamalar  
 Bir özel durum, `list` sol değiştirilmemiş ve özel durum işlenemezse.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_emplace_front.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   list <string> c2;  
   string str("a");  
  
   c2.emplace_front( move( str ) );  
   cout << "Moved first element: " << c2.front( ) << endl;  
}  
```  
  
```Output  
Moved first element: a  
```  
  
##  <a name="empty"></a>List::empty  
 Liste boşsa, testleri.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** liste boşsa; **false** listesi boş değilse.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_empty.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   if ( c1.empty( ) )  
      cout << "The list is empty." << endl;  
   else  
      cout << "The list is not empty." << endl;  
}  
```  
  
```Output  
The list is not empty.  
```  
  
##  <a name="end"></a>List::End  
 Listesindeki son öğeyi başarılı konumu adresleri yineleyici döndürür.  
  
```  
const_iterator end() const;
iterator end();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listesindeki son öğeyi başarılı konumu adresleri çift yönlü yineleyici. Liste boş ise, `list::end == list::begin`.  
  
### <a name="remarks"></a>Açıklamalar  
 **Son** Yineleyici, listenin sonuna ulaştı olup olmadığını test etmek için kullanılır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_end.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_Iter = c1.end( );  
   c1_Iter--;  
   cout << "The last integer of c1 is " << *c1_Iter << endl;  
  
   c1_Iter--;  
 *c1_Iter = 400;  
   cout << "The new next-to-last integer of c1 is "  
        << *c1_Iter << endl;  
  
   // If a const iterator had been declared instead with the line:  
   // list <int>::const_iterator c1_Iter;  
   // an error would have resulted when inserting the 400  
  
   cout << "The list is now:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
}  
```  
  
```Output  
The last integer of c1 is 30  
The new next-to-last integer of c1 is 400  
The list is now: 10 400 30  
```  
  
##  <a name="erase"></a>List::ERASE  
 Bir öğenin veya öğe aralığını belirtilen konumları listesinden kaldırır.  
  
```  
iterator erase(iterator Where);
iterator erase(iterator first, iterator last);
```  
  
### <a name="parameters"></a>Parametreler  
 `Where`  
 Listeden kaldırılacak öğe konumu.  
  
 `first`  
 İlk öğenin konumunu listeden kaldırıldı.  
  
 `last`  
 Yalnızca son öğenin ötesinde konumunu listeden kaldırıldı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaldırılan herhangi bir öğenin dışında kalan ilk öğe atayan bir çift yönlü yineleyici veya böyle bir öğe varsa, listenin sonuna bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir yeniden ayırma yineleyiciler ve başvuruları için yalnızca silinen öğeleri geçersiz hale şekilde gerçekleşir.  
  
 **ERASE** hiçbir zaman bir özel durum oluşturur.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_erase.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 40 );  
   c1.push_back( 50 );  
   cout << "The initial list is:";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   c1.erase( c1.begin( ) );  
   cout << "After erasing the first element, the list becomes:";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
   Iter = c1.begin( );  
   Iter++;  
   c1.erase( Iter, c1.end( ) );  
   cout << "After erasing all elements but the first, the list becomes: ";  
   for (Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
}  
```  
  
```Output  
The initial list is: 10 20 30 40 50  
After erasing the first element, the list becomes: 20 30 40 50  
After erasing all elements but the first, the list becomes:  20  
```  
  
##  <a name="front"></a>List::Front  
 Bir listedeki ilk öğeye bir başvuru döndürür.  
  
```  
reference front();
const_reference front() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste boşsa, dönüş tanımlanmamıştır.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa dönüş değerini `front` atanmış bir `const_reference`, liste nesnesi değiştirilemez. Varsa dönüş değerini `front` atanmış bir **başvuru**, liste nesnesi değiştirilebilir.  
  
 Kullanarak derlendiğinde [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) boş bir liste öğesi erişmeyi denerseniz, 1 veya 2 olarak tanımlanan, bir çalışma zamanı hatası meydana gelir.  Bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md) daha fazla bilgi için.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_front.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main() {  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
  
   int& i = c1.front();  
   const int& ii = c1.front();  
  
   cout << "The first integer of c1 is " << i << endl;  
   i++;  
   cout << "The first integer of c1 is " << ii << endl;  
}  
```  
  
```Output  
The first integer of c1 is 10  
The first integer of c1 is 11  
```  
  
##  <a name="get_allocator"></a>List::get_allocator  
 Bir liste oluşturmak için kullanılan ayırıcısı nesnesinin bir kopyasını döndürür.  
  
```  
Allocator get_allocator() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste tarafından kullanılan ayırıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Allocators listesi sınıfı için sınıf depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan allocators çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak ileri düzeyde C++ bir konudur.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_get_allocator.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   // The following lines declare objects   
   // that use the default allocator.  
   list <int> c1;  
   list <int, allocator<int> > c2 = list <int, allocator<int> >( allocator<int>( ) );  
  
   // c3 will use the same allocator class as c1  
   list <int> c3( c1.get_allocator( ) );  
  
   list<int>::allocator_type xlst = c1.get_allocator( );  
   // You can now call functions on the allocator class used by c1  
}  
```  
  
##  <a name="insert"></a>List::insert  
 Bir öğenin veya öğe sayısı veya bir dizi öğeleri listesini belirtilen konumda ekler.  
  
```  
iterator insert(iterator Where, const Type& Val);
iterator insert(iterator Where, Type&& Val);

void insert(iterator Where, size_type Count, const Type& Val);
iterator insert(iterator Where, initializer_list<Type> IList);

template <class InputIterator>  
void insert(iterator Where, InputIterator First, InputIterator Last);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Where`|Hedef listesindeki ilk öğe burada eklenen konumu.|  
|`Val`|Listeye eklenen öğesinin değeri.|  
|`Count`|Listeye eklenen öğelerin sayısı.|  
|`First`|Kopyalanacak bağımsız değişken listesindeki öğeleri aralığındaki ilk öğe konumu.|  
|`Last`|Kopyalanacak bağımsız değişken listesi öğelerinin aralık ötesinde ilk öğe konumu.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk iki Ekle işlevler burada yeni öğe listeye eklenen konumuna işaret eden bir yineleyici döndürür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_class_insert.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main()  
{  
    using namespace std;  
    list <int> c1, c2;  
    list <int>::iterator Iter;  
  
    c1.push_back(10);  
    c1.push_back(20);  
    c1.push_back(30);  
    c2.push_back(40);  
    c2.push_back(50);  
    c2.push_back(60);  
  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    Iter = c1.begin();  
    Iter++;  
    c1.insert(Iter, 100);  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    Iter = c1.begin();  
    Iter++;  
    Iter++;  
    c1.insert(Iter, 2, 200);  
  
    cout << "c1 =";  
    for(auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    c1.insert(++c1.begin(), c2.begin(), --c2.end());  
  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    // initialize a list of strings by moving  
    list < string > c3;  
    string str("a");  
  
    c3.insert(c3.begin(), move(str));  
    cout << "Moved first element: " << c3.front() << endl;  
  
    // Assign with an initializer_list  
    list <int> c4{ {1, 2, 3, 4} };  
    c4.insert(c4.begin(), { 5, 6, 7, 8 });  
  
    cout << "c4 =";  
    for (auto c : c4)  
        cout << " " << c;  
    cout << endl;  
}  
```  
  
##  <a name="iterator"></a>List::iterator  
 Okuma veya herhangi bir öğe listesini değiştirmek için bir çift yönlü yineleyici sağlayan türü.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür **yineleyici** bir öğenin değerini değiştirmek için kullanılabilir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [başlamak](#begin).  
  
##  <a name="list"></a>List::List  
 Belirli bir boyuta veya belirli bir değerin veya belirli bir ayırıcı veya tüm kopyasını veya başka bir liste parçası olarak öğelerle bir liste oluşturur.  
  
```  
list();
explicit list(const Allocator& Al);
explicit list(size_type Count);
list(size_type Count, const Type& Val);
list(size_type Count, const Type& Val, const Allocator& Al);

list(const list& Right);
list(list&& Right);
list(initializer_list<Type> IList, const Allocator& Al);

template <class InputIterator>  
list(InputIterator First, InputIterator Last);

template <class InputIterator>  
list(InputIterator First, InputIterator Last, const Allocator& Al);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Al`|Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.|  
|`Count`|Oluşturulan listedeki öğe sayısı.|  
|`Val`|Listedeki öğelerin değeri.|  
|`Right`|Oluşturulan listenin bir kopyasını olmasını olduğu listesi.|  
|`First`|Kopyalanacak öğe aralığını ilk öğe konumu.|  
|`Last`|Kopyalanacak öğeleri aralık ötesinde ilk öğe konumu.|  
|`IList`|Kopyalanacak öğeleri içeren initializer_list.|  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm oluşturucular ayırıcısı nesneyi depolamak ( `Al`) ve listesi başlatılamıyor.  
  
 [get_allocator](#get_allocator) listesini oluşturmak için kullanılan ayırıcısı nesnesinin bir kopyasını döndürür.  
  
 İlk iki oluşturucular belirtin boş başlangıç listesi, ikinci ayırıcısı türünü belirtme ( `Al`) kullanılacak.  
  
 Belirtilen sayının yineleme üçüncü Oluşturucusu belirtir ( `Count`) sınıfı için varsayılan değer öğelerinin **türü**.  
  
 Dördüncü ve beşinci oluşturucular yineleme sayısını belirtin ( `Count`) değerinin öğeleri `Val`.  
  
 Altıncı Oluşturucusu listesinin bir kopyasını belirtir `Right`.  
  
 Liste yedinci Oluşturucusu taşınır `Right`.  
  
 Sekizinci Oluşturucusu bir initializer_list öğeleri belirlemek için kullanır.  
  
 Sonraki iki oluşturucular aralığı kopyalayın `[First, Last)` listesi.  
  
 Oluşturucular hiçbiri tüm ara adetle sınırla gerçekleştirin.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_class_list.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    // Create an empty list c0  
    list <int> c0;  
  
    // Create a list c1 with 3 elements of default value 0  
    list <int> c1(3);  
  
    // Create a list c2 with 5 elements of value 2  
    list <int> c2(5, 2);  
  
    // Create a list c3 with 3 elements of value 1 and with the   
    // allocator of list c2  
    list <int> c3(3, 1, c2.get_allocator());  
  
    // Create a copy, list c4, of list c2  
    list <int> c4(c2);  
  
    // Create a list c5 by copying the range c4[ first,  last)  
    list <int>::iterator c4_Iter = c4.begin();  
    c4_Iter++;  
    c4_Iter++;  
    list <int> c5(c4.begin(), c4_Iter);  
  
    // Create a list c6 by copying the range c4[ first,  last) and with   
    // the allocator of list c2  
    c4_Iter = c4.begin();  
    c4_Iter++;  
    c4_Iter++;  
    c4_Iter++;  
    list <int> c6(c4.begin(), c4_Iter, c2.get_allocator());  
  
    cout << "c1 =";  
    for (auto c : c1)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c2 =";  
    for (auto c : c2)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c3 =";  
    for (auto c : c3)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c4 =";  
    for (auto c : c4)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c5 =";  
    for (auto c : c5)  
        cout << " " << c;  
    cout << endl;  
  
    cout << "c6 =";  
    for (auto c : c6)  
        cout << " " << c;  
    cout << endl;  
  
    // Move list c6 to list c7  
    list <int> c7(move(c6));  
    cout << "c7 =";  
    for (auto c : c7)  
        cout << " " << c;  
    cout << endl;  
  
    // Construct with initializer_list  
    list<int> c8({ 1, 2, 3, 4 });  
    cout << "c8 =";  
    for (auto c : c8)  
        cout << " " << c;  
    cout << endl;  
}  
```  
  
```Output  
c1 = 0 0 0c2 = 2 2 2 2 2c3 = 1 1 1c4 = 2 2 2 2 2c5 = 2 2c6 = 2 2 2c7 = 2 2 2c8 = 1 2 3 4  
```  
  
##  <a name="max_size"></a>List::max_size  
 Uzunluk listesini döndürür.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Olası uzunluk listesi.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_max_size.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::size_type i;  
  
   i = c1.max_size( );  
   cout << "Maximum possible length of the list is " << i << "." << endl;  
}  
```  
  
##  <a name="merge"></a>List::Merge  
 Öğeleri bağımsız değişkeni listeden kaldırır, bunları hedef listesine ekler ve öğeleri artan düzende veya başka bir belirtilen sırayla yeni, birleştirilmiş kümesini sıralar.  
  
```  
void merge(list<Type, Allocator>& right);

template <class Traits>  
void merge(list<Type, Allocator>& right, Traits comp);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Hedef listesiyle birleştirilecek bağımsız değişken listesi.  
  
 `comp`  
 Hedef listenin öğelerini sıralamak için kullanılan karşılaştırma işleci.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken listesi `right` hedef listesi ile birleştirilir.  
  
 Bağımsız değişken ve hedef listeleri tarafından oluşturulan dizisi sıralanmalıdır olduğu karşılaştırma ilişkisiyle sıralanmalıdır. İlk üye işlevi için varsayılan sırayı, artan. İkinci üye işlevi kullanıcı tarafından belirtilen karşılaştırma işlemi uygular `comp` sınıfının **nitelikler**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_merge.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1, c2, c3;  
   list <int>::iterator c1_Iter, c2_Iter, c3_Iter;  
  
   c1.push_back( 3 );  
   c1.push_back( 6 );  
   c2.push_back( 2 );  
   c2.push_back( 4 );  
   c3.push_back( 5 );  
   c3.push_back( 1 );  
  
   cout << "c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   cout << "c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
  
   c2.merge( c1 );  // Merge c1 into c2 in (default) ascending order  
   c2.sort( greater<int>( ) );  
   cout << "After merging c1 with c2 and sorting with >: c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
  
   cout << "c3 =";  
   for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )  
      cout << " " << *c3_Iter;  
   cout << endl;  
  
   c2.merge( c3, greater<int>( ) );  
   cout << "After merging c3 with c2 according to the '>' comparison relation: c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
}  
```  
  
```Output  
c1 = 3 6  
c2 = 2 4  
After merging c1 with c2 and sorting with >: c2 = 6 4 3 2  
c3 = 5 1  
After merging c3 with c2 according to the '>' comparison relation: c2 = 6 5 4 3 2 1  
```  
  
##  <a name="op_eq"></a>List::operator =  
 Liste öğelerini, başka bir listesinin bir kopyasını yerini alır.  
  
```  
list& operator=(const list& right);
list& operator=(list&& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`right`|[Listesi](../standard-library/list-class.md) içine kopyalanmasını `list`.|  
  
### <a name="remarks"></a>Açıklamalar  
 Var olan öğeleri silindikten sonra bir `list`, işleci kopyalar veya içeriğini taşır `right` içine `list`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_operator_as.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list<int> v1, v2, v3;  
   list<int>::iterator iter;  
  
   v1.push_back(10);  
   v1.push_back(20);  
   v1.push_back(30);  
   v1.push_back(40);  
   v1.push_back(50);  
  
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
   v2 = forward< list<int> >(v1);  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
}  
```  
  
##  <a name="pointer"></a>List::pointer  
 Bir listedeki bir öğe için bir işaretçi sağlar.  
  
```
typedef typename Allocator::pointer pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür **işaretçi** bir öğenin değerini değiştirmek için kullanılabilir.  
  
 Çoğu durumda, bir [yineleyici](#iterator) bir liste nesnesi öğelerinde erişmek için kullanılmalıdır.  
  
##  <a name="pop_back"></a>List::pop_back  
 Öğe listesinin sonunda siler.  
  
``` 
void pop_back();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Son öğe boş olmamalıdır. `pop_back`hiçbir zaman bir özel durum oluşturur.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_pop_back.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   cout << "The first element is: " << c1.front( ) << endl;  
   cout << "The last element is: " << c1.back( ) << endl;  
  
   c1.pop_back( );  
   cout << "After deleting the element at the end of the list, "  
           "the last element is: " << c1.back( ) << endl;  
}  
```  
  
```Output  
The first element is: 1  
The last element is: 2  
After deleting the element at the end of the list, the last element is: 1  
```  
  
##  <a name="pop_front"></a>List::pop_front  
 Öğe listesinin başında siler.  
  
``` 
void pop_front();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İlk öğe boş olmamalıdır. `pop_front`hiçbir zaman bir özel durum oluşturur.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_pop_front.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   cout << "The first element is: " << c1.front( ) << endl;  
   cout << "The second element is: " << c1.back( ) << endl;  
  
   c1.pop_front( );  
   cout << "After deleting the element at the beginning of the list, "  
         "the first element is: " << c1.front( ) << endl;  
}  
```  
  
```Output  
The first element is: 1  
The second element is: 2  
After deleting the element at the beginning of the list, the first element is: 2  
```  
  
##  <a name="push_back"></a>List::push_back  
 Bir öğe listesinin sonuna ekler.  
  
```  
void push_back(void push_back(Type&& val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`val`|Öğe listesinin sonuna eklenir.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bir özel durum, listenin sol değiştirilmemiş ve özel durum işlenemezse.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_push_back.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 1 );  
   if ( c1.size( ) != 0 )  
      cout << "Last element: " << c1.back( ) << endl;  
  
   c1.push_back( 2 );  
   if ( c1.size( ) != 0 )  
      cout << "New last element: " << c1.back( ) << endl;  
  
// move initialize a list of strings  
   list <string> c2;  
   string str("a");  
  
   c2.push_back( move( str ) );  
   cout << "Moved first element: " << c2.back( ) << endl;  
}  
```  
  
```Output  
Last element: 1  
New last element: 2  
Moved first element: a  
```  
  
##  <a name="push_front"></a>List::push_front  
 Bir öğe listesini başlangıcına ekler.  
  
```  
void push_front(const Type& val);
void push_front(Type&& val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`val`|Öğeyi listenin başına eklenir.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bir özel durum, listenin sol değiştirilmemiş ve özel durum işlenemezse.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_push_front.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_front( 1 );  
   if ( c1.size( ) != 0 )  
      cout << "First element: " << c1.front( ) << endl;  
  
   c1.push_front( 2 );  
   if ( c1.size( ) != 0 )  
      cout << "New first element: " << c1.front( ) << endl;  
  
// move initialize a list of strings  
   list <string> c2;  
   string str("a");  
  
   c2.push_front( move( str ) );  
   cout << "Moved first element: " << c2.front( ) << endl;  
}  
```  
  
```Output  
First element: 1  
New first element: 2  
Moved first element: a  
```  
  
##  <a name="rbegin"></a>List::rbegin  
 Ters listesindeki ilk öğeyi adresleri yineleyici döndürür.  
  
``` 
const_reverse_iterator rbegin() const;
reverse_iterator rbegin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir ters çift yönlü yineleyici ters listesindeki ilk öğeyi Adresleme (veya ne unreversed listenin son öğesi olsaydı adresleme).  
  
### <a name="remarks"></a>Açıklamalar  
 `rbegin`Ters listesiyle kullanılan gibi [başlamak](#begin) bir listesiyle kullanılır.  
  
 Varsa dönüş değerini `rbegin` atanmış bir `const_reverse_iterator`, liste nesnesi değiştirilemez. Varsa dönüş değerini `rbegin` atanmış bir `reverse_iterator`, liste nesnesi değiştirilebilir.  
  
 `rbegin`bir liste geriye doğru yinelemek için kullanılabilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_rbegin.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
   list <int>::reverse_iterator c1_rIter;  
  
   // If the following line replaced the line above, *c1_rIter = 40;  
   // (below) would be an error  
   //list <int>::const_reverse_iterator c1_rIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1_rIter = c1.rbegin( );  
   cout << "The last element in the list is " << *c1_rIter << "." << endl;  
  
   cout << "The list is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   // rbegin can be used to start an iteration through a list in   
   // reverse order  
   cout << "The reversed list is:";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << " " << *c1_rIter;  
   cout << endl;  
  
   c1_rIter = c1.rbegin( );  
 *c1_rIter = 40;  
   cout << "The last element in the list is now " << *c1_rIter << "." << endl;  
}  
```  
  
```Output  
The last element in the list is 30.  
The list is: 10 20 30  
The reversed list is: 30 20 10  
The last element in the list is now 40.  
```  
  
##  <a name="reference"></a>List::Reference  
 Listede depolanmış bir öğe için bir başvuru sağlar türü.  
  
```  
typedef typename Allocator::reference reference;  
```  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_ref.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   int &i = c1.front( );  
   int &j = c1.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="remove"></a>List::Remove  
 Belirtilen değerle eşleşen listedeki öğeleri siler.  
  
``` 
void remove(const Type& val);
```  
  
### <a name="parameters"></a>Parametreler  
 `val`  
 Bu öğenin kaldırma listeden bir öğe tarafından tutulan varsa sonuçlanır değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Kalan öğelerin sırasını etkilenmez.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_remove.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter, c2_Iter;  
  
   c1.push_back( 5 );  
   c1.push_back( 100 );  
   c1.push_back( 5 );  
   c1.push_back( 200 );  
   c1.push_back( 5 );  
   c1.push_back( 300 );  
  
   cout << "The initial list is c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   list <int> c2 = c1;  
   c2.remove( 5 );  
   cout << "After removing elements with value 5, the list becomes c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The initial list is c1 = 5 100 5 200 5 300  
After removing elements with value 5, the list becomes c2 = 100 200 300  
```  
  
##  <a name="remove_if"></a>List::remove_if  
 Öğeleri belirtilen bir koşulu karşılanıp listeden siler.  
  
``` 
template <class Predicate>  
void remove_if(Predicate pred)  
```  
  
### <a name="parameters"></a>Parametreler  
 `pred`  
 Bir öğe tarafından karşılanan varsa bu öğe listeden silinmesini sonuçlanır hangi birli koşul.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_remove_if.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
template <class T> class is_odd : public std::unary_function<T, bool>   
{  
public:  
   bool operator( ) ( T& val )   
   {  
   return ( val % 2 ) == 1;  
   }  
};  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter, c2_Iter;  
  
   c1.push_back( 3 );  
   c1.push_back( 4 );  
   c1.push_back( 5 );  
   c1.push_back( 6 );  
   c1.push_back( 7 );  
   c1.push_back( 8 );  
  
   cout << "The initial list is c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   list <int> c2 = c1;  
   c2.remove_if( is_odd<int>( ) );  
  
   cout << "After removing the odd elements, "  
        << "the list becomes c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The initial list is c1 = 3 4 5 6 7 8  
After removing the odd elements, the list becomes c2 = 4 6 8  
```  
  
##  <a name="rend"></a>List::rend  
 Ters listesindeki son öğeyi izleyen konumu adresleri yineleyici döndürür.  
  
``` 
const_reverse_iterator rend() const;
reverse_iterator rend();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 (İlk öğe unreversed listesinde öncesinde konum) ters listesindeki son öğeyi başarılı konumu adresleri ters çift yönlü yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 `rend`Ters listesiyle kullanılan gibi [son](#end) bir listesiyle kullanılır.  
  
 Varsa dönüş değerini `rend` atanmış bir `const_reverse_iterator`, liste nesnesi değiştirilemez. Varsa dönüş değerini `rend` atanmış bir `reverse_iterator`, liste nesnesi değiştirilebilir.  
  
 `rend`Ters yineleyici olup, listenin sonuna sınırına için test etmek için kullanılabilir.  
  
 Tarafından döndürülen değer `rend` değil başvuru yapıldı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_rend.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
   list <int>::reverse_iterator c1_rIter;  
  
   // If the following line had replaced the line above, an error would   
   // have resulted in the line modifying an element (commented below)  
   // because the iterator would have been const  
   // list <int>::const_reverse_iterator c1_rIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_rIter = c1.rend( );  
   c1_rIter --;  // Decrementing a reverse iterator moves it forward in   
                 // the list (to point to the first element here)  
   cout << "The first element in the list is: " << *c1_rIter << endl;  
  
   cout << "The list is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   // rend can be used to test if an iteration is through all of the   
   // elements of a reversed list  
   cout << "The reversed list is:";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << " " << *c1_rIter;  
   cout << endl;  
  
   c1_rIter = c1.rend( );  
   c1_rIter--;  // Decrementing the reverse iterator moves it backward   
                // in the reversed list (to the last element here)  
  
 *c1_rIter = 40;  // This modification of the last element would have   
                    // caused an error if a const_reverse iterator had   
                    // been declared (as noted above)  
  
   cout << "The modified reversed list is:";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << " " << *c1_rIter;  
   cout << endl;  
}  
```  
  
```Output  
The first element in the list is: 10  
The list is: 10 20 30  
The reversed list is: 30 20 10  
The modified reversed list is: 30 20 40  
```  
  
##  <a name="resize"></a>List::Resize  
 Bir liste için yeni bir boyutunu belirtir.  
  
``` 
void resize(size_type _Newsize);
void resize(size_type _Newsize, Type val);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Newsize`  
 Listeden yeni boyutu.  
  
 `val`  
 Yeni boyutu büyükse, listeye eklenecek yeni öğeler değeri, özgün boyutu. Değer belirtilmezse, yeni öğeler sınıfı için varsayılan değeri atanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin boyutu istenen boyuttan daha az ise `_Newsize`, istenen boyuta ulaşana kadar öğeleri listesine eklenir.  
  
 Listenin boyutu istenen boyutundan daha büyükse listesi boyuta ulaşana kadar listesinin sonuna yakın öğeleri silinir `_Newsize`.  
  
 Liste mevcut boyutunu istenen boyutu ile aynı olduğunda, hiçbir işlem yapılmadı.  
  
 [boyutu](#size) listesi geçerli boyutu yansıtır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_resize.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{   
   using namespace std;  
   list <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1.resize( 4,40 );  
   cout << "The size of c1 is " << c1.size( ) << endl;  
   cout << "The value of the last element is " << c1.back( ) << endl;  
  
   c1.resize( 5 );  
   cout << "The size of c1 is now " << c1.size( ) << endl;  
   cout << "The value of the last element is now " << c1.back( ) << endl;  
  
   c1.resize( 2 );  
   cout << "The reduced size of c1 is: " << c1.size( ) << endl;  
   cout << "The value of the last element is now " << c1.back( ) << endl;  
}  
```  
  
```Output  
The size of c1 is 4  
The value of the last element is 40  
The size of c1 is now 5  
The value of the last element is now 0  
The reduced size of c1 is: 2  
The value of the last element is now 20  
```  
  
##  <a name="reverse"></a>List::reverse  
 Öğeleri listede ortaya sırasını tersine çevirir.  
  
``` 
void reverse();
```  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_reverse.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   cout << "c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.reverse( );  
   cout << "Reversed c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
}  
```  
  
```Output  
c1 = 10 20 30  
Reversed c1 = 30 20 10  
```  
  
##  <a name="reverse_iterator"></a>List::reverse_iterator  
 Okuma veya ters listesindeki bir öğeyi değiştirmek için bir çift yönlü yineleyici sağlayan türü.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `reverse_iterator` ters listesinde yinelemek için kullanılır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [rbegin](#rbegin).  
  
##  <a name="size"></a>List::size  
 Bir listedeki öğe sayısını döndürür.  
  
``` 
size_type size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listeden geçerli uzunluğu.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_size.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list <int> c1;  
   list <int>::size_type i;  
  
   c1.push_back( 5 );  
   i = c1.size( );  
   cout << "List length is " << i << "." << endl;  
  
   c1.push_back( 7 );  
   i = c1.size( );  
   cout << "List length is now " << i << "." << endl;  
}  
```  
  
```Output  
List length is 1.  
List length is now 2.  
```  
  
##  <a name="size_type"></a>List::size_type  
 Listedeki öğeleri sayar türü.  
  
```  
typedef typename Allocator::size_type size_type;  
```  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [boyutu](#size).  
  
##  <a name="sort"></a>List::sort  
 Öğeleri listesini artan düzende veya başka bir kullanıcı tarafından belirtilen sipariş göre düzenler.  
  
``` 
void sort();

template <class Traits>  
void sort(Traits comp);
```  
  
### <a name="parameters"></a>Parametreler  
 `comp`  
 Birbirini izleyen öğeleri sıralamak için kullanılan karşılaştırma işleci.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi varsayılan olarak artan düzende öğeleri koyar.  
  
 Kullanıcı tarafından belirtilen karşılaştırma işlemi göre öğeleri üye şablon işlevi siparişleri `comp` sınıfının **nitelikler**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_sort.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter;  
  
   c1.push_back( 20 );  
   c1.push_back( 10 );  
   c1.push_back( 30 );  
  
   cout << "Before sorting: c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.sort( );  
   cout << "After sorting c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.sort( greater<int>( ) );  
   cout << "After sorting with 'greater than' operation, c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
}  
```  
  
```Output  
Before sorting: c1 = 20 10 30  
After sorting c1 = 10 20 30  
After sorting with 'greater than' operation, c1 = 30 20 10  
```  
  
##  <a name="splice"></a>List::splice  
 Öğeleri kaynak listeden kaldırır ve hedef listesine ekler.  
  
```  
// insert the entire source list  
void splice(const_iterator Where, list<Type, Allocator>& Source);
void splice(const_iterator Where, list<Type, Allocator>&& Source); 

// insert one element of the source list  
void splice(const_iterator Where, list<Type, Allocator>& Source, const_iterator Iter);
void splice(const_iterator Where, list<Type, Allocator>&& Source, const_iterator Iter);
 
// insert a range of elements from the source list  
void splice(const_iterator Where, list<Type, Allocator>& Source, const_iterator First, const_iterator Last);
void splice(const_iterator Where, list<Type, Allocator>&& Source, const_iterator First, const_iterator Last);
```  
  
### <a name="parameters"></a>Parametreler  
 `Where`  
 Eklenecek önce hedef listesi konumu.  
  
 `Source`  
 Hedef listeye eklenecek kaynak listesi.  
  
 `Iter`  
 Kaynak listeden eklenecek öğe.  
  
 `First`  
 Kaynak listeden eklenecek aralıktaki ilk öğe.  
  
 `Last`  
 Kaynak listeden eklenecek aralıktaki ilk konumu son öğenin ötesinde.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevleri ilk çiftinin başvurulan konumu önce hedef listesi kaynak listesinde tüm öğeler ekler `Where` ve kaynak listeden tüm öğeleri kaldırır. ( `&Source` eşit değil gerekir `this`.)  
  
 Üye işlevleri ikinci çiftinin başvurulan öğesi ekler `Iter` hedef listesindeki konumu başvurulan önce `Where` ve kaldırır `Iter` source listesinden. (Varsa `Where == Iter || Where == ++Iter`, hiçbir değişiklik olmaz.)  
  
 Üye işlevleri üçüncü çiftinin belirlenen aralığı ekler [ `First`, `Last`) hedef listesi öğesinde başvurulan önce `Where` ve öğeleri aralığını kaynak listeden kaldırır. (Varsa `&Source == this`, aralığın `[First, Last)` gösterdiği öğesi içermemesi `Where`.)  
  
 Ranged splice ekliyorsa `N` öğeleri ve `&Source != this`, sınıfın bir nesnesi [yineleyici](../standard-library/forward-list-class.md#iterator) artırılır `N` kez.  
  
 Tüm durumlarda yineleyiciler, işaretçileri ya da spliced öğelerine başvuran başvurusu geçerli kalır ve hedef kapsayıcıya aktarılır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_splice.cpp  
// compile with: /EHsc /W4  
#include <list>  
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
    list<int> c1{10,11};  
    list<int> c2{20,21,22};  
    list<int> c3{30,31};  
    list<int> c4{40,41,42,43};  
  
    list<int>::iterator where_iter;  
    list<int>::iterator first_iter;  
    list<int>::iterator last_iter;  
  
    cout << "Beginning state of lists:" << endl;  
    cout << "c1 = ";  
    print(c1);  
    cout << "c2 = ";  
    print(c2);  
    cout << "c3 = ";  
    print(c3);  
    cout << "c4 = ";  
    print(c4);  
  
    where_iter = c2.begin();  
    ++where_iter; // start at second element  
    c2.splice(where_iter, c1);  
    cout << "After splicing c1 into c2:" << endl;  
    cout << "c1 = ";  
    print(c1);  
    cout << "c2 = ";  
    print(c2);  
  
    first_iter = c3.begin();  
    c2.splice(where_iter, c3, first_iter);  
    cout << "After splicing the first element of c3 into c2:" << endl;  
    cout << "c3 = ";  
    print(c3);  
    cout << "c2 = ";  
    print(c2);  
  
    first_iter = c4.begin();  
    last_iter = c4.end();  
    // set up to get the middle elements  
    ++first_iter;  
    --last_iter;  
    c2.splice(where_iter, c4, first_iter, last_iter);  
    cout << "After splicing a range of c4 into c2:" << endl;  
    cout << "c4 = ";  
    print(c4);  
    cout << "c2 = ";  
    print(c2);  
}  
  
```  
  
```Output  
Beginning state of lists:c1 = 2 elements: (10) (11)c2 = 3 elements: (20) (21) (22)c3 = 2 elements: (30) (31)c4 = 4 elements: (40) (41) (42) (43)After splicing c1 into c2:c1 = 0 elements:c2 = 5 elements: (20) (10) (11) (21) (22)After splicing the first element of c3 into c2:c3 = 1 elements: (31)c2 = 6 elements: (20) (10) (11) (30) (21) (22)After splicing a range of c4 into c2:c4 = 2 elements: (40) (43)c2 = 8 elements: (20) (10) (11) (30) (41) (42) (21) (22)  
```  
  
##  <a name="swap"></a>List::Swap  
 İki liste öğelerini değiş tokuş eder.  
  
``` 
void swap(list<Type, Allocator>& right);
friend void swap(list<Type, Allocator>& left, list<Type, Allocator>& right)  
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Öğeleri takas için sağlama listesi veya öğeleri olan listesinin olanlar değiştirilmek üzere listesi `left`.  
  
 `left`  
 Öğeleri olan listesinin olanlar değiştirilebilmesi için bir liste `right`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_swap.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list <int> c1, c2, c3;  
   list <int>::iterator c1_Iter;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 3 );  
   c2.push_back( 10 );  
   c2.push_back( 20 );  
   c3.push_back( 100 );  
  
   cout << "The original list c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.swap( c2 );  
  
   cout << "After swapping with c2, list c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   swap( c1,c3 );  
  
   cout << "After swapping with c3, list c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The original list c1 is: 1 2 3  
After swapping with c2, list c1 is: 10 20  
After swapping with c3, list c1 is: 100  
```  
  
##  <a name="unique"></a>List::Unique  
 Bitişik yinelenen öğeler veya bir listeden bazı diğer ikili koşulu karşılayan bitişik öğeleri kaldırır.  
  
```  
void unique();

template <class BinaryPredicate>  
void unique(BinaryPredicate pred);
```  
  
### <a name="parameters"></a>Parametreler  
 `pred`  
 Birbirini izleyen öğeleri karşılaştırmak için kullanılan ikili koşul.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm yinelenen öğeler bitişik; böylece bu işlevi listenin sıralı olduğunu varsayar. Bitişik olmayan çoğaltmaları silinmez.  
  
 İlk üye işlevi, önceki öğesine eşit karşılaştırır her öğeyi kaldırır.  
  
 Koşul işlevini karşılayan her öğenin ikinci üye işlevi kaldırır `pred` önceki öğeyle karşılaştırıldığında. Bildirilen ikili işlevi nesnelerden herhangi birini kullanabilirsiniz `<functional>`bağımsız değişkeni pred veya üstbilgisi oluşturabilir, kendi.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_unique.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   list <int> c1;  
   list <int>::iterator c1_Iter, c2_Iter,c3_Iter;  
   not_equal_to<int> mypred;  
  
   c1.push_back( -10 );  
   c1.push_back( 10 );  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 20 );  
   c1.push_back( -10 );  
  
   cout << "The initial list is c1 =";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   list <int> c2 = c1;  
   c2.unique( );  
   cout << "After removing successive duplicate elements, c2 =";  
   for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
      cout << " " << *c2_Iter;  
   cout << endl;  
  
   list <int> c3 = c2;  
   c3.unique( mypred );  
   cout << "After removing successive unequal elements, c3 =";  
   for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )  
      cout << " " << *c3_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The initial list is c1 = -10 10 10 20 20 -10  
After removing successive duplicate elements, c2 = -10 10 20 -10  
After removing successive unequal elements, c3 = -10 -10  
```  
  
##  <a name="value_type"></a>List::value_type  
 Bir listede depolanan veri türünü temsil eden tür.  
  
```  
typedef typename Allocator::value_type value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `value_type`Şablon parametresi için bir eş anlamlı olduğundan **türü**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// list_value_type.cpp  
// compile with: /EHsc  
#include <list>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   list<int>::value_type AnInt;  
   AnInt = 44;  
   cout << AnInt << endl;  
}  
```  
  
```Output  
44  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Liste >](../standard-library/list.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

