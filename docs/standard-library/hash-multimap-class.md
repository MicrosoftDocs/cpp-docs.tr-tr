---
title: "hash_multimap sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hash_map/stdext::hash_multimap
- hash_map/stdext::hash_multimap::allocator_type
- hash_map/stdext::hash_multimap::const_iterator
- hash_map/stdext::hash_multimap::const_pointer
- hash_map/stdext::hash_multimap::const_reference
- hash_map/stdext::hash_multimap::const_reverse_iterator
- hash_map/stdext::hash_multimap::difference_type
- hash_map/stdext::hash_multimap::iterator
- hash_map/stdext::hash_multimap::key_compare
- hash_map/stdext::hash_multimap::key_type
- hash_map/stdext::hash_multimap::mapped_type
- hash_map/stdext::hash_multimap::pointer
- hash_map/stdext::hash_multimap::reference
- hash_map/stdext::hash_multimap::reverse_iterator
- hash_map/stdext::hash_multimap::size_type
- hash_map/stdext::hash_multimap::value_type
- hash_map/stdext::hash_multimap::begin
- hash_map/stdext::hash_multimap::cbegin
- hash_map/stdext::hash_multimap::cend
- hash_map/stdext::hash_multimap::clear
- hash_map/stdext::hash_multimap::count
- hash_map/stdext::hash_multimap::crbegin
- hash_map/stdext::hash_multimap::crend
- hash_map/stdext::hash_multimap::emplace
- hash_map/stdext::hash_multimap::emplace_hint
- hash_map/stdext::hash_multimap::empty
- hash_map/stdext::hash_multimap::end
- hash_map/stdext::hash_multimap::equal_range
- hash_map/stdext::hash_multimap::erase
- hash_map/stdext::hash_multimap::find
- hash_map/stdext::hash_multimap::get_allocator
- hash_map/stdext::hash_multimap::insert
- hash_map/stdext::hash_multimap::key_comp
- hash_map/stdext::hash_multimap::lower_bound
- hash_map/stdext::hash_multimap::max_size
- hash_map/stdext::hash_multimap::rbegin
- hash_map/stdext::hash_multimap::rend
- hash_map/stdext::hash_multimap::size
- hash_map/stdext::hash_multimap::swap
- hash_map/stdext::hash_multimap::upper_bound
- hash_map/stdext::hash_multimap::value_comp
dev_langs: C++
helpviewer_keywords:
- stdext::hash_multimap
- stdext::hash_multimap::allocator_type
- stdext::hash_multimap::const_iterator
- stdext::hash_multimap::const_pointer
- stdext::hash_multimap::const_reference
- stdext::hash_multimap::const_reverse_iterator
- stdext::hash_multimap::difference_type
- stdext::hash_multimap::iterator
- stdext::hash_multimap::key_compare
- stdext::hash_multimap::key_type
- stdext::hash_multimap::mapped_type
- stdext::hash_multimap::pointer
- stdext::hash_multimap::reference
- stdext::hash_multimap::reverse_iterator
- stdext::hash_multimap::size_type
- stdext::hash_multimap::value_type
- stdext::hash_multimap::begin
- stdext::hash_multimap::cbegin
- stdext::hash_multimap::cend
- stdext::hash_multimap::clear
- stdext::hash_multimap::count
- stdext::hash_multimap::crbegin
- stdext::hash_multimap::crend
- stdext::hash_multimap::emplace
- stdext::hash_multimap::emplace_hint
- stdext::hash_multimap::empty
- stdext::hash_multimap::end
- stdext::hash_multimap::equal_range
- stdext::hash_multimap::erase
- stdext::hash_multimap::find
- stdext::hash_multimap::get_allocator
- stdext::hash_multimap::insert
- stdext::hash_multimap::key_comp
- stdext::hash_multimap::lower_bound
- stdext::hash_multimap::max_size
- stdext::hash_multimap::rbegin
- stdext::hash_multimap::rend
- stdext::hash_multimap::size
- stdext::hash_multimap::swap
- stdext::hash_multimap::upper_bound
- stdext::hash_multimap::value_comp
ms.assetid: f41a6db9-67aa-43a3-a3c5-dbfe9ec3ae7d
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1e5c64e90b2e75a7dc0879bbc871892d90d1a02c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultimap-class"></a>hash_multimap Sınıfı
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Kapsayıcı sınıfı hash_multimap C++ Standart Kitaplığı, bir uzantısıdır ve depolama ve her öğenin değeri benzersiz olması gerekmez sıralama anahtarı olan bir çift olduğu bir koleksiyon ve ilişkili veriler bir değer verileri hızlı alınması için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Key,   
    class Type,   
    class Traits=hash_compare <Key, less <Key>>,   
    class Allocator=allocator <pair  <const Key, Type>>>  
