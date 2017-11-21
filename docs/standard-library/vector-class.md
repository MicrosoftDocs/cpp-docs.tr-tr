---
title: "vector sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vector/std::vector::allocator_type
- vector/std::vector::const_iterator
- vector/std::vector::const_pointer
- vector/std::vector::const_reference
- vector/std::vector::const_reverse_iterator
- vector/std::vector::difference_type
- vector/std::vector::iterator
- vector/std::vector::pointer
- vector/std::vector::reference
- vector/std::vector::reverse_iterator
- vector/std::vector::size_type
- vector/std::vector::value_type
- vector/std::vector::assign
- vector/std::vector::at
- vector/std::vector::back
- vector/std::vector::begin
- vector/std::vector::capacity
- vector/std::vector::cbegin
- vector/std::vector::cend
- vector/std::vector::crbegin
- vector/std::vector::crend
- vector/std::vector::clear
- vector/std::vector::data
- vector/std::vector::emplace
- vector/std::vector::emplace_back
- vector/std::vector::empty
- vector/std::vector::end
- vector/std::vector::erase
- vector/std::vector::front
- vector/std::vector::get_allocator
- vector/std::vector::insert
- vector/std::vector::max_size
- vector/std::vector::pop_back
- vector/std::vector::push_back
- vector/std::vector::rbegin
- vector/std::vector::rend
- vector/std::vector::reserve
- vector/std::vector::resize
- vector/std::vector::shrink_to_fit
- vector/std::vector::size
- vector/std::vector::swap
dev_langs: C++
helpviewer_keywords:
- std::vector [C++], allocator_type
- std::vector [C++], const_iterator
- std::vector [C++], const_pointer
- std::vector [C++], const_reference
- std::vector [C++], const_reverse_iterator
- std::vector [C++], difference_type
- std::vector [C++], iterator
- std::vector [C++], pointer
- std::vector [C++], reference
- std::vector [C++], reverse_iterator
- std::vector [C++], size_type
- std::vector [C++], value_type
- std::vector [C++], assign
- std::vector [C++], at
- std::vector [C++], back
- std::vector [C++], begin
- std::vector [C++], capacity
- std::vector [C++], cbegin
- std::vector [C++], cend
- std::vector [C++], crbegin
- std::vector [C++], crend
- std::vector [C++], clear
- std::vector [C++], data
- std::vector [C++], emplace
- std::vector [C++], emplace_back
- std::vector [C++], empty
- std::vector [C++], end
- std::vector [C++], erase
- std::vector [C++], front
- std::vector [C++], get_allocator
- std::vector [C++], insert
- std::vector [C++], max_size
- std::vector [C++], pop_back
- std::vector [C++], push_back
- std::vector [C++], rbegin
- std::vector [C++], rend
- std::vector [C++], reserve
- std::vector [C++], resize
- std::vector [C++], shrink_to_fit
- std::vector [C++], size
- std::vector [C++], swap
ms.assetid: a3e0a8f8-7565-4fe0-93e4-e4d74ae1b70d
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 57cc809cad0ef81d59e58a4fa0d582f2964fdbb8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="vector-class"></a>vector Sınıfı
C++ Standart Kitaplığı vector sınıfı doğrusal bir düzenleme içinde belirli bir türde öğelerini düzenlemek ve herhangi bir öğeye hızlı rastgele erişim izin veren dizisi kapsayıcıların şablon sınıfıdır. Rasgele erişim performansı üst düzey olduğunda sırası için tercih edilen kapsayıcı olması gerekir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Type, class Allocator = allocator<Type>>  
class vector  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Türü*  
 Vektör depolanması için öğe veri türü  
  
 `Allocator`  
 Vector öğesinin ayırma ve bellek ayırmayı kaldırma hakkında ayrıntılar yalıtan saklı ayırıcısı nesneyi temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **ayırıcısı***\<türü >.*  
  