class hash_multimap  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Key`  
 Hash_multimap depolanması için anahtar veri türü.  
  
 `Type`  
 Hash_multimap depolanması için öğe veri türü.  
  
 `Traits`  
 Bir sınıfın iki işlev nesneleri içeren türü `Traits` göreli sıralarına ve imzasız tamsayılar öğelerine koşul eşlemesi anahtar değerlerinin bir birli olan karma işlevi belirlemek için sıralama anahtarları olarak iki öğenin değerleri karşılaştırmak mümkün olan tür **size_t**. Bu bağımsız değişken isteğe bağlıdır ve `hash_compare<Key, less<Key>>` varsayılan değerdir.  
  
 `Allocator`  
 Hash_multimap's ayırma ve bellek ayırmayı kaldırma hakkında ayrıntılar yalıtan saklı ayırıcısı nesneyi temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `allocator<pair <const Key, Type>>`.  
  
## <a name="remarks"></a>Açıklamalar  
 Hash_multimap aşağıdaki gibidir:  
  
-   İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı.  
  
-   Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.  
  
-   Karma, öğelerin anahtar değerleri için uygulanan bir karma işlevine değere göre demet içine öğeleri gruplandırıldığından.  
  
-   Öğelerinin benzersiz anahtarlara ihtiyacı olmaması için çokludur, böylece bir anahtar değer onunla ilişkili çok sayıda öğe verisi değerine sahip olabilir.  
  
-   Bir çifti ilişkilendirilebilir kapsayıcı öğesi değerlerini kendi anahtar değerlerini birbirinden farklı olduğundan.  
  
-   Bir şablon sınıfıdır, çünkü sağladığı işlevsellik geneldir ve böylece öğeler veya anahtarlar olarak kapsanan belirli veri türünden bağımsızdır. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.  
  
 Sıralama üzerinden karma ana avantajı, verimliliği olmasıdır; başarılı bir karma eklemeler, silmeler gerçekleştirir ve sabit ortalama süresi bir saat ile karşılaştırıldığında teknikleri sıralamak için kapsayıcısında öğe sayısını logaritmasını orantılı bulur. Bir hash_multimap bir öğe değerini ancak değil ilişkili anahtar değerini, doğrudan değiştirilebilir. Bunun yerine, eski öğelerle ilişkili anahtar değerleri silinmeli ve eklenen yeni öğelerle ilişkili yeni anahtar değerleri eklenmelidir.  
  
 Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Karma ilişkilendirilebilir kapsayıcıları, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Açıkça işlemlerini destekleyen üye işlevleri, bunları ortalama sabit ve kapsayıcı öğe sayısı bağımlı bir süre içinde gerçekleştirdiğiniz bir iyi tasarlanmış karma işlevi ile kullanıldığında verimlidir. İyi tasarlanmış karma işlevi karma değerleri Tekdüzen dağıtımını oluşturur ve çakışma, burada bir çakışma DISTINCT anahtar değerleri aynı karma değer eşlenir ortaya söylenir sayısını en aza indirir. En kötü durumda, en kötü olası karma işlevi ile işlemlerinin sayısı (doğrusal saati) dizisindeki öğelerin sayısı orantılıdır.  
  
 Uygulama tarafından değerleri kendi anahtarlarla ilişkilendirme koşulları sağlandığında hash_multimap tercih ilişkilendirilebilir kapsayıcı olmalıdır. Bu tür bir yapı için model, mesela açıklamalar sağlayan dize değerleriyle ilişkili anahtar sözcüklerin sıralı bir listesidir, burada sözcükler her zaman benzersiz olarak tanımlanmamıştır. Böylece anahtarları benzersiz bunun yerine, anahtar sözcükleri benzersiz şekilde tanımlanan varsa, bir hash_map tercih kapsayıcı olacaktır. Diğer taraftan, yalnızca sözcükleri listesini depolanmakta varsa, bir hash_set doğru kapsayıcı olacaktır. Birden çok tekrarı sözcükleri izin verilmekteydi, bir hash_multiset uygun bir kapsayıcı yapısı olacaktır.  
  
 Hash_multimap denetimleri depolanan karma çağırarak dizisi siparişleri `Traits` nesne türü [value_compare](../standard-library/value-compare-class.md). Üye işlevini çağırarak bu saklı nesne erişilebileceği [key_comp](../standard-library/hash-map-class.md#key_comp). Bu tür bir işlev nesnesi sınıfın bir nesnesi olarak aynı şekilde davranır gerekir [hash_compare](../standard-library/hash-compare-class.md)`<Key, less<Key>>`. Özellikle, tüm değerler için `Key` türü `Key`, çağrı `Traits (Key)` türü değerleri dağıtımını verir `size_t`.  
  
 Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, bir eşdeğer olmayan öğeler arasında sıralamada sonuçlanır. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. İkili karşılaştırma f (x, y) iki bağımsız değişken nesnelere sahip bir işlev nesnesidir `x` ve `y` ve dönüş değeri `true` veya `false`. İkili karşılaştırma dönüşsüz, ters ve geçişli ve burada iki nesneleri eşdeğer geçişli ise, sıralama katı bir zayıf olduğu bir hash_multimap üzerinde uygulanan sıralama `x` ve `y` ne zaman eşdeğer olarak tanımlanan her iki f (x y) ve f (y, x) `false`. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.  
  
 Denetlenen sıradaki öğelerin gerçek sırası karma işlevi, sıralama işlevi ve kapsayıcı nesnesinde depolanan karma tablosu boyutunu bağlıdır. Denetlenen sıradaki öğelerin sırasını genel tahmin edilemez şekilde karma tablo geçerli boyutu saptanamaz. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.  
  
 Hash_multimap sınıfı tarafından sağlanan yineleyici sınıf üyesi işlevleri ancak bir çift yönlü yineleyici olan [Ekle](#insert) ve [hash_multimap](#hash_multimap) şablon parametreleri olarak daha zayıf bir giriş gerçekleştirin sürümlerin gerekir Yineleyici, çift yönlü yineleyiciler sınıfı tarafından garanti olandan daha az olan işlevselliği gereksinimleri. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Kendi hash_multimap gereksinimlerinin her yineleyici kavramına sahiptir ve bunlarla çalışmak algoritmaları yineleyici türü tarafından sağlanan gereksinimlerini için kendi varsayımlar sınırlamanız gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu işlevlerin en az bir hash_multimap olur, ancak anlamlı yineleyiciler çeşitli hakkında iletişim kurabilmesi için yeterlidir `[First, Last)` üye işlevleri bağlamında.  
  
   
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[hash_multimap](#hash_multimap)|Belirli bir boyutta veya belirli bir değere öğelerini veya belirli bir liste oluşturur `allocator` veya başka bir kopyasını olarak `hash_multimap`.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|Temsil eden bir tür `allocator` için sınıf `hash_multimap` nesnesi.|  
|[const_iterator](#const_iterator)|Çift yönlü yineleyici bu can sağlayan bir türü okuma bir `const` öğesinde `hash_multimap`.|  
|[const_pointer](#const_pointer)|Bir işaretçi sağlayan bir türü bir `const` öğesinde bir `hash_multimap`.|  
|[const_reference](#const_reference)|Bir başvuru sağlayan bir türü bir `const` öğesi saklanan bir `hash_multimap` okumak ve gerçekleştirmek için `const` işlemleri.|  
|[const_reverse_iterator](#const_reverse_iterator)|Herhangi bir çift yönlü yineleyici bu can sağlayan bir türü okuma `const` öğesinde `hash_multimap`.|  
|[difference_type](#difference_type)|Öğelerinin sayısı temsil etmek için kullanılan bir imzalı tamsayı türü bir `hash_multimap` yineleyiciler tarafından işaret öğeler arasındaki bir aralıkta.|  
|[Yineleyici](#iterator)|Çift yönlü yineleyici sağlayan bir tür okuma veya herhangi bir öğe değiştirme bir `hash_multimap`.|  
|[key_compare](#key_compare)|Göreli içinde iki öğe sırasını belirlemek için iki sıralama anahtarları karşılaştırabilirsiniz bir işlev nesnesi sağlayan bir türü `hash_multimap`.|  
|[key_type](#key_type)|Her öğeye oluşturduğunu sıralama anahtar nesneyi tanımlayan bir tür `hash_multimap`.|  
|[mapped_type](#mapped_type)|İçinde depolanan veri türünü temsil eden bir tür bir `hash_multimap`.|  
|[İşaretçi](#pointer)|Bir öğe için bir işaretçi sağlayan bir türü bir `hash_multimap`.|  
|[başvuru](#reference)|Depolanmış bir öğe için bir başvuru sağlayan bir türü bir `hash_multimap`.|  
|[reverse_iterator](#reverse_iterator)|Çift yönlü yineleyici sağlayan bir tür okuma veya bir öğedeki bir ters değiştirme `hash_multimap`.|  
|[size_type](#size_type)|Öğe sayısı gösterebilir bir işaretsiz tamsayı türü bir `hash_multimap`.|  
|[value_type](#value_type)|İki öğe içindeki göreli sıralarına belirlemek için sıralama anahtarları olarak karşılaştırabilirsiniz bir işlev nesnesi sağlayan bir türü `hash_multimap`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[başlayın](#begin)|İlk öğe adresleme yineleyici döndürür `hash_multimap`.|  
|[cbegin](#cbegin)|İlk öğe adresleme const yineleyici döndürür `hash_multimap`.|  
|[cend](#cend)|Son öğesi başarılı konumu adresleri const bir yineleyici döndüren bir `hash_multimap`.|  
|[Temizle](#clear)|Tüm öğeleri sildiği bir `hash_multimap`.|  
|[sayısı](#count)|Öğelerin sayısını döndürür bir `hash_multimap` parametresi belirtilen bir anahtarı olan anahtar eşleşir.|  
|[crbegin](#crbegin)|İlk öğe bir ters adresleme const yineleyici döndürür `hash_multimap`.|  
|[crend](#crend)|Son öğesi bir ters başarılı konumu adresleri const bir yineleyici döndürür `hash_multimap`.|  
|[emplace](#emplace)|Yerinde oluşturulan bir öğe ekler bir `hash_multimap`.|  
|[emplace_hint](#emplace_hint)|Yerinde oluşturulan bir öğe ekler bir `hash_multimap`, yerleştirme İpucu ile.|  
|[boş](#empty)|Testleri bir `hash_multimap` boş.|  
|[Bitiş](#end)|Son öğesi başarılı konumu adresleri yineleyici döndüren bir `hash_multimap`.|  
|[equal_range](#equal_range)|Son öğesi başarılı konumu adresleri yineleyici döndüren bir `hash_multimap`.|  
|[silme](#erase)|Bir öğenin veya bir dizi öğeleri kaldırır bir `hash_multimap` belirtilen konumlardan|  
|[Bul](#find)|Bir öğedeki konumunu adresleme yineleyici döndüren bir `hash_multimap` , belirtilen anahtar için eşdeğer bir anahtara sahip.|  
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` oluşturmak için kullanılan nesne `hash_multimap`.|  
|[Ekle](#insert)|Bir öğenin veya bir dizi elemanlara ekler `hash_multimap` belirtilen konumda.|  
|[key_comp](#key_comp)|Sipariş anahtarlarında kullanılacak karşılaştırma nesnesinin bir kopyasını alır bir `hash_multimap`.|  
|[lower_bound](#lower_bound)|Yineleyici ilk öğe döndürür bir `hash_multimap` bir anahtarla değerine eşit veya bundan büyük, belirtilen anahtar.|  
|[max_size](#max_size)|En büyük uzunluğunu döndürür `hash_multimap`.|  
|[rbegin](#rbegin)|İlk öğe bir ters adresleme yineleyici döndürür `hash_multimap`.|  
|[rend](#rend)|Son öğesi bir ters başarılı konumu adresleri yineleyici döndürür `hash_multimap`.|  
|[boyutu](#size)|Yeni bir boyutu belirtir bir `hash_multimap`.|  
|[değiştirme](#swap)|İki öğelerini alış verişleri `hash_multimap`s.|  
|[upper_bound](#upper_bound)|Yineleyici ilk öğe döndürür bir `hash_multimap` bir anahtarla değeri, belirtilen anahtar daha büyük.|  
|[value_comp](#value_comp)|Sipariş öğesi değerleri için kullanılan karşılaştırma nesnesinin bir kopyasını alır bir `hash_multimap`.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[hash_multimap::operator =](#op_eq)|Öğeleri değiştirir bir `hash_multimap` başka bir kopyasına sahip `hash_multimap`.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<hash_map >  
  
 **Namespace:** stdext  
  
##  <a name="allocator_type"></a>hash_multimap::allocator_type  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Allocator sınıfı hash_multimap nesnesinin temsil eden tür.  
  
```  
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `allocator_type`Şablon parametresi için bir eş anlamlı olduğundan `Allocator`.  
  
 Daha fazla bilgi için `Allocator`, Açıklamalar bölümüne bakın [hash_multimap sınıfı](../standard-library/hash-multimap-class.md) konu.  
  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [get_allocator](#get_allocator) kullanarak bir örnek için `allocator_type`.  
  
##  <a name="begin"></a>hash_multimap::Begin  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Hash_multimap ilk öğe adresleme yineleyici döndürür.  
  
```  
const_iterator begin() const;

iterator begin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hash_multimap ya da boş bir hash_multimap başarılı konumu ilk öğe adresleme çift yönlü yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa dönüş değerini **başlamak** atanmış bir `const_iterator`, hash_multimap nesnesindeki öğelerin değiştirilemez. Varsa dönüş değerini **başlamak** atanmış bir **yineleyici**, hash_multimap nesnesindeki öğelerin değiştirilebilir.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_begin.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1;  
  
   hash_multimap <int, int> :: iterator hm1_Iter;  
   hash_multimap <int, int> :: const_iterator hm1_cIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 0, 0 ) );  
   hm1.insert ( Int_Pair ( 1, 1 ) );  
   hm1.insert ( Int_Pair ( 2, 4 ) );  
  
   hm1_cIter = hm1.begin ( );  
   cout << "The first element of hm1 is " << hm1_cIter -> first   
        << "." << endl;  
  
   hm1_Iter = hm1.begin ( );  
   hm1.erase ( hm1_Iter );  
  
   // The following 2 lines would err because the iterator is const  
   // hm1_cIter = hm1.begin ( );  
   // hm1.erase ( hm1_cIter );  
  
   hm1_cIter = hm1.begin( );  
   cout << "The first element of hm1 is now " << hm1_cIter -> first   
        << "." << endl;  
}  
```  
  
```Output  
The first element of hm1 is 0.  
The first element of hm1 is now 1.  
```  
  
##  <a name="cbegin"></a>hash_multimap::cbegin  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Hash_multimap ilk öğe adresleme const yineleyici döndürür.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk öğe adresleme const bir çift yönlü yineleyici [hash_multimap](../standard-library/hash-multimap-class.md) ya da boş bir başarılı konumu `hash_multimap`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_cbegin.cpp  
// compile with: /EHsc  
#include <hash_multimap>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1;  
  
   hash_multimap <int, int> :: const_iterator hm1_cIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 2, 4 ) );  
  
   hm1_cIter = hm1.cbegin ( );  
   cout << "The first element of hm1 is "   
        << hm1_cIter -> first << "." << endl;  
   }  
```  
  
```Output  
The first element of hm1 is 2.  
```  
  
##  <a name="cend"></a>hash_multimap::cend  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Bir hash_multimap son öğesi başarılı konumu adresleri const bir yineleyici döndürür.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Son öğesi başarılı konumu adresleri const bir çift yönlü yineleyici bir [hash_multimap](../standard-library/hash-multimap-class.md). Varsa `hash_multimap` boş olduğundan `hash_multimap::cend == hash_multimap::begin`.  
  
### <a name="remarks"></a>Açıklamalar  
 `cend`Yineleyici kendi hash_multimap sonuna ulaştı olup olmadığını test etmek için kullanılır.  
  
 Tarafından döndürülen değer `cend` değil başvuru yapıldı.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_cend.cpp  
// compile with: /EHsc  
#include <hash_multimap>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1;  
  
   hash_multimap <int, int> :: const_iterator hm1_cIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   hm1_cIter = hm1.cend( );  
   hm1_cIter--;  
   cout << "The value of last element of hm1 is "   
        << hm1_cIter -> second << "." << endl;  
   }  
```  
  
```Output  
The value of last element of hm1 is 30.  
```  
  
##  <a name="clear"></a>hash_multimap::Clear  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Bir hash_multimap tüm öğeleri siler.  
  
```  
void clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  Aşağıdaki örnek hash_multimap::clear üye fonksiyonu kullanımını göstermektedir.  
  
```  
// hash_multimap_clear.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    using namespace stdext;  
    hash_multimap<int, int> hm1;  
    hash_multimap<int, int>::size_type i;  
    typedef pair<int, int> Int_Pair;  
  
    hm1.insert(Int_Pair(1, 1));  
    hm1.insert(Int_Pair(2, 4));  
  
    i = hm1.size();  
    cout << "The size of the hash_multimap is initially "  
         << i  << "." << endl;  
  
    hm1.clear();  
    i = hm1.size();  
    cout << "The size of the hash_multimap after clearing is "  
         << i << "." << endl;  
}  
```  
  
```Output  
The size of the hash_multimap is initially 2.  
The size of the hash_multimap after clearing is 0.  
```  
  
##  <a name="const_iterator"></a>hash_multimap::const_iterator  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Çift yönlü yineleyici bu can sağlayan bir türü okuma bir **const** hash_multimap öğesinde.  
  
```  
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.  
  
 `const_iterator` Nesnelerin hash_multimap noktalarına tarafından tanımlanan [value_type](#value_type), türü olan `pair`  *\<*  **constKey, türü**  *>*. Anahtar değeri ilk üye çifti kullanılabilir ve eşlenen öğesinin değeri çifti ikinci üyesi üzerinden kullanılabilir.  
  
 Başvuru için bir `const_iterator` `cIter` bir hash_multimap bir öğesine işaret eden, kullanın  **->**  işleci.  
  
 Öğe için anahtar değerini erişmek için `cIter`  ->  **ilk**, eşit olduğu (\* `cIter`). **İlk**. Eşlenen veri öğesinin değeri erişmek için `cIter`  ->  **ikinci**, eşit olduğu (\* `cIter`). **İlk**.  
  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [başlamak](#begin) kullanarak bir örnek için `const_iterator`.  
  
##  <a name="const_pointer"></a>hash_multimap::const_pointer  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Bir işaretçi sağlayan bir türü bir **const** bir hash_multimap öğesinde.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.  
  
 Çoğu durumda, bir [yineleyici](#iterator) hash_multimap nesnesindeki öğelerin erişmek için kullanılmalıdır.  
  
   
  
##  <a name="const_reference"></a>hash_multimap::const_reference  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Bir başvuru sağlayan bir türü bir **const** okumak ve gerçekleştirmek için bir hash_multimap depolanan öğesi **const** işlemleri.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_const_ref.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap<int, int> hm1;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
  
   // Declare and initialize a const_reference &Ref1   
   // to the key of the first element  
   const int &Ref1 = ( hm1.begin( ) -> first );  
  
   // The following line would cause an error because the   
   // non-const_reference cannot be used to access the key  
   // int &Ref1 = ( hm1.begin( ) -> first );  
  
   cout << "The key of first element in the hash_multimap is "  
        << Ref1 << "." << endl;  
  
   // Declare and initialize a reference &Ref2   
   // to the data value of the first element  
   int &Ref2 = ( hm1.begin() -> second );  
  
   cout << "The data value of 1st element in the hash_multimap is "  
        << Ref2 << "." << endl;  
}  
```  
  
```Output  
The key of first element in the hash_multimap is 1.  
The data value of 1st element in the hash_multimap is 10.  
```  
  
##  <a name="const_reverse_iterator"></a>hash_multimap::const_reverse_iterator  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Herhangi bir çift yönlü yineleyici bu can sağlayan bir türü okuma **const** hash_multimap öğesinde.  
  
```  
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse_iterator const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_reverse_iterator` bir öğenin değerini değiştiremez ve kullanın ters hash_multimap yinelemek için.  
  
 `const_reverse_iterator` Nesnelerin hash_multimap noktalarına tarafından tanımlanan [value_type](#value_type), türü olan `pair`  *\<*  **const anahtar, türü >**, ilk üye öğesi anahtarıdır ve ikinci olan üye eşlenen datum öğe tarafından tutulur.  
  
 Başvuru için bir `const_reverse_iterator` `crIter` bir hash_multimap bir öğesine işaret eden, kullanın  **->**  işleci.  
  
 Öğe için anahtar değerini erişmek için `crIter`  ->  **ilk**, eşit olduğu (\* `crIter`). **İlk**. Eşlenen veri öğesinin değeri erişmek için `crIter`  ->  **ikinci**, eşit olduğu (\* `crIter`). **İlk**.  
  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [rend](#rend) bildirme ve kullanma konusunda bir örnek için `const_reverse_iterator`.  
  
##  <a name="count"></a>hash_multimap::Count  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Parametresi belirtilen bir anahtarı olan anahtarla eşleşen bir hash_multimap öğe sayısını döndürür.  
  
```  
size_type count(const Key& key) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Öğeleri hash_multimap eşleştirilmesi için anahtar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 hash_multimap olan sıralama anahtarı parametre anahtarıyla eşleşen bir öğe içeriyorsa 1; 0 hash_multimap bir öğesi ile eşleşen bir anahtarı içermiyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini aralığında öğe sayısını döndürür  
  
 **[lower_bound (** `key` **), upper_bound (** `key` **))**  
  
 bir anahtar değerine sahip `key`.  
  
   
  
### <a name="example"></a>Örnek  
  Aşağıdaki örnek hash_multimap::count üye fonksiyonu kullanımını göstermektedir.  
  
```  
// hash_multimap_count.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
    using namespace std;  
    using namespace stdext;  
    hash_multimap<int, int> hm1;  
    hash_multimap<int, int>::size_type i;  
    typedef pair<int, int> Int_Pair;  
  
    hm1.insert(Int_Pair(1, 1));  
    hm1.insert(Int_Pair(2, 1));  
    hm1.insert(Int_Pair(1, 4));  
    hm1.insert(Int_Pair(2, 1));  
  
    // Elements do not need to have unique keys in hash_multimap,  
    // so duplicates are allowed and counted  
    i = hm1.count(1);  
    cout << "The number of elements in hm1 with a sort key of 1 is: "  
         << i << "." << endl;  
  
    i = hm1.count(2);  
    cout << "The number of elements in hm1 with a sort key of 2 is: "  
         << i << "." << endl;  
  
    i = hm1.count(3);  
    cout << "The number of elements in hm1 with a sort key of 3 is: "  
         << i << "." << endl;  
}  
```  
  
```Output  
The number of elements in hm1 with a sort key of 1 is: 2.  
The number of elements in hm1 with a sort key of 2 is: 2.  
The number of elements in hm1 with a sort key of 3 is: 0.  
```  
  
##  <a name="crbegin"></a>hash_multimap::crbegin  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Ters hash_multimap ilk öğe adresleme const yineleyici döndürür.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir const ters ilk öğe bir ters adresleme çift yönlü yineleyici [hash_multimap](../standard-library/hash-multimap-class.md) veya ne son öğesi unreversed olsaydı adresleme `hash_multimap`.  
  
### <a name="remarks"></a>Açıklamalar  
 `crbegin`Ters hash_multimap ile kullanılan gibi [hash_multimap::begin](#begin) ile kullanılan bir `hash_multimap`.  
  
 Dönüş değeri ile `crbegin`, `hash_multimap` nesnesi değiştirilemez.  
  
 `crbegin`yinelemek için kullanılabilecek bir `hash_multimap` geriye doğru.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_crbegin.cpp  
// compile with: /EHsc  
#include <hash_multimap>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1;  
  
   hash_multimap <int, int> :: const_reverse_iterator hm1_crIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   hm1_crIter = hm1.crbegin( );  
   cout << "The first element of the reversed hash_multimap hm1 is "  
        << hm1_crIter -> first << "." << endl;  
}  
```  
  
```Output  
The first element of the reversed hash_multimap hm1 is 3.  
```  
  
##  <a name="crend"></a>hash_multimap::crend  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Ters hash_multimap son öğesi başarılı konumu adresleri const bir yineleyici döndürür.  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir const ters son öğesi bir ters başarılı konumu adresleri çift yönlü yineleyici [hash_multimap](../standard-library/hash-multimap-class.md) (ilk öğe unreversed öncesinde konumu `hash_multimap`).  
  
### <a name="remarks"></a>Açıklamalar  
 `crend`Ters hash_multimap ile kullanılan gibi [hash_multimap::end](#end) hash_multimap ile kullanılır.  
  
 Dönüş değeri ile `crend`, `hash_multimap` nesnesi değiştirilemez.  
  
 `crend`Ters yineleyici kendi hash_multimap sonuna olup ulaştı için test etmek için kullanılabilir.  
  
 Tarafından döndürülen değer `crend` değil başvuru yapıldı.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_crend.cpp  
// compile with: /EHsc  
#include <hash_multimap>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1;  
  
   hash_multimap <int, int> :: const_reverse_iterator hm1_crIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   hm1_crIter = hm1.crend( );  
   hm1_crIter--;  
   cout << "The last element of the reversed hash_multimap hm1 is "  
        << hm1_crIter -> first << "." << endl;  
}  
```  
  
```Output  
The last element of the reversed hash_multimap hm1 is 3.  
```  
  
##  <a name="difference_type"></a>hash_multimap::difference_type  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Hash_multimap yineleyiciler tarafından işaret öğeler arasındaki bir aralıkta öğe sayısını temsil etmek için kullanılan bir imzalı tamsayı türü.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `difference_type` Türü çıkarılmasıyla veya kapsayıcı yineleyiciler artırma döndürülür. `difference_type` Genellikle aralığında öğe sayısını temsil etmek için kullanılan *[Soyadı)* yineleyiciler arasında `first` ve `last`, gösterdiği öğesini içeren `first` ve aralığı öğeleri kadar ancak dahil değil, öğe işaret için tarafından `last`.  
  
 Ancak unutmayın `difference_type` kümesi, çıkarma yineleyiciler arasında yalnızca gibi ters çevrilebilir kapsayıcıları tarafından desteklenen çift yönlü yineleyiciler sınıfı içeren bir giriş yineleyici gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir rasgele erişim kapsayıcı vektör gibi tarafından sağlanan rasgele erişim yineleyiciler tarafından desteklenir.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_difference_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <hash_map>  
#include <algorithm>  
  
int main()  
{  
    using namespace std;  
    using namespace stdext;  
    hash_multimap<int, int> hm1;  
    typedef pair<int, int> Int_Pair;  
  
    hm1.insert(Int_Pair(2, 20));  
    hm1.insert(Int_Pair(1, 10));  
    hm1.insert(Int_Pair(3, 20));  
  
    // The following will insert, because map keys  
    // do not need to be unique  
    hm1.insert(Int_Pair(2, 30));  
  
    hash_multimap<int, int>::iterator hm1_Iter, hm1_bIter, hm1_eIter;  
    hm1_bIter = hm1.begin();  
    hm1_eIter = hm1.end();  
  
    // Count the number of elements in a hash_multimap  
    hash_multimap<int, int>::difference_type df_count = 0;  
    hm1_Iter = hm1.begin();  
    while (hm1_Iter != hm1_eIter)  
    {  
        df_count++;  
        hm1_Iter++;  
    }  
  
    cout << "The number of elements in the hash_multimap hm1 is: "  
         << df_count << "." << endl;  
  
    cout << "The keys of the mapped elements are:";  
    for (hm1_Iter= hm1.begin() ; hm1_Iter!= hm1.end();  
        hm1_Iter++)  
        cout << " " << hm1_Iter-> first;  
    cout << "." << endl;  
  
    cout << "The values of the mapped elements are:";  
    for (hm1_Iter= hm1.begin() ; hm1_Iter!= hm1.end();  
        hm1_Iter++)  
        cout << " " << hm1_Iter-> second;  
    cout << "." << endl;  
}  
```  
  
```Output  
The number of elements in the hash_multimap hm1 is: 4.  
The keys of the mapped elements are: 1 2 2 3.  
The values of the mapped elements are: 10 20 30 20.  
```  
  
##  <a name="emplace"></a>hash_multimap::emplace  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Hash_multimap yerinde oluşturulan bir öğe ekler.  
  
```  
template <class ValTy>  
iterator emplace(ValTy&& val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`val`|Taşıma için kullanılan değer oluşturmak içine Eklenecek öğenin [hash_multimap](../standard-library/hash-multimap-class.md).|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `emplace` Üye işlevi yeni öğe eklenir burada konumuna işaret eden bir yineleyici döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 [Hash_multimap::value_type](#value_type) böylece bir öğe değerini bir sıralı çifti anahtar değerine eşit ilk bileşeni ve öğenin veri değerine eşit ikinci bileşeni ile bir çift öğesidir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_emplace.cpp  
// compile with: /EHsc  
#include<hash_multimap>  
#include<iostream>  
#include <string>  
  
int main()  
{  
    using namespace std;  
    using namespace stdext;  
    hash_multimap<int, string> hm1;  
    typedef pair<int, string> is1(1, "a");  
  
    hm1.emplace(move(is1));  
    cout << "After the emplace, hm1 contains:" << endl  
      << " " << hm1.begin()->first  
      << " => " << hm1.begin()->second  
      << endl;  
}  
```  
  
```Output  
After the emplace insertion, hm1 contains:  
 1 => a  
```  
  
##  <a name="emplace_hint"></a>hash_multimap::emplace_hint  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Yerleştirme İpucu ile bir hash_multimap içine yerinde oluşturulan bir öğe ekler.  
  
```  
template <class ValTy>  
iterator emplace_hint(
    const_iterator _Where,  
    ValTy&& val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`val`|Taşıma için kullanılan değer oluşturmak içine Eklenecek öğenin [hash_multimap](../standard-library/hash-multimap-class.md) sürece `hash_multimap` zaten o öğenin (veya daha genel olarak, anahtar eşdeğer sıralanmış bir öğe) içerir.|  
|`_Where`|Ekleme için doğru noktası aramaya başlamak için yer ile ilgili bir ipucu.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 [Hash_multimap::emplace](#emplace) üye işlevinin döndürdüğü burada yeni öğe eklenir içine konumuna işaret eden bir yineleyici `hash_multimap`.  
  
### <a name="remarks"></a>Açıklamalar  
 [Hash_multimap::value_type](#value_type) böylece bir öğe değerini bir sıralı çifti anahtar değerine eşit ilk bileşeni ve öğenin veri değerine eşit ikinci bileşeni ile bir çift öğesidir.  
  
 Ekleme gerçekleşebilir Logaritmik zaman yerine amortized sabit zaman ekleme noktasını hemen izleyen `_Where`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_emplace_hint.cpp  
// compile with: /EHsc  
#include<hash_multimap>  
#include<iostream>  
#include <string>  
  
int main()  
{  
    using namespace std;  
    using namespace stdext;  
    hash_multimap<int, string> hm1;  
    typedef pair<int, string> is1(1, "a");  
  
    hm1.emplace(hm1.begin(), move(is1));  
    cout << "After the emplace insertion, hm1 contains:" << endl  
      << " " << hm1.begin()->first  
      << " => " << hm1.begin()->second  
      << endl;  
}  
```  
  
```Output  
After the emplace insertion, hm1 contains:  
 1 => a  
```  
  
##  <a name="empty"></a>hash_multimap::empty  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Bir hash_multimap boşsa, testleri.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** hash_multimap boşsa; **false** hash_multimap boş olmayan ise.  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_empty.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1, hm2;  
  
   typedef pair <int, int> Int_Pair;  
   hm1.insert ( Int_Pair ( 1, 1 ) );  
  
   if ( hm1.empty( ) )  
      cout << "The hash_multimap hm1 is empty." << endl;  
   else  
      cout << "The hash_multimap hm1 is not empty." << endl;  
  
   if ( hm2.empty( ) )  
      cout << "The hash_multimap hm2 is empty." << endl;  
   else  
      cout << "The hash_multimap hm2 is not empty." << endl;  
}  
```  
  
```Output  
The hash_multimap hm1 is not empty.  
The hash_multimap hm2 is empty.  
```  
  
##  <a name="end"></a>hash_multimap::End  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Bir hash_multimap son öğesi başarılı konumu adresleri yineleyici döndürür.  
  
```  
const_iterator end() const;

iterator end();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir hash_multimap son öğesi başarılı konumu adresleri çift yönlü yineleyici. Hash_multimap boş, hash_multimap::end ise hash_multimap::begin ==.  
  
### <a name="remarks"></a>Açıklamalar  
 **Son** yineleyici kendi hash_multimap sonuna ulaştı olup olmadığını test etmek için kullanılır.  
  
 Tarafından döndürülen değer **son** değil başvuru yapıldı.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_end.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1;  
  
   hash_multimap <int, int> :: iterator hm1_Iter;  
   hash_multimap <int, int> :: const_iterator hm1_cIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   hm1_cIter = hm1.end( );  
   hm1_cIter--;  
   cout << "The value of last element of hm1 is "   
        << hm1_cIter -> second << "." << endl;  
  
   hm1_Iter = hm1.end( );  
   hm1_Iter--;  
   hm1.erase ( hm1_Iter );  
  
   // The following 2 lines would err because the iterator is const  
   // hm1_cIter = hm1.end ( );  
   // hm1_cIter--;  
   // hm1.erase ( hm1_cIter );  
  
   hm1_cIter = hm1.end( );  
   hm1_cIter--;  
   cout << "The value of last element of hm1 is now "  
        << hm1_cIter -> second << "." << endl;  
}  
```  
  
```Output  
The value of last element of hm1 is 30.  
The value of last element of hm1 is now 20.  
```  
  
##  <a name="equal_range"></a>hash_multimap::equal_range  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Yineleyiciler çifti sırasıyla hash_multimap belirtilen anahtar daha büyük bir anahtarla ilk öğe ve eşit veya bundan büyük anahtarı bir anahtarla hash_multimap ilk öğe döndürür.  
  
```  
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Aranmakta hash_multimap öğeden sıralama anahtarı ile Karşılaştırılacak bağımsız değişkeni anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleyiciler çifti ilk olacak şekilde, [lower_bound](#lower_bound) anahtarı ve ikincisi [upper_bound](#upper_bound) anahtarı.  
  
 İlk yineleyici çiftinin erişmek için `pr` üye işlevi tarafından döndürülen, kullanmak `pr`. **İlk** ve alt sınır yineleyici başvurulacak kullanmak \*( `pr`. **İlk**). İkinci yineleyici çiftinin erişmek için `pr` üye işlevi tarafından döndürülen, kullanmak `pr`. **İkinci** ve üst sınır yineleyici başvurulacak kullanmak \*( `pr`. **İkinci**).  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_equal_range.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   typedef hash_multimap <int, int> IntMMap;  
   IntMMap hm1;  
   hash_multimap <int, int> :: const_iterator hm1_RcIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   pair <IntMMap::const_iterator, IntMMap::const_iterator> p1, p2;  
   p1 = hm1.equal_range( 2 );  
  
   cout << "The lower bound of the element with "  
        << "a key of 2\n in the hash_multimap hm1 is: "  
        << p1.first -> second << "." << endl;  
  
   cout << "The upper bound of the element with "  
        << "a key of 2\n in the hash_multimap hm1 is: "  
        << p1.second -> second << "." << endl;  
  
   // Compare the upper_bound called directly   
   hm1_RcIter = hm1.upper_bound( 2 );  
  
   cout << "A direct call of upper_bound( 2 ) gives "  
        << hm1_RcIter -> second << "," << endl  
        << " matching the 2nd element of the pair"  
        << " returned by equal_range( 2 )." << endl;  
  
   p2 = hm1.equal_range( 4 );  
  
   // If no match is found for the key,  
   // both elements of the pair return end( )  
   if ( ( p2.first == hm1.end( ) ) && ( p2.second == hm1.end( ) ) )  
      cout << "The hash_multimap hm1 doesn't have an element "  
           << "with a key less than 4." << endl;  
   else  
      cout << "The element of hash_multimap hm1 with a key >= 40 is: "  
           << p1.first -> first << "." << endl;  
}  
```  
  
```Output  
The lower bound of the element with a key of 2  
 in the hash_multimap hm1 is: 20.  
The upper bound of the element with a key of 2  
 in the hash_multimap hm1 is: 30.  
A direct call of upper_bound( 2 ) gives 30,  
 matching the 2nd element of the pair returned by equal_range( 2 ).  
The hash_multimap hm1 doesn't have an element with a key less than 4.  
```  
  
##  <a name="erase"></a>hash_multimap::ERASE  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Bir öğenin veya bir dizi öğeleri hash_multimap belirtilen konumlardan kaldırır veya belirtilen anahtar eşleşen öğeleri kaldırır.  
  
```  
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Where`  
 Hash_multimap kaldırılacak öğe konumu.  
  
 `first`  
 İlk öğenin konumunu hash_multimap kaldırıldı.  
  
 `last`  
 Yalnızca son öğenin ötesinde konumu hash_multimap kaldırıldı.  
  
 `key`  
 Hash_multimap kaldırılacak öğe anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk iki üye işlevleri için çift yönlü Yineleyici, böyle bir öğe varsa, kaldırılan öğelerin veya işaretçisi hash_multimap sonuna dışında kalan ilk öğe belirler.  
  
 Üye işlevi için üçüncü hash_multimap kaldırılmış olan öğe sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevleri hiçbir zaman bir özel durum.  
  
   
  
### <a name="example"></a>Örnek  
  Aşağıdaki örnek hash_multimap::erase üye fonksiyonu kullanımını göstermektedir.  
  
```  
// hash_multimap_erase.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    using namespace stdext;  
    hash_multimap<int, int> hm1, hm2, hm3;  
    hash_multimap<int, int> :: iterator pIter, Iter1, Iter2;  
    int i;  
    hash_multimap<int, int>::size_type n;  
    typedef pair<int, int> Int_Pair;  
  
    for (i = 1; i < 5; i++)  
    {  
        hm1.insert(Int_Pair (i, i) );  
        hm2.insert(Int_Pair (i, i*i) );  
        hm3.insert(Int_Pair (i, i-1) );  
    }  
  
    // The 1st member function removes an element at a given position  
    Iter1 = ++hm1.begin();  
    hm1.erase(Iter1);  
  
    cout << "After the 2nd element is deleted, "  
         << "the hash_multimap hm1 is:";  
    for (pIter = hm1.begin(); pIter != hm1.end(); pIter++)  
        cout << " " << pIter -> second;  
    cout << "." << endl;  
  
    // The 2nd member function removes elements  
    // in the range [ first,  last)  
    Iter1 = ++hm2.begin();  
    Iter2 = --hm2.end();  
    hm2.erase(Iter1, Iter2);  
  
    cout << "After the middle two elements are deleted, "  
         << "the hash_multimap hm2 is:";  
    for (pIter = hm2.begin(); pIter != hm2.end(); pIter++)  
        cout << " " << pIter -> second;  
    cout << "." << endl;  
  
    // The 3rd member function removes elements with a given  key  
    hm3.insert(Int_Pair (2, 5));  
    n = hm3.erase(2);  
  
    cout << "After the element with a key of 2 is deleted,\n"  
         << " the hash_multimap hm3 is:";  
    for (pIter = hm3.begin(); pIter != hm3.end(); pIter++)  
        cout << " " << pIter -> second;  
    cout << "." << endl;  
  
    // The 3rd member function returns the number of elements removed  
    cout << "The number of elements removed from hm3 is: "  
         << n << "." << endl;  
  
    // The dereferenced iterator can also be used to specify a key  
    Iter1 = ++hm3.begin();  
    hm3.erase(Iter1);  
  
    cout << "After another element with a key equal to that of the"  
         << endl;  
    cout  << " 2nd element is deleted, "  
          << "the hash_multimap hm3 is:";  
    for (pIter = hm3.begin(); pIter != hm3.end(); pIter++)  
        cout << " " << pIter -> second;  
    cout << "." << endl;  
}  
```  
  
```Output  
After the 2nd element is deleted, the hash_multimap hm1 is: 1 3 4.  
After the middle two elements are deleted, the hash_multimap hm2 is: 1 16.  
After the element with a key of 2 is deleted,  
 the hash_multimap hm3 is: 0 2 3.  
The number of elements removed from hm3 is: 2.  
After another element with a key equal to that of the  
 2nd element is deleted, the hash_multimap hm3 is: 0 3.  
```  
  
##  <a name="find"></a>hash_multimap::Find  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Belirtilen anahtar için eşdeğer bir anahtara sahip bir hash_multimap bir öğedeki ilk konumunu adresleme yineleyici döndürür.  
  
```  
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Aranmakta hash_multimap öğeden sıralama anahtarı tarafından eşleştirilmesini anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen bir anahtar veya anahtar için bir eşleşme varsa hash_multimap son öğesi başarılı konumu ile bir öğenin ilk konum adresleri yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi olan sıralama anahtarı hash_multimap bir öğedeki adresleri yineleyici döndürür **eşdeğer** bağımsız değişkeni comparability ilişkisi küçüktür anahtarı bir sıralama uygulanmasını ikili bir koşul altında dayalı.  
  
 Varsa dönüş değerini **Bul** atanmış bir `const_iterator`, hash_multimap nesnesi değiştirilemez. Varsa dönüş değerini **Bul** atanmış bir **yineleyici**, hash_multimap nesne değiştirilebilir.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_find.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <hash_map>  
  
int main()  
{  
    using namespace std;  
    using namespace stdext;  
    hash_multimap<int, int> hm1;  
    hash_multimap<int, int> :: const_iterator hm1_AcIter, hm1_RcIter;  
    typedef pair<int, int> Int_Pair;  
  
    hm1.insert(Int_Pair(1, 10));  
    hm1.insert(Int_Pair(2, 20));  
    hm1.insert(Int_Pair(3, 20));  
    hm1.insert(Int_Pair(3, 30));  
  
    hm1_RcIter = hm1.find(2);  
    cout << "The element of hash_multimap hm1 with a key of 2 is: "  
          << hm1_RcIter -> second << "." << endl;  
  
    hm1_RcIter = hm1.find(3);  
    cout << "The first element of hash_multimap hm1 with a key of 3 is: "  
          << hm1_RcIter -> second << "." << endl;  
  
    // If no match is found for the key, end() is returned  
    hm1_RcIter = hm1.find(4);  
  
    if (hm1_RcIter == hm1.end())  
        cout << "The hash_multimap hm1 doesn't have an element "  
             << "with a key of 4." << endl;  
    else  
        cout << "The element of hash_multimap hm1 with a key of 4 is: "  
             << hm1_RcIter -> second << "." << endl;  
  
    // The element at a specific location in the hash_multimap can be  
    // found using a dereferenced iterator addressing the location  
    hm1_AcIter = hm1.end();  
    hm1_AcIter--;  
    hm1_RcIter = hm1.find(hm1_AcIter -> first);  
    cout << "The first element of hm1 with a key matching"  
         << endl << "that of the last element is: "  
         << hm1_RcIter -> second << "." << endl;  
  
    // Note that the first element with a key equal to  
    // the key of the last element is not the last element  
    if (hm1_RcIter == --hm1.end())  
        cout << "This is the last element of hash_multimap hm1."  
             << endl;  
    else  
        cout << "This is not the last element of hash_multimap hm1."  
             << endl;  
}  
```  
  
```Output  
The element of hash_multimap hm1 with a key of 2 is: 20.  
The first element of hash_multimap hm1 with a key of 3 is: 20.  
The hash_multimap hm1 doesn't have an element with a key of 4.  
The first element of hm1 with a key matching  
that of the last element is: 20.  
This is not the last element of hash_multimap hm1.  
```  
  
##  <a name="get_allocator"></a>hash_multimap::get_allocator  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Hash_multimap oluşturmak için kullanılan ayırıcısı nesnesinin bir kopyasını döndürür.  
  
```  
Allocator get_allocator() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hash_multimap tarafından kullanılan ayırıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Allocators hash_multimap sınıfı için sınıf depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan allocators çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak ileri düzeyde C++ bir konudur.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_get_allocator.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int>::allocator_type hm1_Alloc;  
   hash_multimap <int, int>::allocator_type hm2_Alloc;  
   hash_multimap <int, double>::allocator_type hm3_Alloc;  
   hash_multimap <int, int>::allocator_type hm4_Alloc;  
  
   // The following lines declare objects  
   // that use the default allocator.  
   hash_multimap <int, int> hm1;  
   hash_multimap <int, int> hm2;  
   hash_multimap <int, double> hm3;  
  
   hm1_Alloc = hm1.get_allocator( );  
   hm2_Alloc = hm2.get_allocator( );  
   hm3_Alloc = hm3.get_allocator( );  
  
   cout << "The number of integers that can be allocated"  
        << endl << " before free memory is exhausted: "  
        << hm2.max_size( ) << "." << endl;  
  
   cout << "The number of doubles that can be allocated"  
        << endl << " before free memory is exhausted: "  
        << hm3.max_size( ) <<  "." << endl;  
  
   // The following line creates a hash_multimap hm4  
   // with the allocator of hash_multimap hm1.  
   hash_multimap <int, int> hm4( less<int>( ), hm1_Alloc );  
  
   hm4_Alloc = hm4.get_allocator( );  
  
   // Two allocators are interchangeable if  
   // storage allocated from each can be  
   // deallocated by the other  
   if( hm1_Alloc == hm4_Alloc )     
   {  
      cout << "The allocators are interchangeable."  
           << endl;     
   }  
   else     
   {  
      cout << "The allocators are not interchangeable."  
           << endl;  
   }  
}  
```  
  
##  <a name="hash_multimap"></a>hash_multimap::hash_multimap  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Boş veya tüm kopyalama veya başka bir hash_multimap parçası olan bir hash_multimap oluşturur.  
  
```  
hash_multimap();

explicit hash_multimap(
    const Compare& Comp);

hash_multimap(
    const Compare& Comp,  
    const Allocator& Al);

hash_multimap(
    const hash_multimap& Right);

hash_multimap(
    hash_multimap&& Right);

hash_multimap(
    initializer_list<Type> IList);

hash_multimap(
    initializer_list<Type> IList,  
    const Compare& Comp);

 
hash_multimap(
    initializer_list<Type> IList,  
    const Compare& Comp,  
    const Allocator& Al);

template <class InputIterator>  
hash_multimap(
 InputIterator First,  
    InputIterator Last);

template <class InputIterator>  
hash_multimap(
 InputIterator First,  
    InputIterator Last,  
    const Compare& Comp);

template <class InputIterator>  
hash_multimap(
 InputIterator First,  
    InputIterator Last,  
    const Compare& Comp,  
    const Allocator& Al);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Al`|Varsayılan olarak bu hash_multimap nesne için kullanılacak depolama allocator sınıfı `Allocator`.|  
|`Comp`|Türü karşılaştırma işlevinden `const Traits` varsayılan olarak eşlemesindeki öğeleri sıralamak için kullanılan `Traits`.|  
|`Right`|Oluşturulan kümesi bir kopya olarak olduğu eşleme.|  
|`First`|Kopyalanacak öğe aralığını ilk öğe konumu.|  
|`Last`|Kopyalanacak öğeleri aralık ötesinde ilk öğe konumu.|  
|`IList`|Kopyalanacak initializer_list.|  
  
### <a name="remarks"></a>Açıklamalar  
 Hash_multimap için bellek depolama yönetir ve, daha sonra döndürülüp döndürülmediğini çağırarak ayırıcısı nesne türünü tüm oluşturucular depolamak [get_allocator](#get_allocator). Allocator parametresi sınıf bildirimlerinde genellikle atlanır ve önişlem makroları alternatif allocators yerine kullanılır.  
  
 Tüm oluşturucular kendi hash_multimap başlatır.  
  
 İşlev nesnesi türündeki tüm oluşturucular depolamak `Traits` sipariş hash_multimap anahtarlar oluşturmak için kullanılır ve daha sonra çağırarak döndürülebilecek [key_comp](#key_comp).  
  
 İlk üç oluşturucular boş bir ilk hash_multimap belirtin; İkinci karşılaştırma işlevi türünü belirtir ( `Comp`) öğeleri ve üçüncü sırasını açıkça oluşturmada kullanılacak ayırıcı türünü belirtir ( `_Al`) kullanılacak. Anahtar sözcüğü `explicit` otomatik tür dönüştürme belirli türdeki gizler.  
  
 Hash_multimap bir kopyasını dördüncü Oluşturucusu belirtir `Right`.  
  
 Sonraki üç oluşturucular aralığı kopyalayın `First, Last)` sınıfının karşılaştırma işlevini türünü belirleyen içinde explicitness artan eşleme **nitelikler** ve ayırıcı.  
  
 Hash_multimap sekizinci Oluşturucusu taşır `Right`.  
  
 Son üç oluşturucular bir initializer_list kullanın.  
  
##  <a name="insert"></a>hash_multimap::insert  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Bir öğenin veya bir dizi öğeleri hash_multimap ekler.  
  
```  
iterator insert(
    const value_type& Val);

iterator insert(
    const_iterator Where,  
    const value_type& Val);void insert(
    initializer_list<value_type> IList);

template <class InputIterator>  
void insert(
    InputIterator First,  
    InputIterator Last);

template <class ValTy>  
iterator insert(
    ValTy&& Val);

template <class ValTy>  
iterator insert(
    const_iterator Where,  
    ValTy&& Val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Val`|Bu öğe zaten içeriyor veya zaten bir öğe olan anahtar içerdiği sürece daha genel olarak, eşdeğer sıralanır sürece hash_multimap Eklenecek öğenin değeri.|  
|`Where`|Ekleme için doğru noktası aramaya başlamak nereye konusunda ipucu.|  
|`First`|Bir eşlemesinden kopyalanacak ilk öğe konumu.|  
|`Last`|Yalnızca bir eşlemesinden kopyalanacak son öğenin ötesinde konumu.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk iki `insert` üye işlevleri yeni öğe eklenir burada konumuna işaret eden bir yineleyici döndürür.  
  
 Eklenecek öğeler için bir initializer_list üçüncü üye işlevi kullanır.  
  
 Dördüncü üye işlevi bir dizi öğesi değerlerini yineleyici aralığında tarafından ele her öğesine karşılık gelen bir harita ekler `[First, Last)` belirtilen kümenin.  
  
 Son iki `insert` üye işlevleri davrandığını ilk iki aynı bunlar taşıma-yapı eklenen değer dışında.  
  
### <a name="remarks"></a>Açıklamalar  
 [Value_type](#value_type) böylece bir öğenin değerini ilk bileşen olduğu anahtar değerine eşit bir sıralı çiftinin bir çifti öğesidir ve ikinci öğesi veri değerine eşit bileşendir.  
  
 Ekleme ipucu sürümü için amortized sabit zaman içinde gerçekleşebilir `insert`, ekleme noktasını hemen izliyorsa Logaritmik zaman yerine `Where`.  
  
##  <a name="iterator"></a>hash_multimap::iterator  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Okuma veya herhangi bir hash_multimap öğesinde değiştirmek için bir çift yönlü yineleyici sağlayan türü.  
  
```  
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 **Yineleyici** nesnelerin hash_multimap noktalarına tarafından tanımlanan [value_type](#value_type), türü olan `pair` \< **const anahtar, türü**>, yalnızca ilk üye anahtarı öğesi olduğundan ve ikinci öğe tarafından tutulan eşlenen datum üyesidir.  
  
 Başvuru için bir **yineleyici** `Iter` bir hash_multimap bir öğesine işaret eden, kullanın  **->**  işleci.  
  
 Öğe için anahtar değerini erişmek için `Iter`  ->  **ilk**, eşit olduğu (\* `Iter`). **İlk**. Eşlenen veri öğesinin değeri erişmek için `Iter`  ->  **ikinci**, eşit olduğu (\* `Iter`). **İlk**.  
  
 Bir tür **yineleyici** bir öğenin değerini değiştirmek için kullanılabilir.  
  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [başlamak](#begin) bildirme ve kullanma konusunda bir örnek için **yineleyici**.  
  
##  <a name="key_comp"></a>hash_multimap::key_comp  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Bir hash_multimap sipariş anahtarlarında kullanılacak karşılaştırma nesnesinin bir kopyasını alır.  
  
```  
key_compare key_comp() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri sıralamak için bir hash_multimap kullanan işlevi nesnesini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini saklanan nesne tanımlar  
  
 **bool işleci (const anahtar &** `left` **, const anahtar &** `right` **);**  
  
 döndüren **true** varsa `left` önündeki ve eşit değil `right` sıralama düzeninde.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_key_comp.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
  
   hash_multimap <int, int, hash_compare<int, less<int>>> hm1;  
   hash_multimap <int, int, hash_compare<int, less<int>>   
      >::key_compare kc1 = hm1.key_comp( ) ;  
   bool result1 = kc1( 2, 3 ) ;  
   if( result1 == true )  
   {  
      cout << "kc1( 2,3 ) returns value of true,\n"  
           << "where kc1 is the function object of hm1.\n"  
           << endl;  
   }  
   else     
   {  
      cout << "kc1( 2,3 ) returns value of false,\n"  
           << "where kc1 is the function object of hm1.\n"  
           << endl;  
   }  
  
   hash_multimap <int, int, hash_compare<int, greater<int>>> hm2;  
   hash_multimap <int, int, hash_compare<int, greater<int>>   
      >::key_compare kc2 = hm2.key_comp( );  
   bool result2 = kc2( 2, 3 ) ;  
   if( result2 == true )  
   {  
      cout << "kc2( 2,3 ) returns value of true,\n"  
           << "where kc2 is the function object of hm2."  
           << endl;  
   }  
   else     
   {  
      cout << "kc2( 2,3 ) returns value of false,\n"  
           << "where kc2 is the function object of hm2."  
           << endl;  
   }  
}  
```  
  
##  <a name="key_compare"></a>hash_multimap::key_compare  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 İşlev nesnesi sağlayan bir türü göreli hash_multimap içinde iki öğe sırasını belirlemek için iki sıralama anahtarları karşılaştırabilirsiniz.  
  
```  
typedef Traits key_compare;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 **key_compare** şablon parametresi için bir eş anlamlı olduğundan `Traits`.  
  
 Daha fazla bilgi için `Traits` bkz [hash_multimap sınıfı](../standard-library/hash-multimap-class.md) konu.  
  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [key_comp](#key_comp) bildirme ve kullanma konusunda bir örnek için `key_compare`.  
  
##  <a name="key_type"></a>hash_multimap::key_type  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Hash_multimap her öğeye oluşturduğunu sıralama anahtar nesneyi tanımlayan bir türü.  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `key_type`Şablon parametresi için bir eş anlamlı olduğundan `Key`.  
  
 Daha fazla bilgi için `Key`, Açıklamalar bölümüne bakın [hash_multimap sınıfı](../standard-library/hash-multimap-class.md) konu.  
  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_compare`.  
  
##  <a name="lower_bound"></a>hash_multimap::lower_bound  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Yineleyici eşit veya bundan büyük belirtilen anahtar bir anahtarı olan bir hash_multimap ilk öğe döndürür.  
  
```  
iterator lower_bound(const Key& key);

const_iterator lower_bound(const Key& key) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Aranmakta hash_multimap öğeden sıralama anahtarı ile Karşılaştırılacak bağımsız değişkeni anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir [yineleyici](#iterator) veya [const_iterator](#const_iterator) eşit veya bundan büyük bağımsız değişkeni anahtar ya da son başarılı konumu adresleri bir anahtarla bir hash_multimap bir öğedeki konumunu adresleri anahtar için bir eşleşme varsa hash_multimap öğe.  
  
 Varsa dönüş değerini `lower_bound` atanmış bir `const_iterator`, hash_multimap nesnesi değiştirilemez. Varsa dönüş değerini `lower_bound` atanmış bir **yineleyici**, hash_multimap nesne değiştirilebilir.  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_lower_bound.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1;  
   hash_multimap <int, int> :: const_iterator hm1_AcIter,   
      hm1_RcIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
   hm1.insert ( Int_Pair ( 3, 20 ) );  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   hm1_RcIter = hm1.lower_bound( 2 );  
   cout << "The element of hash_multimap hm1 with a key of 2 is: "  
        << hm1_RcIter -> second << "." << endl;  
  
   hm1_RcIter = hm1.lower_bound( 3 );  
   cout << "The first element of hash_multimap hm1 with a key of 3 is: "  
        << hm1_RcIter -> second << "." << endl;  
  
   // If no match is found for the key, end( ) is returned  
   hm1_RcIter = hm1.lower_bound( 4 );  
  
   if ( hm1_RcIter == hm1.end( ) )  
      cout << "The hash_multimap hm1 doesn't have an element "  
           << "with a key of 4." << endl;  
   else  
      cout << "The element of hash_multimap hm1 with a key of 4 is: "  
           << hm1_RcIter -> second << "." << endl;  
  
   // The element at a specific location in the hash_multimap can be  
   // found using a dereferenced iterator addressing the location  
   hm1_AcIter = hm1.end( );  
   hm1_AcIter--;  
   hm1_RcIter = hm1.lower_bound( hm1_AcIter -> first );  
   cout << "The first element of hm1 with a key matching"  
        << endl << " that of the last element is: "  
        << hm1_RcIter -> second << "." << endl;  
  
   // Note that the first element with a key equal to  
   // the key of the last element is not the last element  
   if ( hm1_RcIter == --hm1.end( ) )  
      cout << "This is the last element of hash_multimap hm1."  
           << endl;  
   else  
      cout << "This is not the last element of hash_multimap hm1."  
           << endl;  
}  
```  
  
```Output  
The element of hash_multimap hm1 with a key of 2 is: 20.  
The first element of hash_multimap hm1 with a key of 3 is: 20.  
The hash_multimap hm1 doesn't have an element with a key of 4.  
The first element of hm1 with a key matching  
 that of the last element is: 20.  
This is not the last element of hash_multimap hm1.  
```  
  
##  <a name="mapped_type"></a>hash_multimap::mapped_type  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Hash_multimap içinde depolanan veri türünü temsil eden tür.  
  
```  
typedef Type mapped_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `mapped_type`Şablon parametresi için bir eş anlamlı olduğundan `Type`.  
  
 Daha fazla bilgi için `Type` bkz [hash_multimap sınıfı](../standard-library/hash-multimap-class.md) konu.  
  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.  
  
##  <a name="max_size"></a>hash_multimap::max_size  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Hash_multimap en büyük uzunluğunu döndürür.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hash_multimap en fazla olası uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_max_size.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1;  
   hash_multimap <int, int> :: size_type i;  
  
   i = hm1.max_size( );  
   cout << "The maximum possible length "  
        << "of the hash_multimap is " << i << "." << endl;  
}  
```  
  
##  <a name="op_eq"></a>hash_multimap::operator =  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Hash_multimap öğelerini başka bir hash_multimap bir kopyası ile değiştirir.  
  
```  
hash_multimap& operator=(const hash_multimap& right);

hash_multimap& operator=(hash_multimap&& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`right`|[Hash_multimap](../standard-library/hash-multimap-class.md) içine kopyalanmasını `hash_multimap`.|  
  
### <a name="remarks"></a>Açıklamalar  
 Var olan öğeleri silindikten sonra bir `hash_multimap`, `operator=` kopyalar ya da içeriğini taşır `right` içine `hash_multimap`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_operator_as.cpp  
// compile with: /EHsc  
#include <hash_multimap>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap<int, int> v1, v2, v3;  
   hash_multimap<int, int>::iterator iter;  
  
   v1.insert(pair<int, int>(1, 10));  
  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << iter->second << " ";  
   cout << endl;  
  
   v2 = v1;  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << iter->second << " ";  
   cout << endl;  
  
// move v1 into v2  
   v2.clear();  
   v2 = move(v1);  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << iter->second << " ";  
   cout << endl;  
}  
```  
  
##  <a name="pointer"></a>hash_multimap::pointer  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Bir hash_multimap bir öğe için bir işaretçi sağlayan türü.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür **işaretçi** bir öğenin değerini değiştirmek için kullanılabilir.  
  
 Çoğu durumda, bir [yineleyici](#iterator) hash_multimap nesnesindeki öğelerin erişmek için kullanılmalıdır.  
  
   
  
##  <a name="rbegin"></a>hash_multimap::rbegin  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Yineleyici ters hash_multimap ilk öğe adresleme döndürür.  
  
```  
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ters hash_multimap ilk öğe adresleme veya ne adresleme ters çift yönlü yineleyici unreversed hash_multimap son öğesi eklenmiştir.  
  
### <a name="remarks"></a>Açıklamalar  
 `rbegin`Ters hash_multimap ile kullanılan gibi [başlamak](#begin) hash_multimap ile kullanılır.  
  
 Varsa dönüş değerini `rbegin` atanmış bir `const_reverse_iterator`, sonra da hash_multimap nesnesi değiştirilemez. Varsa dönüş değerini `rbegin` atandığı bir `reverse_iterator`, sonra hash_multimap nesne değiştirilebilir.  
  
 `rbegin`hash_multimap geriye doğru yinelemek için kullanılabilir.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_rbegin.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1;  
  
   hash_multimap <int, int> :: iterator hm1_Iter;  
   hash_multimap <int, int> :: reverse_iterator hm1_rIter;  
   hash_multimap <int, int> :: const_reverse_iterator hm1_crIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   hm1_rIter = hm1.rbegin( );  
   cout << "The first element of the reversed hash_multimap hm1 is "  
        << hm1_rIter -> first << "." << endl;  
  
   // begin can be used to start an iteration   
   // through a hash_multimap in a forward order  
   cout << "The hash_multimap is: ";  
   for ( hm1_Iter = hm1.begin( ) ; hm1_Iter != hm1.end( ); hm1_Iter++)  
      cout << hm1_Iter -> first << " ";  
      cout << "." << endl;  
  
   // rbegin can be used to start an iteration   
   // through a hash_multimap in a reverse order  
   cout << "The reversed hash_multimap is: ";  
   for ( hm1_rIter = hm1.rbegin( ) ; hm1_rIter != hm1.rend( ); hm1_rIter++)  
      cout << hm1_rIter -> first << " ";  
      cout << "." << endl;  
  
   // A hash_multimap element can be erased by dereferencing its key   
   hm1_rIter = hm1.rbegin( );  
   hm1.erase ( hm1_rIter -> first );  
  
   hm1_rIter = hm1.rbegin( );  
   cout << "After the erasure, the first element"  
        << "\n in the reversed hash_multimap is "  
        << hm1_rIter -> first << "." << endl;  
}  
```  
  
```Output  
The first element of the reversed hash_multimap hm1 is 3.  
The hash_multimap is: 1 2 3 .  
The reversed hash_multimap is: 3 2 1 .  
After the erasure, the first element  
 in the reversed hash_multimap is 2.  
```  
  
##  <a name="reference"></a>hash_multimap::Reference  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Hash_multimap içinde depolanan bir öğe için bir başvuru sağlar türü.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::reference reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_reference.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
  
   // Declare and initialize a const_reference &Ref1   
   // to the key of the first element  
   const int &Ref1 = ( hm1.begin( ) -> first );  
  
   // The following line would cause an error as the   
   // non-const_reference cannot be used to access the key  
   // int &Ref1 = ( hm1.begin( ) -> first );  
  
   cout << "The key of first element in the hash_multimap is "  
        << Ref1 << "." << endl;  
  
   // Declare and initialize a reference &Ref2   
   // to the data value of the first element  
   int &Ref2 = ( hm1.begin( ) -> second );  
  
   cout << "The data value of first element in the hash_multimap is "  
        << Ref2 << "." << endl;  
  
   //The non-const_reference can be used to modify the   
   //data value of the first element  
   Ref2 = Ref2 + 5;  
   cout << "The modified data value of first element is "  
        << Ref2 << "." << endl;  
}  
```  
  
```Output  
The key of first element in the hash_multimap is 1.  
The data value of first element in the hash_multimap is 10.  
The modified data value of first element is 15.  
```  
  
##  <a name="rend"></a>hash_multimap::rend  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Ters hash_multimap son öğesi başarılı konumu adresleri yineleyici döndürür.  
  
```  
const_reverse_iterator rend() const;

reverse_iterator rend();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ters hash_multimap (ilk öğe unreversed hash_multimap öncesinde konum) son öğesi başarılı konumu adresleri ters çift yönlü yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 `rend`Ters hash_multimap ile kullanılan gibi [son](#end) hash_multimap ile kullanılır.  
  
 Varsa dönüş değerini `rend` atanmış bir [const_reverse_iterator](#const_reverse_iterator), sonra da hash_multimap nesnesi değiştirilemez. Varsa dönüş değerini `rend` atandığı bir [reverse_iterator](#reverse_iterator), sonra hash_multimap nesne değiştirilebilir.  
  
 `rend`Ters yineleyici kendi hash_multimap sonuna olup ulaştı için test etmek için kullanılabilir.  
  
 Tarafından döndürülen değer `rend` değil başvuru yapıldı.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_rend.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1;  
  
   hash_multimap <int, int> :: iterator hm1_Iter;  
   hash_multimap <int, int> :: reverse_iterator hm1_rIter;  
   hash_multimap <int, int> :: const_reverse_iterator hm1_crIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
  
   hm1_rIter = hm1.rend( );  
   hm1_rIter--;  
   cout << "The last element of the reversed hash_multimap hm1 is "  
        << hm1_rIter -> first << "." << endl;  
  
   // begin can be used to start an iteration   
   // through a hash_multimap in a forward order  
   cout << "The hash_multimap is: ";  
   for ( hm1_Iter = hm1.begin( ) ; hm1_Iter != hm1.end( ); hm1_Iter++)  
      cout << hm1_Iter -> first << " ";  
      cout << "." << endl;  
  
   // rbegin can be used to start an iteration   
   // through a hash_multimap in a reverse order  
   cout << "The reversed hash_multimap is: ";  
   for ( hm1_rIter = hm1.rbegin( ) ; hm1_rIter != hm1.rend( ); hm1_rIter++)  
      cout << hm1_rIter -> first << " ";  
      cout << "." << endl;  
  
   // A hash_multimap element can be erased by dereferencing its key   
   hm1_rIter = --hm1.rend( );  
   hm1.erase ( hm1_rIter -> first );  
  
   hm1_rIter = hm1.rend( );  
   hm1_rIter--;  
   cout << "After the erasure, the last element "  
        << "in the reversed hash_multimap is "  
        << hm1_rIter -> first << "." << endl;  
}  
```  
  
```Output  
The last element of the reversed hash_multimap hm1 is 1.  
The hash_multimap is: 1 2 3 .  
The reversed hash_multimap is: 3 2 1 .  
After the erasure, the last element in the reversed hash_multimap is 2.  
```  
  
##  <a name="reverse_iterator"></a>hash_multimap::reverse_iterator  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Okuma veya ters hash_multimap bir öğedeki değiştirmek için bir çift yönlü yineleyici sağlayan türü.  
  
```  
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `reverse_iterator` ters hash_multimap yinelemek için kullanılır.  
  
 `reverse_iterator` Nesnelerin hash_multimap noktalarına tarafından tanımlanan [value_type](#value_type), türü olan `pair` \< **const anahtar, türü**>. Anahtar değeri ilk üye çifti kullanılabilir ve eşlenen öğesinin değeri çifti ikinci üyesi üzerinden kullanılabilir.  
  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [rbegin](#rbegin) bildirme ve kullanma konusunda bir örnek için `reverse_iterator`.  
  
##  <a name="size"></a>hash_multimap::size  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Hash_multimap öğe sayısını döndürür.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hash_multimap geçerli uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  Aşağıdaki örnek hash_multimap::size üye fonksiyonu kullanımını göstermektedir.  
  
```  
// hash_multimap_size.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
    using namespace std;  
    using namespace stdext;  
    hash_multimap<int, int> hm1, hm2;  
    hash_multimap<int, int>::size_type i;  
    typedef pair<int, int> Int_Pair;  
  
    hm1.insert(Int_Pair(1, 1));  
    i = hm1.size();  
    cout << "The hash_multimap length is " << i << "." << endl;  
  
    hm1.insert(Int_Pair(2, 4));  
    i = hm1.size();  
    cout << "The hash_multimap length is now " << i << "." << endl;  
}  
```  
  
```Output  
The hash_multimap length is 1.  
The hash_multimap length is now 2.  
```  
  
##  <a name="size_type"></a>hash_multimap::size_type  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Bir hash_multimap öğelerin sayısını sayar bir işaretsiz tamsayı türü.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [boyutu](#size) bildirme ve kullanma örneği`size_type`  
  
##  <a name="swap"></a>hash_multimap::Swap  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 İki hash_multimaps öğelerini değiş tokuş eder.  
  
```  
void swap(hash_multimap& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Öğeleri takas için sağlama hash_multimap veya hash_multimap olanlar değiştirilmek üzere öğeleri olan hash_multimap.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini hiçbir başvuruları, işaretçileri veya öğeleri arasında alınıp verilen iki hash_multimaps öğelerinde tanımladığınız yineleyiciler geçersiz kılar.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_swap.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1, hm2, hm3;  
   hash_multimap <int, int>::iterator hm1_Iter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
   hm2.insert ( Int_Pair ( 10, 100 ) );  
   hm2.insert ( Int_Pair ( 20, 200 ) );  
   hm3.insert ( Int_Pair ( 30, 300 ) );  
  
   cout << "The original hash_multimap hm1 is:";  
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )  
      cout << " " << hm1_Iter -> second;  
   cout   << "." << endl;  
  
   // This is the member function version of swap  
   hm1.swap( hm2 );  
  
   cout << "After swapping with hm2, hash_multimap hm1 is:";  
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )  
      cout << " " << hm1_Iter -> second;  
   cout  << "." << endl;  
  
   // This is the specialized template version of swap  
   swap( hm1, hm3 );  
  
   cout << "After swapping with hm3, hash_multimap hm1 is:";  
   for ( hm1_Iter = hm1.begin( ); hm1_Iter != hm1.end( ); hm1_Iter++ )  
      cout << " " << hm1_Iter -> second;  
   cout   << "." << endl;  
}  
```  
  
```Output  
The original hash_multimap hm1 is: 10 20 30.  
After swapping with hm2, hash_multimap hm1 is: 100 200.  
After swapping with hm3, hash_multimap hm1 is: 300.  
```  
  
##  <a name="upper_bound"></a>hash_multimap::upper_bound  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Belirtilen anahtar daha büyük bir anahtara sahip bir hash_multimap ilk öğe yineleyici döndürür.  
  
```  
iterator upper_bound(const Key& key);

const_iterator upper_bound(const Key& key) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Aranmakta hash_multimap öğeden sıralama anahtarı ile Karşılaştırılacak bağımsız değişkeni anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir [yineleyici](#iterator) veya [const_iterator](#const_iterator) bağımsız değişkeni anahtarından daha büyük ya da son öğesi başarılı konumu adresleri bir anahtara sahip bir öğe bir hash_multimap konumunu adresleri hash_multimap anahtar için bir eşleşme.  
  
 Varsa dönüş değerini `upper_bound` atanmış bir `const_iterator`, hash_multimap nesnesi değiştirilemez. Varsa dönüş değerini `upper_bound` atanmış bir **yineleyici**, hash_multimap nesne değiştirilebilir.  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_upper_bound.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1;  
   hash_multimap <int, int> :: const_iterator hm1_AcIter, hm1_RcIter;  
   typedef pair <int, int> Int_Pair;  
  
   hm1.insert ( Int_Pair ( 1, 10 ) );  
   hm1.insert ( Int_Pair ( 2, 20 ) );  
   hm1.insert ( Int_Pair ( 3, 30 ) );  
   hm1.insert ( Int_Pair ( 3, 40 ) );  
  
   hm1_RcIter = hm1.upper_bound( 1 );  
   cout << "The 1st element of hash_multimap hm1 with "  
        << "a key greater than 1 is: "  
        << hm1_RcIter -> second << "." << endl;  
  
   hm1_RcIter = hm1.upper_bound( 2 );  
   cout << "The first element of hash_multimap hm1\n with a key "  
        << " greater than 2 is: "  
        << hm1_RcIter -> second << "." << endl;  
  
   // If no match is found for the key, end( ) is returned  
   hm1_RcIter = hm1.lower_bound( 4 );  
  
   if ( hm1_RcIter == hm1.end( ) )  
      cout << "The hash_multimap hm1 doesn't have an element "  
           << "with a key of 4." << endl;  
   else  
      cout << "The element of hash_multimap hm1 with a key of 4 is: "  
           << hm1_RcIter -> second << "." << endl;  
  
   // The element at a specific location in the hash_multimap can be  
   // found using a dereferenced iterator addressing the location  
   hm1_AcIter = hm1.begin( );  
   hm1_RcIter = hm1.upper_bound( hm1_AcIter -> first );  
   cout << "The first element of hm1 with a key greater than"  
        << endl << " that of the initial element of hm1 is: "  
        << hm1_RcIter -> second << "." << endl;  
}  
```  
  
```Output  
The 1st element of hash_multimap hm1 with a key greater than 1 is: 20.  
The first element of hash_multimap hm1  
 with a key  greater than 2 is: 30.  
The hash_multimap hm1 doesn't have an element with a key of 4.  
The first element of hm1 with a key greater than  
 that of the initial element of hm1 is: 20.  
```  
  
##  <a name="value_comp"></a>hash_multimap::value_comp  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Üye işlevini anahtar değerlerine karşılaştırarak bir hash_multimap öğelerin sırasını belirleyen bir işlev nesnesi döndürür.  
  
```  
value_compare value_comp() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri sıralamak için bir hash_multimap kullanan karşılaştırma işlevi nesnesini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir hash_multimap için *m*, iki öğe *e*1 ( *k*1 *, d*1) ve *e*2 ( *k*2 *, d*2) türündeki nesneler [value_type](#value_type), burada *k*1 ve *k*2 olan kendi anahtarları türü [key_type](#key_type) ve `d`1 ve `d`2 kendi veri türü olan [mapped_type](#mapped_type), ardından *m.*`value_comp`() ( *e*1 *, e*olan 2) eşdeğer *m.*`key_comp`() ( *k*1 *, k*2). Üye işlevini saklanan bir nesne tanımlar  
  
 **bool işleci**( **value_type &**`left`, **value_type &** `right`);  
  
 döndüren **true** , anahtar değeri `left` önündeki ve anahtar değerine eşit değil `right` sıralama düzeninde.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_value_comp.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
  
   hash_multimap <int, int, hash_compare<int, less<int>>> hm1;  
   hash_multimap <int, int, hash_compare<int, less<int>>   
      >::value_compare vc1 = hm1.value_comp( );  
   hash_multimap <int,int>::iterator Iter1, Iter2;  
  
   Iter1= hm1.insert ( hash_multimap <int, int> :: value_type ( 1, 10 ) );  
   Iter2= hm1.insert ( hash_multimap <int, int> :: value_type ( 2, 5 ) );  
  
   if( vc1( *Iter1, *Iter2 ) == true )  
   {  
      cout << "The element ( 1,10 ) precedes the element ( 2,5 )."  
           << endl;  
   }  
   else     
   {  
      cout << "The element ( 1,10 ) does "  
           << "not precede the element ( 2,5 )."  
           << endl;  
   }  
  
   if( vc1( *Iter2, *Iter1 ) == true )     
   {  
      cout << "The element ( 2,5 ) precedes the element ( 1,10 )."  
           << endl;  
   }  
   else     
   {  
      cout << "The element ( 2,5 ) does "  
           << "not precede the element ( 1,10 )."  
           << endl;  
   }  
}  
```  
  
##  <a name="value_type"></a>hash_multimap::value_type  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 Hash_multimap içinde depolanan nesne türünü temsil eden tür.  
  
```  
typedef pair<const Key, Type> value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `value_type`çifti olarak bildirilen\<const [key_type](#key_type), [mapped_type](#mapped_type)> ve değil eşleştirin\<key_type, mapped_type > ilişkilendirilebilir kapsayıcı anahtarları değiştirilmedi çünkü nonconstant yineleyici veya reference kullanıyor.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multimap_value_type.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   typedef pair <const int, int> cInt2Int;  
   hash_multimap <int, int> hm1;  
   hash_multimap <int, int> :: key_type key1;  
   hash_multimap <int, int> :: mapped_type mapped1;  
   hash_multimap <int, int> :: value_type value1;  
   hash_multimap <int, int> :: iterator pIter;  
  
   // value_type can be used to pass the correct type  
   // explicitely to avoid implicit type conversion  
   hm1.insert ( hash_multimap <int, int> :: value_type ( 1, 10 ) );  
  
   // Compare another way to insert objects into a hash_multimap  
   hm1.insert ( cInt2Int ( 2, 20 ) );  
  
   // Initializing key1 and mapped1  
   key1 = ( hm1.begin( ) -> first );  
   mapped1 = ( hm1.begin( ) -> second );  
  
   cout << "The key of first element in the hash_multimap is "  
        << key1 << "." << endl;  
  
   cout << "The data value of first element in the hash_multimap is "  
        << mapped1 << "." << endl;  
  
   // The following line would cause an error because  
   // the value_type is not assignable  
   // value1 = cInt2Int ( 4, 40 );  
  
   cout  << "The keys of the mapped elements are:";  
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )  
      cout << " " << pIter -> first;  
   cout << "." << endl;  
  
   cout  << "The values of the mapped elements are:";  
   for ( pIter = hm1.begin( ) ; pIter != hm1.end( ) ; pIter++ )  
      cout << " " << pIter -> second;  
   cout << "." << endl;  
}  
```  
  
```Output  
The key of first element in the hash_multimap is 1.  
The data value of first element in the hash_multimap is 10.  
The keys of the mapped elements are: 1 2.  
The values of the mapped elements are: 10 20.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