## <a name="remarks"></a>Açıklamalar  
 Vektörler sabit zaman eklemeler ve silmeler dizisi sonunda izin verin. Ekleme veya öğeleri ortasında bir vektör silme doğrusal süresi gerektirir. Performansını [deque sınıfı](../standard-library/deque-class.md) kapsayıcıdır eklemeler ve silmeler başlangıcına ve sonuna bir sıra göre üstün. [Sınıf listesi](../standard-library/list-class.md) kapsayıcıdır eklemeler ve silmeler bir dizisi içindeki herhangi bir konumdaki göre üstün.  
  
 Üye işlevi geçerli depolama kapasitesinin vektör nesnesi içinde yer alan sırası artırmanız gerekir vektör yeniden ayırma oluşur. Diğer eklemeler ve silme dizisi içindeki çeşitli depolama adresleri değiştirebilir. Tüm bu gibi durumlarda, Yineleyiciler veya geçersiz hale sırası değiştirilmiş kısımlarını işaret eden başvuruları. Hiçbir yeniden ayırma olursa, yalnızca yineleyiciler ve başvurular ekleme/silme noktası önce geçerli kalır.  
  
 [Vektör\<bool > sınıfı](../standard-library/vector-bool-class.md) tam uzmanlaşması türü bool öğeleri için Şablon sınıfı vektör uzmanlık tarafından kullanılan temel alınan türü için bir ayırıcı sahip olduğu.  
  
 [Vektör\<bool > sınıfa referans](../standard-library/vector-bool-class.md#reference_class) , nesneleri bir vektör içinde (tek BITS) öğelere başvurular sağlayabilir iç içe bir sınıf\<bool > nesne.  
  
## <a name="members"></a>Üyeler  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[vektör](#vector)|Belirli bir boyuta veya belirli bir değere öğelerin veya belirli bir ile Vektör yapıları `allocator` veya başka bir vektör kopyası olarak.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|Temsil eden bir tür `allocator` vektör nesne için sınıf.|  
|[const_iterator](#const_iterator)|Rasgele erişim yineleyici bu can sağlayan bir türü okuma bir `const` vektör öğesinde.|  
|[const_pointer](#const_pointer)|Bir işaretçi sağlayan bir türü bir `const` vektör öğesinde.|  
|[const_reference](#const_reference)|Bir başvuru sağlayan bir türü bir `const` okumak ve gerçekleştirmek için bir vektör depolanan öğesi `const` işlemleri.|  
|[const_reverse_iterator](#const_reverse_iterator)|Herhangi bir rastgele erişim yineleyici bu can sağlayan bir türü okuma `const` vektör öğesinde.|  
|[difference_type](#difference_type)|Vektör iki öğelerinde adreslerini arasındaki farkı sağlayan türü.|  
|[Yineleyici](#iterator)|Rasgele erişim yineleyici sağlayan bir türünü okumak veya herhangi bir vektör öğesinde değiştirin.|  
|[İşaretçi](#pointer)|Vektör bir öğesine bir işaretçi sağlayan türü.|  
|[başvuru](#reference)|Bir vektör depolanan bir öğe için bir başvuru sağlar türü.|  
|[reverse_iterator](#reverse_iterator)|Rasgele erişim yineleyici sağlayan bir tür okumak veya ters vektörü herhangi bir öğeyi değiştirin.|  
|[size_type](#size_type)|Vektör öğelerinde sayar türü.|  
|[value_type](#value_type)|Vektör içinde depolanan veri türünü temsil eden tür.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[Ata](#assign)|Vektör siler ve belirtilen öğelerini boş vektör kopyalar.|  
|[konumundaki](#at)|Belirtilen bir konumdaki öğeye başvuru vektörü döndürür.|  
|[Geri](#back)|Vektör son öğesinden bir başvuru döndürür.|  
|[başlayın](#begin)|Rasgele erişim yineleyici vektör ilk öğe döndürür.|  
|[Kapasite](#capacity)|Daha fazla depolama alanı ayırmadan vektör içerebilir öğe sayısını döndürür.|  
|[cbegin](#cbegin)|Rasgele erişim const yineleyici vektör ilk öğe döndürür.|  
|[cend](#cend)|Rasgele erişim const yineleyici vektörü yalnızca ötesinde işaret döndürür.|  
|[crbegin](#crbegin)|Const yineleyici ters vektör ilk öğe döndürür.|  
|[crend](#crend)|Const yineleyici ters vektör sonunu döndürür.|  
|[Temizle](#clear)|Vektör öğelerini siler.|  
|[veri](#data)|Vektör ilk öğe için bir işaretçi döndürür.|  
|[emplace](#emplace)|Belirtilen konumda vektör içine yerinde oluşturulan bir öğe ekler.|  
|[emplace_back](#emplace_back)|Vektör sonuna yerinde oluşturulan bir öğe ekler.|  
|[boş](#empty)|Vektör kapsayıcı boşsa, testleri.|  
|[Bitiş](#end)|Vektör sonuna işaret eden bir rastgele erişim yineleyici döndürür.|  
|[silme](#erase)|Bir öğenin veya öğe aralığını belirtilen konumlardan vektör kaldırır.|  
|[Ön](#front)|Bir vektör ilk öğe için bir başvuru döndürür.|  
|[get_allocator](#get_allocator)|Bir nesne döndürür `allocator` vektörü ile kullanılan bir sınıftır.|  
|[Ekle](#insert)|Bir öğenin veya öğe sayısı belirtilen konumda vektör ekler.|  
|[max_size](#max_size)|Vektör maksimum uzunluğunu döndürür.|  
|[pop_back](#pop_back)|Vektör ucundaki öğe siler.|  
|[push_back](#push_back)|Bir öğenin vektör sonuna ekleyin.|  
|[rbegin](#rbegin)|Yineleyici ters vektör ilk öğe döndürür.|  
|[rend](#rend)|Yineleyici ters vektör sonunu döndürür.|  
|[ayırma](#reserve)|Depolama vektör nesnesi için minimum uzunluğu saklı tutar.|  
|[yeniden boyutlandırma](#resize)|Yeni bir vektör boyutu belirtir.|  
|[shrink_to_fit](#shrink_to_fit)|Fazlalık kapasite atar.|  
|[boyutu](#size)|Vektör öğe sayısını döndürür.|  
|[değiştirme](#swap)|İki vektör öğelerini değiş tokuş eder.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator &#91; &#93;](#op_at)|Vektör öğesine belirtilen konumda bir başvuru döndürür.|  
|[işleç =](#op_eq)|Vektör öğelerini başka bir vektör bir kopyası ile değiştirir.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<vektör >  
  
 **Namespace:** std  
  
##  <a name="allocator_type"></a>Vector::allocator_type  
 Allocator sınıfı vektör nesnesinin temsil eden tür.  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `allocator_type`Şablon parametresi için bir eş anlamlı olduğundan **ayırıcısı.**  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [get_allocator](#get_allocator) kullanan bir örnek `allocator_type`.  
  
##  <a name="assign"></a>Vector::Assign  
 Vektör siler ve belirtilen öğelerini boş vektör kopyalar.  
  
```  
void assign(size_type Count, const Type& Val);
void assign(initializer_list<Type> IList);

template <class InputIterator>  
void assign(InputIterator First, InputIterator Last);
```  
  
### <a name="parameters"></a>Parametreler  
 `First`  
 Kopyalanacak öğe aralığını ilk öğe konumu.  
  
 `Last`  
 Kopyalanacak öğeleri aralık ötesinde ilk öğe konumu.  
  
 `Count`  
 Vektör eklenen bir öğenin kopya sayısı.  
  
 `Val`  
 Vektör eklenen öğesinin değeri.  
  
 `IList`  
 Eklemek için öğeleri içeren initializer_list.  
  
### <a name="remarks"></a>Açıklamalar  
 Var olan herhangi bir vektör öğelerinde silindikten sonra ya da ekler öğeleri belirtilen bir dizi özgün öğesinden yeni bir öğesi belirtilen vektör içine bir vektör ya da ekler kopyaları içine atayın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
/ vector_assign.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    vector<int> v1, v2, v3;  
  
    v1.push_back(10);  
    v1.push_back(20);  
    v1.push_back(30);  
    v1.push_back(40);  
    v1.push_back(50);  
  
    cout << "v1 = ";  
    for (auto& v : v1){  
        cout << v << " ";  
    }  
    cout << endl;  
  
    v2.assign(v1.begin(), v1.end());  
    cout << "v2 = ";  
    for (auto& v : v2){  
        cout << v << " ";  
    }  
    cout << endl;  
  
    v3.assign(7, 4);  
    cout << "v3 = ";  
    for (auto& v : v3){  
        cout << v << " ";  
    }  
    cout << endl;  
  
    v3.assign({ 5, 6, 7 });  
    for (auto& v : v3){  
        cout << v << " ";  
    }  
    cout << endl;  
}  
  
```  
  
##  <a name="at"></a>Vector::AT  
 Belirtilen bir konumdaki öğeye başvuru vektörü döndürür.  
  
```  
reference at(size_type _Pos);

const_reference at(size_type _Pos) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Pos`  
 Vektör başvurmak için öğesi alt simge veya konum sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağımsız değişkeni alt indisli bir dizi öğesine başvuru. Varsa `_Off` vektör boyutundan büyük **adresindeki** bir özel durum oluşturur.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa dönüş değerini **adresindeki** atanmış bir `const_reference`, vektör nesnesi değiştirilemez. Varsa dönüş değerini **adresindeki** atanmış bir **başvuru**, vektör nesnesi değiştirilebilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_at.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
  
   const int &i = v1.at( 0 );  
   int &j = v1.at( 1 );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="back"></a>Vector::Back  
 Vektör son öğesinden bir başvuru döndürür.  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Vektör son öğesi. Vektör boşsa, dönüş değeri tanımlanmamıştır.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa dönüş değerini **geri** atanmış bir `const_reference`, vektör nesnesi değiştirilemez. Varsa dönüş değerini **geri** atanmış bir **başvuru**, vektör nesnesi değiştirilebilir.  
  
 Kullanarak derlendiğinde [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) bir öğe boş bir vektör erişmeye 1 veya 2 olarak tanımlanan, bir çalışma zamanı hatası oluşur.  Bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md) daha fazla bilgi için.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_back.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 11 );  
  
   int& i = v1.back( );  
   const int& ii = v1.front( );  
  
   cout << "The last integer of v1 is " << i << endl;  
   i--;  
   cout << "The next-to-last integer of v1 is "<< ii << endl;  
}  
```  
  
##  <a name="begin"></a>Vector::Begin  
 Rasgele erişim yineleyici vektör ilk öğe döndürür.  
  
```  
const_iterator begin() const;

 
iterator begin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk öğe adresleme rasgele erişim yineleyici `vector` ya da boş bir başarılı konuma `vector`. İle döndürülen değer her zaman karşılaştırmanız gerekir [vector::end](#end) geçerli olduğundan emin olmak için.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa dönüş değerini `begin` atanmış bir [vector::const_iterator](#const_iterator), `vector` nesnesi değiştirilemez. Varsa dönüş değerini `begin` atanmış bir [vector::iterator](#iterator), `vector` nesne değiştirilebilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_begin.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    vector<int> c1;  
    vector<int>::iterator c1_Iter;  
    vector<int>::const_iterator c1_cIter;  
  
    c1.push_back(1);  
    c1.push_back(2);  
  
    cout << "The vector c1 contains elements:";  
    c1_Iter = c1.begin();  
    for (; c1_Iter != c1.end(); c1_Iter++)  
    {  
        cout << " " << *c1_Iter;  
    }  
    cout << endl;  
  
    cout << "The vector c1 now contains elements:";  
    c1_Iter = c1.begin();  
 *c1_Iter = 20;  
    for (; c1_Iter != c1.end(); c1_Iter++)  
    {  
        cout << " " << *c1_Iter;  
    }  
    cout << endl;  
  
    // The following line would be an error because iterator is const  
    // *c1_cIter = 200;  
}  
```  
  
```Output  
The vector c1 contains elements: 1 2  
The vector c1 now contains elements: 20 2  
```  
  
##  <a name="capacity"></a>Vector::Capacity  
 Daha fazla depolama alanı ayırmadan vektör içerebilir öğe sayısını döndürür.  
  
```  
size_type capacity() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Vektör için ayrılan depolama alanını geçerli uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini [yeniden boyutlandırma](#resize) uyum için yeterli bellek ayrılırsa daha verimli olacaktır. Üye işlevini [yedek](#reserve) ayrılmış bellek miktarı belirtmek için.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_capacity.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
  
   v1.push_back( 1 );  
   cout << "The length of storage allocated is "  
        << v1.capacity( ) << "." << endl;  
  
   v1.push_back( 2 );  
   cout << "The length of storage allocated is now "  
        << v1.capacity( ) << "." << endl;  
}  
```  
  
```Output  
The length of storage allocated is 1.  
The length of storage allocated is now 2.  
```  
  
##  <a name="cbegin"></a>Vector::cbegin  
 Döndürür bir `const` aralığın ilk öğe adresleri yineleyici.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `const` ilk öğede aralığı ya da yalnızca boş bir aralığın ötesinde konumunu işaret rasgele erişim yineleyici (boş bir aralığın için `cbegin() == cend()`).  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri ile `cbegin`, öğeleri aralığında değiştirilemez.  
  
 Bu üye işlevi yerine kullanabileceğiniz `begin()` üye işlevi dönüş değeri garanti `const_iterator`. Genellikle, ile birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` bir değiştirilebilir için (olmayan `const`) destekleyen herhangi bir türde kapsayıcı `begin()` ve `cbegin()`.  
  
```cpp  
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator  
```  
  
##  <a name="cend"></a>Vector::cend  
 Döndürür bir `const` konumun yalnızca bir aralıkta son öğenin ötesinde adresleri yineleyici.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `const` yalnızca aralığın sonunu aşan işaret rasgele erişim yineleyici.  
  
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
  
##  <a name="clear"></a>Vector::Clear  
 Vektör öğelerini siler.  
  
```  
void clear();
```  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_clear.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "The size of v1 is " << v1.size( ) << endl;  
   v1.clear( );  
   cout << "The size of v1 after clearing is " << v1.size( ) << endl;  
}  
```  
  
```Output  
The size of v1 is 3  
The size of v1 after clearing is 0  
```  
  
##  <a name="const_iterator"></a>Vector::const_iterator  
 Rasgele erişim yineleyici bu can sağlayan bir türü okuma bir **const** vektör öğesinde.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [geri](#back) kullanan bir örnek `const_iterator`.  
  
##  <a name="const_pointer"></a>Vector::const_pointer  
 Bir işaretçi sağlayan bir türü bir **const** vektör öğesinde.  
  
```  
typedef typename Allocator::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.  
  
 Bir [yineleyici](#iterator) vektör bir öğesine erişmek için daha yaygın olarak kullanılır.  
  
##  <a name="const_reference"></a>Vector::const_reference  
 Bir başvuru sağlayan bir türü bir **const** okumak ve gerçekleştirmek için bir vektör depolanan öğesi **const** işlemleri.  
  
```  
typedef typename Allocator::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_reference` bir öğenin değerini değiştirmek için kullanılamaz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_const_ref.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
  
   const vector <int> v2 = v1;  
   const int &i = v2.front( );  
   const int &j = v2.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
  
   // The following line would cause an error as v2 is const  
   // v2.push_back( 30 );  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="const_reverse_iterator"></a>Vector::const_reverse_iterator  
 Herhangi bir rastgele erişim yineleyici bu can sağlayan bir türü okuma **const** vektör öğesinde.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_reverse_iterator` bir öğenin değerini değiştiremez ve vektör ters yinelemek için kullanılır.  
  
### <a name="example"></a>Örnek  
  Bkz: [rbegin](#rbegin) yineleyici bildirme ve nasıl kullanılacağını gösteren bir örnek.  
  
##  <a name="crbegin"></a>Vector::crbegin  
 Const yineleyici ters vektör ilk öğe döndürür.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir const ters ilk öğe bir ters adresleme rasgele erişim yineleyici [vektör](../standard-library/vector-class.md) veya ne son öğesi unreversed olsaydı adresleme `vector`.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri ile `crbegin`, `vector` nesnesi değiştirilemez.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_crbegin.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator v1_Iter;  
   vector <int>::const_reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   v1_Iter = v1.begin( );  
   cout << "The first element of vector is "  
        << *v1_Iter << "." << endl;  
  
   v1_rIter = v1.crbegin( );  
   cout << "The first element of the reversed vector is "  
        << *v1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element of vector is 1.  
The first element of the reversed vector is 2.  
```  
  
##  <a name="crend"></a>Vector::crend  
 Ters vektör son öğesi başarılı konumu adresleri const bir yineleyici döndürür.  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir const ters son öğesi bir ters başarılı konumu adresleri rasgele erişim yineleyici [vektör](../standard-library/vector-class.md) (ilk öğe unreversed öncesinde konumu `vector`).  
  
### <a name="remarks"></a>Açıklamalar  
 `crend`kullanılan bir ters ile `vector` gibi [vector::cend](#cend) ile kullanılan bir `vector`.  
  
 Dönüş değeri ile `crend` (uygun indirildiği), `vector` nesnesi değiştirilemez.  
  
 `crend`Ters yineleyici sonuna olup ulaştı için test etmek için kullanılan kendi `vector`.  
  
 Tarafından döndürülen değer `crend` değil başvuru yapıldı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_crend.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::const_reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )  
      cout << *v1_rIter << endl;  
}  
```  
  
```Output  
2  
1  
```  
  
##  <a name="data"></a>Vector::Data  
 Vektör ilk öğe için bir işaretçi döndürür.  
  
```  
const_pointer data() const;

 
pointer data();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk öğe için bir işaretçi [vektör](../standard-library/vector-class.md) ya da boş bir başarılı konuma `vector`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_data.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    vector<int> c1;  
    vector<int>::pointer c1 ptr;  
    vector<int>::const_pointer c1_cPtr;  
  
    c1.push_back(1);  
    c1.push_back(2);  
  
    cout << "The vector c1 contains elements:";  
    c1_cPtr = c1.data();  
    for (size_t n = c1.size(); 0 < n; --n, c1_cPtr++)  
    {  
        cout << " " << *c1_cPtr;  
    }  
    cout << endl;  
  
    cout << "The vector c1 now contains elements:";  
    c1 ptr = c1.data();  
 *c1 ptr = 20;  
    for (size_t n = c1.size(); 0 < n; --n, c1 ptr++)  
    {  
        cout << " " << *c1 ptr;  
    }  
    cout << endl;  
}  
```  
  
```Output  
The vector c1 contains elements: 1 2  
The vector c1 now contains elements: 20 2  
```  
  
##  <a name="difference_type"></a>Vector::difference_type  
 Aynı vektör içinde öğelerin başvurmak iki yineleyiciler arasındaki farkı sağlayan türü.  
  
```  
typedef typename Allocator::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 A `difference_type` bir öğe için bir işaretçi adresini içerdiğinden de öğelerin iki işaretçileri arasında bir sayı olarak açıklanabilir.  
  
 Bir [yineleyici](#iterator) vektör bir öğesine erişmek için daha yaygın olarak kullanılır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <vector>  
#include <algorithm>  
  
int main( )  
{  
   using namespace std;  
  
   vector <int> c1;  
   vector <int>::iterator c1_Iter, c2_Iter;  
  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 10 );  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
  
   c1_Iter = c1.begin( );  
   c2_Iter = c1.end( );  
  
   vector <int>::difference_type   df_typ1, df_typ2, df_typ3;  
  
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
  
##  <a name="emplace"></a>Vector::emplace  
 Belirtilen konumda vektör içine yerinde oluşturulan bir öğe ekler.  
  
```  
iterator emplace(
    const_iterator _Where,  
    Type&& val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`_Where`|Konumda [vektör](../standard-library/vector-class.md) burada ilk öğesine eklenir.|  
|`val`|İçine eklenen öğenin değerini `vector`.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Burada yeni öğe eklenir içine konumuna işaret eden bir yineleyici işlevi döndürür `vector`.  
  
### <a name="remarks"></a>Açıklamalar  
 Herhangi bir ekleme işlemi pahalı, bkz: [vector sınıfı](../standard-library/vector-class.md) bir irdelemesi `vector` performans.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_emplace.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
// initialize a vector of vectors by moving v1  
   vector < vector <int> > vv1;  
  
   vv1.emplace( vv1.begin(), move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      {  
      cout << "vv1[0] =";  
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )  
         cout << " " << *Iter;  
      cout << endl;  
      }  
}  
```  
  
```Output  
v1 = 10 20 30  
vv1[0] = 10 20 30  
```  
  
##  <a name="emplace_back"></a>Vector::emplace_back  
 Vektör sonuna yerinde oluşturulan bir öğe ekler.  
  
```  
template <class... Types>  
void emplace_back(Types&&... _Args);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`_Args`|Oluşturucu bağımsız değişkenleri. İşlevi çağırmak için hangi Oluşturucusu aşırı sağlanan bağımsız değişkenler temel oluşturur.|  
  
### <a name="example"></a>Örnek  
  
```cpp  
#include <vector>  
struct obj  
{  
   obj(int, double) {}  
};  
  
int main()  
{  
   std::vector<obj> v;  
   v.emplace_back(1, 3.14); // obj in created in place in the vector  
}  
  
```  
  
##  <a name="empty"></a>Vector::empty  
 Vektör boşsa, testleri.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** vektör boşsa; **false** vektör boş değilse.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_empty.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
  
   if ( v1.empty( ) )  
      cout << "The vector is empty." << endl;  
   else  
      cout << "The vector is not empty." << endl;  
}  
```  
  
```Output  
The vector is not empty.  
```  
  
##  <a name="end"></a>Vector::End  
 past-the-end yineleyici döndürür.  
  
```  
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçmiş--end yineleyici vektörü için. Vektör boşsa, `vector::end() == vector::begin()`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa dönüş değerini **son** türündeki bir değişkene atanır `const_iterator`, vektör nesnesi değiştirilemez. Varsa dönüş değerini **son** türündeki bir değişkene atanır **yineleyici**, vektör nesnesi değiştirilebilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_end.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
   vector <int>::iterator v1_Iter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   for ( v1_Iter = v1.begin( ) ; v1_Iter != v1.end( ) ; v1_Iter++ )  
      cout << *v1_Iter << endl;  
}  
```  
  
```Output  
1  
2  
```  
  
##  <a name="erase"></a>Vector::ERASE  
 Bir öğenin veya öğe aralığını belirtilen konumlardan vektör kaldırır.  
  
```  
iterator erase(
    const_iterator _Where);

iterator erase(
    const_iterator first,  
    const_iterator last);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`_Where`|Öğesinden kaldırılacak öğe konumu.|  
|`first`|İlk öğenin konumunu öğesinden kaldırıldı.|  
|`last`|Konum yalnızca son öğenin ötesinde öğesinden kaldırıldı.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaldırılan herhangi bir öğenin dışında kalan ilk öğe atayan bir yineleyici veya böyle bir öğe varsa vektör sonuna bir işaretçi.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_erase.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
   v1.push_back( 40 );  
   v1.push_back( 50 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   v1.erase( v1.begin( ) );  
   cout << "v1 =";  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   v1.erase( v1.begin( ) + 1, v1.begin( ) + 3 );  
   cout << "v1 =";  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
}  
```  
  
```Output  
v1 = 10 20 30 40 50  
v1 = 20 30 40 50  
v1 = 20 50  
```  
  
##  <a name="front"></a>Vector::Front  
 Bir vektör ilk öğe için bir başvuru döndürür.  
  
```  
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Vektör nesnesi ilk öğe başvuru. Vektör boşsa, dönüş tanımlanmamıştır.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa dönüş değerini `front` atanmış bir `const_reference`, vektör nesnesi değiştirilemez. Varsa dönüş değerini `front` atanmış bir **başvuru**, vektör nesnesi değiştirilebilir.  
  
 Kullanarak derlendiğinde [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) bir öğe boş bir vektör erişmeye 1 veya 2 olarak tanımlanan, bir çalışma zamanı hatası oluşur.  Bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md) daha fazla bilgi için.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_front.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 11 );  
  
   int& i = v1.front( );  
   const int& ii = v1.front( );  
  
   cout << "The first integer of v1 is "<< i << endl;  
   // by incrementing i, we move the the front reference to the second element  
   i++;  
   cout << "Now, the first integer of v1 is "<< i << endl;  
}  
```  
  
##  <a name="get_allocator"></a>Vector::get_allocator  
 Vektör oluşturmak için kullanılan ayırıcısı nesnesinin bir kopyasını döndürür.  
  
```  
Allocator get_allocator() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Vektör tarafından kullanılan ayırıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Allocators vector sınıfı için sınıf depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan allocators çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak ileri düzeyde C++ bir konudur.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_get_allocator.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // The following lines declare objects that use the default allocator.  
   vector<int> v1;  
   vector<int, allocator<int> > v2 = vector<int, allocator<int> >(allocator<int>( )) ;  
  
   // v3 will use the same allocator class as v1  
   vector <int> v3( v1.get_allocator( ) );  
  
   vector<int>::allocator_type xvec = v3.get_allocator( );  
   // You can now call functions on the allocator class used by vec  
}  
```  
  
##  <a name="insert"></a>Vector::insert  
 Bir öğenin veya öğe sayısı veya bir dizi öğeleri belirtilen bir konumda vektör ekler.  
  
```  
iterator insert(
    const_iterator _Where,  
    const Type& val);

iterator insert(
    const_iterator _Where,  
    Type&& val);

void insert(
    const_iterator _Where,  
    size_type count,  
    const Type& val);

template <class InputIterator>  
void insert(
    const_iterator _Where,  
    InputIterator first,  
    InputIterator last);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`_Where`|Burada ilk öğe eklenen konumu vektörü.|  
|`val`|Vektör eklenen öğesinin değeri.|  
|`count`|Vektör eklenen öğelerin sayısı.|  
|`first`|Kopyalanacak öğe aralığını ilk öğe konumu.|  
|`last`|Kopyalanacak öğeleri aralık ötesinde ilk öğe konumu.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk iki `insert` işlevler yeni öğe vektör eklenir burada konumuna işaret eden bir yineleyici döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir önkoşulu olarak `first` ve `last` yineleyiciler vektör içine olmamalıdır veya tanımlanmayan bir davranıştır. Herhangi bir ekleme işlemi pahalı, bkz: [vector sınıfı](../standard-library/vector-class.md) bir irdelemesi `vector` performans.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_insert.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   v1.insert( v1.begin( ) + 1, 40 );  
   cout << "v1 =";  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
   v1.insert( v1.begin( ) + 2, 4, 50 );  
  
   cout << "v1 =";  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   v1.insert( v1.begin( )+1, v1.begin( )+2, v1.begin( )+4 );  
   cout << "v1 =";  
   for (Iter = v1.begin( ); Iter != v1.end( ); Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
// initialize a vector of vectors by moving v1  
   vector < vector <int> > vv1;  
  
   vv1.insert( vv1.begin(), move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      {  
      vector < vector <int> >::iterator Iter;  
      cout << "vv1[0] =";  
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )  
         cout << " " << *Iter;  
      cout << endl;  
      }  
}  
```  
  
```Output  
v1 = 10 20 30  
v1 = 10 40 20 30  
v1 = 10 40 50 50 50 50 20 30  
v1 = 10 50 50 40 50 50 50 50 20 30  
vv1[0] = 10 50 50 40 50 50 50 50 20 30  
```  
  
##  <a name="iterator"></a>Vector::iterator  
 Rasgele erişim yineleyici sağlayan bir türünü okumak veya herhangi bir vektör öğesinde değiştirin.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür **yineleyici** bir öğenin değerini değiştirmek için kullanılabilir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [başlamak](#begin).  
  
##  <a name="max_size"></a>Vector::max_size  
 Vektör maksimum uzunluğunu döndürür.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Olası uzunluk vektörü.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_max_size.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::size_type i;  
  
   i = v1.max_size( );     
   cout << "The maximum possible length of the vector is " << i << "." << endl;  
}  
```  
  
##  <a name="op_at"></a>Vector::operator]  
 Vektör öğesine belirtilen konumda bir başvuru döndürür.  
  
```  
reference operator[](size_type Pos);

const_reference operator[](size_type Pos) const;
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Pos`|Vektör öğesinin konumu.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen konum kapsayıcısının boyutuna eşit veya ondan daha büyük ise, sonuç tanımsızdır.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa dönüş değerini `operator[]` atanmış bir `const_reference`, vektör nesnesi değiştirilemez. Varsa dönüş değerini `operator[]` atanmış bir başvuru vektör nesnesi değiştirilebilir.  
  
 Kullanarak derlendiğinde [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) vektör sınırları dışındaki bir öğe erişmeye 1 veya 2 olarak tanımlanan, bir çalışma zamanı hatası oluşur.  Bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md) daha fazla bilgi için.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_op_ref.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
  
   int& i = v1[1];  
   cout << "The second integer of v1 is " << i << endl;  
}  
```  
  
##  <a name="op_eq"></a>Vector::operator =  
 Vektör öğelerini başka bir vektör bir kopyası ile değiştirir.  
  
```  
vector& operator=(const vector& right);

vector& operator=(vector&& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`right`|[Vektör](../standard-library/vector-class.md) içine kopyalanmasını `vector`.|  
  
### <a name="remarks"></a>Açıklamalar  
 Var olan öğeleri silindikten sonra bir `vector`, `operator=` kopyalar ya da içeriğini taşır `right` içine `vector`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_operator_as.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector<int> v1, v2, v3;  
   vector<int>::iterator iter;  
  
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
   v2 = move(v1);  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
}  
```  
  
##  <a name="pointer"></a>Vector::pointer  
 Vektör bir öğesine bir işaretçi sağlayan türü.  
  
```  
typedef typename Allocator::pointer pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür **işaretçi** bir öğenin değerini değiştirmek için kullanılabilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_pointer.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector<int> v;  
   v.push_back( 11 );  
   v.push_back( 22 );  
  
   vector<int>::pointer ptr = &v[0];  
   cout << *ptr << endl;  
   ptr++;  
   cout << *ptr << endl;  
 *ptr = 44;  
   cout << *ptr << endl;  
}  
```  
  
```Output  
11  
22  
44  
```  
  
##  <a name="pop_back"></a>Vector::pop_back  
 Vektör ucundaki öğe siler.  
  
```  
void pop_back();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kod örneği için bkz: [vektör:: push_back()](#push_back).  
  
##  <a name="push_back"></a>Vector::push_back  
 Bir öğeyi vektör sonuna ekler.  
  
```  
void push_back(const T& Val);

 
void push_back(T&& Val);
```  
  
### <a name="parameters"></a>Parametreler  
 `Val`  
 Vektör sonuna eklenen öğesine atanacak değer.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <iostream>  
  
using namespace std;  
  
template <typename T> void print_elem(const T& t) {  
    cout << "(" << t << ") ";  
}  
  
template <typename T> void print_collection(const T& t) {  
    cout << "  " << t.size() << " elements: ";  
  
    for (const auto& p : t) {  
        print_elem(p);  
    }  
    cout << endl;  
}  
  
int main()  
{  
    vector<int> v;  
    for (int i = 0; i < 10; ++i) {  
        v.push_back(10 + i);  
    }  
  
    cout << "vector data: " << endl;  
    print_collection(v);  
  
    // pop_back() until it's empty, printing the last element as we go  
    while (v.begin() != v.end()) {   
        cout << "v.back(): "; print_elem(v.back()); cout << endl;  
        v.pop_back();  
    }  
}  
```  
  
##  <a name="rbegin"></a>Vector::rbegin  
 Yineleyici ters vektör ilk öğe döndürür.  
  
```  
reverse_iterator rbegin();
const_reverse_iterator rbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ters vektör ilk öğe adresleme veya ne adresleme ters bir rastgele erişim yineleyici unreversed vektör son öğesi eklenmiştir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa dönüş değerini `rbegin` atanmış bir `const_reverse_iterator`, vektör nesnesi değiştirilemez. Varsa dönüş değerini `rbegin` atanmış bir `reverse_iterator`, vektör nesnesi değiştirilebilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_rbegin.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator v1_Iter;  
   vector <int>::reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   v1_Iter = v1.begin( );  
   cout << "The first element of vector is "  
        << *v1_Iter << "." << endl;  
  
   v1_rIter = v1.rbegin( );  
   cout << "The first element of the reversed vector is "  
        << *v1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element of vector is 1.  
The first element of the reversed vector is 2.  
```  
  
##  <a name="reference"></a>Vector::Reference  
 Bir vektör depolanan bir öğe için bir başvuru sağlar türü.  
  
```  
typedef typename Allocator::reference reference;  
```  
  
### <a name="example"></a>Örnek  
  Bkz: [adresindeki](#at) nasıl kullanılacağına ilişkin bir örnek **başvuru** vector sınıfında.  
  
##  <a name="rend"></a>Vector::rend  
 Ters vektör son öğesi başarılı konumu adresleri yineleyici döndürür.  
  
```  
const_reverse_iterator rend() const;
reverse_iterator rend();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ters vektör (ilk öğe unreversed vektörü öncesinde konum) son öğesi başarılı konumu adresleri ters rasgele erişim yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 `rend`Ters vektörü ile kullanılan gibi [son](#end) vektörü ile kullanılır.  
  
 Varsa dönüş değerini `rend` atanan bir `const_reverse_iterator`, sonra da vektör nesnesi değiştirilemez. Varsa dönüş değerini `rend` atandığı bir `reverse_iterator`, sonra vektör nesnesi değiştirilebilir.  
  
 `rend`Ters yineleyici kendi vektör sonuna olup ulaştı için test etmek için kullanılabilir.  
  
 Tarafından döndürülen değer `rend` değil başvuru yapıldı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_rend.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )  
      cout << *v1_rIter << endl;  
}  
```  
  
```Output  
2  
1  
```  
  
##  <a name="reserve"></a>Vector::reserve  
 Depolama alanı gerekirse ayrılırken bir vektör nesnesi için minimum uzunluğu saklı tutar.  
  
```  
void reserve(size_type count);
```  
  
### <a name="parameters"></a>Parametreler  
 `count`  
 Vektör için ayrılacak depolama en az uzunluğu.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_reserve.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   //vector <int>::iterator Iter;  
  
   v1.push_back( 1 );  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
   v1.reserve( 20 );  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
}  
```  
  
```Output  
Current capacity of v1 = 1  
Current capacity of v1 = 20  
```  
  
##  <a name="resize"></a>Vector::Resize  
 Yeni bir vektör boyutu belirtir.  
  
```  
void resize(size_type Newsize);
void resize(size_type Newsize, Type Val);
```  
  
### <a name="parameters"></a>Parametreler  
 `Newsize`  
 Vektör yeni boyutu.  
  
 `Val`  
 Yeni boyutu daha büyükse vektörüne eklenen yeni öğeleri başlatma değeri, özgün boyutu. Değer belirtilmezse, yeni nesneler kendi varsayılan bir oluşturucu kullanın.  
  
### <a name="remarks"></a>Açıklamalar  
 Kapsayıcının boyutu istenen boyuttan daha az ise `Newsize`, istenen boyuta ulaşana kadar öğeleri vector öğesine eklenir. Kapsayıcının boyutu istenen boyutundan daha büyükse kapsayıcı boyuta ulaşana kadar kapsayıcı sonuna kadar yakın öğeleri silinir `Newsize`. Kapsayıcı mevcut boyutunu istenen boyutu ile aynı olduğunda, hiçbir işlem yapılmadı.  
  
 [boyutu](#size) vektör geçerli boyutunu gösterir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vectorsizing.cpp  
// compile with: /EHsc /W4  
// Illustrates vector::reserve, vector::max_size,  
// vector::resize, vector::resize, and vector::capacity.  
//  
// Functions:  
//  
//    vector::max_size - Returns maximum number of elements vector could  
//                       hold.  
//  
//    vector::capacity - Returns number of elements for which memory has  
//                       been allocated.  
//  
//    vector::size - Returns number of elements in the vector.  
//  
//    vector::resize - Reallocates memory for vector, preserves its  
//                     contents if new size is larger than existing size.  
//  
//    vector::reserve - Allocates elements for vector to ensure a minimum  
//                      size, preserving its contents if the new size is  
//                      larger than existing size.  
//  
//    vector::push_back - Appends (inserts) an element to the end of a  
//                        vector, allocating memory for it if necessary.  
//  
//////////////////////////////////////////////////////////////////////  
  
// The debugger cannot handle symbols more than 255 characters long.  
// The C++ Standard Library often creates symbols longer than that.  
// The warning can be disabled:  
//#pragma warning(disable:4786)  
  
#include <iostream>  
#include <vector>  
#include <string>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
    cout << endl;  
}  
  
void printvstats(const vector<int>& v) {  
    cout << "   the vector's size is: " << v.size() << endl;  
    cout << "   the vector's capacity is: " << v.capacity() << endl;  
    cout << "   the vector's maximum size is: " << v.max_size() << endl;  
}  
  
int main()  
{  
    // declare a vector that begins with 0 elements.  
    vector<int> v;  
  
    // Show statistics about vector.  
    cout << endl << "After declaring an empty vector:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    // Add one element to the end of the vector.  
    v.push_back(-1);  
    cout << endl << "After adding an element:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    for (int i = 1; i < 10; ++i) {  
        v.push_back(i);  
    }  
    cout << endl << "After adding 10 elements:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    v.resize(6);  
    cout << endl << "After resizing to 6 elements without an initialization value:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    v.resize(9, 999);  
    cout << endl << "After resizing to 9 elements with an initialization value of 999:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    v.resize(12);  
    cout << endl << "After resizing to 12 elements without an initialization value:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    // Ensure there's room for at least 1000 elements.  
    v.reserve(1000);  
    cout << endl << "After vector::reserve(1000):" << endl;  
    printvstats(v);  
  
    // Ensure there's room for at least 2000 elements.  
    v.resize(2000);  
    cout << endl << "After vector::resize(2000):" << endl;  
    printvstats(v);  
}  
```  
  
##  <a name="reverse_iterator"></a>Vector::reverse_iterator  
 Rasgele erişim yineleyici sağlayan bir tür okumak veya ters vektörü herhangi bir öğeyi değiştirin.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `reverse_iterator` ters vektör yinelemek için kullanılır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [rbegin](#rbegin).  
  
##  <a name="shrink_to_fit"></a>Vector::shrink_to_fit  
 Fazlalık kapasite atar.  
  
```  
void shrink_to_fit();
```  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_shrink_to_fit.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   //vector <int>::iterator Iter;  
  
   v1.push_back( 1 );  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
   v1.reserve( 20 );  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
   v1.shrink_to_fit();  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
}  
```  
  
```Output  
Current capacity of v1 = 1  
Current capacity of v1 = 20  
Current capacity of v1 = 1  
```  
  
##  <a name="size"></a>Vector::size  
 Vektör öğe sayısını döndürür.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Vektör geçerli uzunluğu.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_size.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::size_type i;  
  
   v1.push_back( 1 );  
   i = v1.size( );  
   cout << "Vector length is " << i << "." << endl;  
  
   v1.push_back( 2 );  
   i = v1.size( );  
   cout << "Vector length is now " << i << "." << endl;  
}  
```  
  
```Output  
Vector length is 1.  
Vector length is now 2.  
```  
  
##  <a name="size_type"></a>Vector::size_type  
 Vektör öğelerinde sayar türü.  
  
```  
typedef typename Allocator::size_type size_type;  
```  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [kapasite](#capacity).  
  
##  <a name="swap"></a>Vector::Swap  
 İki vektör öğelerini değiş tokuş eder.  
  
```  
void swap(
    vector<Type, Allocator>& right);

friend void swap(
    vector<Type, Allocator>& left,  
    vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Öğeleri takas için sağlama vektör veya öğeleri olan vektör olanlar değiştirilebilmesi için vektör `left`.  
  
 `left`  
 Öğeleri olan vektör olanlar değiştirilebilmesi için vektör `right`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_swap.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1, v2;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   v1.push_back( 3 );  
  
   v2.push_back( 10 );  
   v2.push_back( 20 );  
  
   cout << "The number of elements in v1 = " << v1.size( ) << endl;  
   cout << "The number of elements in v2 = " << v2.size( ) << endl;  
   cout << endl;  
  
   v1.swap( v2 );  
  
   cout << "The number of elements in v1 = " << v1.size( ) << endl;  
   cout << "The number of elements in v2 = " << v2.size( ) << endl;  
}  
```  
  
```Output  
The number of elements in v1 = 3  
The number of elements in v2 = 2  
  
The number of elements in v1 = 2  
The number of elements in v2 = 3  
```  
  
##  <a name="value_type"></a>Vector::value_type  
 Vektör içinde depolanan veri türünü temsil eden tür.  
  
```  
typedef typename Allocator::value_type value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `value_type`Şablon parametresi için bir eş anlamlı olduğundan **türü**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_value_type.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector<int>::value_type AnInt;  
   AnInt = 44;  
   cout << AnInt << endl;  
}  
```  
  
```Output  
44  
```  
  
##  <a name="vector"></a>Vector::Vector  
 Belirli bir boyuta veya belirli bir değerin veya belirli bir ayırıcı veya tüm kopyasını veya başka bir vektör bir parçası olarak öğelerle vektör oluşturur.  
  
```  
vector();
explicit vector(const Allocator& Al);
explicit vector(size_type Count);
vector(size_type Count, const Type& Val);
vector(size_type Count, const Type& Val, const Allocator& Al);

vector(const vector& Right);
vector(vector&& Right);
vector(initializer_list<Type> IList, const _Allocator& Al);

template <class InputIterator>  
vector(InputIterator First, InputIterator Last);
template <class InputIterator>  
vector(InputIterator First, InputIterator Last, const Allocator& Al);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Al`|Bu nesneyle kullanılacak kaynak ayırıcı sınıfı. [get_allocator](#get_allocator) allocator sınıfı nesnesi döndürür.|  
|`Count`|Oluşturulan vektör öğe sayısı.|  
|`Val`|Oluşturulan vektör öğelerinde değeri.|  
|`Right`|Oluşturulan vektör kopyasını olmasını olduğu vektörü.|  
|`First`|Kopyalanacak öğe aralığını ilk öğe konumu.|  
|`Last`|Kopyalanacak öğeleri aralık ötesinde ilk öğe konumu.|  
|`IList`|Kopyalamak için elmeents içeren initializer_list.|  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm oluşturucular ayırıcısı nesneyi depolamak ( `Al`) ve vektör başlatma.  
  
 İlk iki oluşturucular boş bir ilk vektörü belirtin. İkinci açıkça ayırıcısı türünü belirtir ( `Al`) kullanılacak.  
  
 Belirtilen sayının yineleme üçüncü Oluşturucusu belirtir ( `Count`) sınıfı için varsayılan değer öğelerinin `Type`.  
  
 Dördüncü ve beşinci oluşturucular yineleme sayısını belirtin ( `Count`) değerinin öğeleri `Val`.  
  
 Altıncı Oluşturucusu vektör kopyasını belirtir `Right`.  
  
 Vektör yedinci Oluşturucusu taşır `Right`.  
  
 Sekizinci Oluşturucusu bir initializer_list öğeleri belirlemek için kullanır.  
  
 Aralığın dokuzuncu ve onuncu oluşturucuları kopyalama [ `First`, `Last`) vektör biri.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// vector_ctor.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    vector <int>::iterator v1_Iter, v2_Iter, v3_Iter, v4_Iter, v5_Iter, v6_Iter;  
  
    // Create an empty vector v0  
    vector <int> v0;  
  
    // Create a vector v1 with 3 elements of default value 0  
    vector <int> v1(3);  
  
    // Create a vector v2 with 5 elements of value 2  
    vector <int> v2(5, 2);  
  
    // Create a vector v3 with 3 elements of value 1 and with the allocator   
    // of vector v2  
    vector <int> v3(3, 1, v2.get_allocator());  
  
    // Create a copy, vector v4, of vector v2  
    vector <int> v4(v2);  
  
    // Create a new temporary vector for demonstrating copying ranges  
    vector <int> v5(5);  
    for (auto i : v5) {  
        v5[i] = i;  
    }  
  
    // Create a vector v6 by copying the range v5[ first,  last)  
    vector <int> v6(v5.begin() + 1, v5.begin() + 3);  
  
    cout << "v1 =";  
    for (auto& v : v1){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    cout << "v2 =";  
    for (auto& v : v2){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    cout << "v3 =";  
    for (auto& v : v3){  
        cout << " " << v;  
    }  
    cout << endl;  
    cout << "v4 =";  
    for (auto& v : v4){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    cout << "v5 =";  
    for (auto& v : v5){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    cout << "v6 =";  
    for (auto& v : v6){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    // Move vector v2 to vector v7  
    vector <int> v7(move(v2));  
    vector <int>::iterator v7_Iter;  
  
    cout << "v7 =";  
    for (auto& v : v7){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    vector<int> v8{ { 1, 2, 3, 4 } };  
    for (auto& v : v8){  
        cout << " " << v ;  
    }  
    cout << endl;  
}  
  
```  
  
```Output  
v1 = 0 0 0v2 = 2 2 2 2 2v3 = 1 1 1v4 = 2 2 2 2 2v5 = 0 1 2 3 4v6 = 1 2v7 = 2 2 2 2 21 2 3 4  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

