---
title: "hash_multiset sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- hash_set/stdext::hash_multiset
- hash_set/stdext::hash_multiset::allocator_type
- hash_set/stdext::hash_multiset::const_iterator
- hash_set/stdext::hash_multiset::const_pointer
- hash_set/stdext::hash_multiset::const_reference
- hash_set/stdext::hash_multiset::const_reverse_iterator
- hash_set/stdext::hash_multiset::difference_type
- hash_set/stdext::hash_multiset::iterator
- hash_set/stdext::hash_multiset::key_compare
- hash_set/stdext::hash_multiset::key_type
- hash_set/stdext::hash_multiset::pointer
- hash_set/stdext::hash_multiset::reference
- hash_set/stdext::hash_multiset::reverse_iterator
- hash_set/stdext::hash_multiset::size_type
- hash_set/stdext::hash_multiset::value_compare
- hash_set/stdext::hash_multiset::value_type
- hash_set/stdext::hash_multiset::begin
- hash_set/stdext::hash_multiset::cbegin
- hash_set/stdext::hash_multiset::cend
- hash_set/stdext::hash_multiset::clear
- hash_set/stdext::hash_multiset::count
- hash_set/stdext::hash_multiset::crbegin
- hash_set/stdext::hash_multiset::crend
- hash_set/stdext::hash_multiset::emplace
- hash_set/stdext::hash_multiset::emplace_hint
- hash_set/stdext::hash_multiset::empty
- hash_set/stdext::hash_multiset::end
- hash_set/stdext::hash_multiset::equal_range
- hash_set/stdext::hash_multiset::erase
- hash_set/stdext::hash_multiset::find
- hash_set/stdext::hash_multiset::get_allocator
- hash_set/stdext::hash_multiset::insert
- hash_set/stdext::hash_multiset::key_comp
- hash_set/stdext::hash_multiset::lower_bound
- hash_set/stdext::hash_multiset::max_size
- hash_set/stdext::hash_multiset::rbegin
- hash_set/stdext::hash_multiset::rend
- hash_set/stdext::hash_multiset::size
- hash_set/stdext::hash_multiset::swap
- hash_set/stdext::hash_multiset::upper_bound
- hash_set/stdext::hash_multiset::value_comp
dev_langs:
- C++
helpviewer_keywords:
- stdext::hash_multiset
- stdext::hash_multiset::allocator_type
- stdext::hash_multiset::const_iterator
- stdext::hash_multiset::const_pointer
- stdext::hash_multiset::const_reference
- stdext::hash_multiset::const_reverse_iterator
- stdext::hash_multiset::difference_type
- stdext::hash_multiset::iterator
- stdext::hash_multiset::key_compare
- stdext::hash_multiset::key_type
- stdext::hash_multiset::pointer
- stdext::hash_multiset::reference
- stdext::hash_multiset::reverse_iterator
- stdext::hash_multiset::size_type
- stdext::hash_multiset::value_compare
- stdext::hash_multiset::value_type
- stdext::hash_multiset::begin
- stdext::hash_multiset::cbegin
- stdext::hash_multiset::cend
- stdext::hash_multiset::clear
- stdext::hash_multiset::count
- stdext::hash_multiset::crbegin
- stdext::hash_multiset::crend
- stdext::hash_multiset::emplace
- stdext::hash_multiset::emplace_hint
- stdext::hash_multiset::empty
- stdext::hash_multiset::end
- stdext::hash_multiset::equal_range
- stdext::hash_multiset::erase
- stdext::hash_multiset::find
- stdext::hash_multiset::get_allocator
- stdext::hash_multiset::insert
- stdext::hash_multiset::key_comp
- stdext::hash_multiset::lower_bound
- stdext::hash_multiset::max_size
- stdext::hash_multiset::rbegin
- stdext::hash_multiset::rend
- stdext::hash_multiset::size
- stdext::hash_multiset::swap
- stdext::hash_multiset::upper_bound
- stdext::hash_multiset::value_comp
ms.assetid: 0580397a-a76e-40ad-aea2-5c6f3a9d0a21
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 78fb4998754bc7a4b30a63de166973909d21b68f
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2018
---
# <a name="hashmultiset-class"></a>hash_multiset Sınıfı
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Kapsayıcı sınıfı hash_multiset C++ Standart Kitaplığı, bir uzantısıdır ve hızlı alınması bulunan öğeleri değerlerini anahtar değerleri hizmet ve benzersiz olması için gerekli olmayan bir koleksiyon verileri ve depolama için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Key, class Traits =hash_compare<Key, less <Key>>, class Allocator =allocator <Key>>  
class hash_multiset  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Key*  
 Hash_multiset depolanması için öğe veri türü.  
  
 `Traits`  
 İki işlev nesneleri içeren, bir sınıfın karşılaştırma türü olan tekli bir koşul eşlemesi anahtar değerleri işaretsiz öğelere, bir karma işlevi ve göreli sıralarına belirlemek için sıralama anahtarları olarak iki öğenin değerleri karşılaştırmak için bir ikili karşılaştırma Tamsayı türünde **size_t**. Bu bağımsız değişken isteğe bağlıdır ve `hash_compare` *< anahtar* **daha az ***\<anahtar >>* varsayılan değerdir.  
  
 `Allocator`  
 Hash_multiset's ayırma ve bellek ayırmayı kaldırma hakkında ayrıntılar yalıtan saklı ayırıcısı nesneyi temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **ayırıcısı ***\<anahtar >.*  
  
## <a name="remarks"></a>Açıklamalar  
 Hash_multiset aşağıdaki gibidir:  
  
-   İlişkili bir anahtar değerine dayalı öğe değerlerinin verimli alınmasını destekleyen bir değişken boyutu kapsayıcı olan ilişkilendirilebilir bir kapsayıcı. Dahası, basit bir ilişkilendirilebilir kapsayıcıdır, çünkü öğelerinin değerleri kendi anahtar değerleridir.  
  
-   Çift yönlüdür, çünkü öğelerine erişmek için çift yönlü bir yineleyici sağlar.  
  
-   Karma, öğelerin anahtar değerleri için uygulanan bir karma işlevine değere göre demet içine öğeleri gruplandırıldığından.  
  
-   Benzersizdir, çünkü öğelerinin her birinde benzersiz bir anahtar olması gerekir. Hash_multiset da basit bir ilişkilendirilebilir kapsayıcı olduğundan, öğeleri de benzersizdir.  
  
-   İşlevselliği sağladığından genel ve bu nedenle bağımsız öğeleri veya anahtarları olarak bulunan verileri, belirli türde bir şablon sınıfı. Öğeler ve anahtarlar için kullanılacak veri türleri, karşılaştırma işlevi ve ayırıcı ile birlikte bir sınıf şablonunda parametreler olarak belirtilir.  
  
 Sıralama üzerinden karma ana avantajı, verimliliği olmasıdır: başarılı karma eklemeler, silmeler gerçekleştirir ve bir süre karşılaştırıldığında sabit ortalama süre sıralamak için kapsayıcısında öğe sayısını logaritmasını orantılı bulur teknikler. Bir kümedeki bir öğenin değeri doğrudan değiştirilemez. Bunun yerine, eski değerleri silmeniz ve yeni değerlere sahip öğeler eklemeniz gerekir.  
  
 Kapsayıcı türünün seçimi genelde uygulamanın gerektirdiği arama ve ekleme türüne dayalı olmalıdır. Karma ilişkilendirilebilir kapsayıcıları, arama, ekleme ve kaldırma işlemleri için en iyi duruma getirilir. Açıkça işlemlerini destekleyen üye işlevleri, bunları ortalama sabit ve kapsayıcı öğe sayısı bağımlı bir süre içinde gerçekleştirdiğiniz bir iyi tasarlanmış karma işlevi ile kullanıldığında verimlidir. İyi tasarlanmış karma işlevi karma değerleri Tekdüzen dağıtımını oluşturur ve çakışma, burada bir çakışma DISTINCT anahtar değerleri aynı karma değer eşlenir ortaya söylenir sayısını en aza indirir. En kötü durumda, en kötü olası karma işlevi ile işlemlerinin sayısı (doğrusal saati) dizisindeki öğelerin sayısı orantılıdır.  
  
 Hash_multiset değerleri kendi anahtarlarla ilişkilendirme koşullar olduğunda tercih ilişkilendirilebilir kapsayıcı uygulama tarafından karşılayan olmalıdır. Bir hash_multiset öğeleri birden çok ve anahtarları benzersiz olmayan şekilde kendi sıralama anahtarı olarak hizmet olabilir. Bu tür bir yapı modeli, sözcüklerin birden çok defa geçebildiği sıralı bir sözcükler listesindedir. Bir hash_set uygun bir kapsayıcı yapısı olabilirdi sonra sözcükleri birden çok tekrarı, izin değil. Benzersiz tanımları benzersiz anahtar sözcüklerin listesini değerleri olarak bağlıymış bir hash_map bu verileri içerecek şekilde uygun bir yapı olacaktır. Bunun yerine tanımları benzersiz değil, bir hash_multimap tercih kapsayıcı olacaktır.  
  
 Hash_multiset denetimleri depolanan karma nitelikler nesne türü çağırarak dizisi siparişleri [value_compare](#value_compare). Üye işlevini çağırarak bu saklı nesne erişilebileceği [key_comp](#key_comp). Bu tür bir işlev nesnesi sınıfın bir nesnesi olarak aynı şekilde davranır gerekir `hash_compare` *< anahtar* **daha az ***\<anahtar >>.* Özellikle, tüm değerler için *anahtar* türü **anahtar**, çağrı **ayırdedici nitelik**( *anahtar*) bir dağıtım türü değerlerinverir**size_t**.  
  
 Genelde, bu sıralamayı oluşturmak için öğelerin yalnızca küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu, denk olmayan öğeler arasında bir sıralamaya neden olur. Daha teknik bir not üzerinde, karşılaştırma işlevi standart matematiksel anlamda katı bir zayıf sıralama sevk eden ikili bir koşuldur. İkili karşılaştırma *f*( *x*, *y*) iki bağımsız değişken nesnelere sahip bir işlev nesnesidir x ve y ve true veya false dönüş değeri. İkili karşılaştırma dönüşsüz, ters ve geçişli ve burada iki nesneleri eşdeğer geçişli ise, sıralama katı bir zayıf bir hash_multiset üzerinde uygulanan sıralama olduğu x ve y ne zaman eşdeğer olarak tanımlanan her ikisi de *f* ( *x*, *y*) ve *f*( *y*, *x*) yanlış ise. Anahtarlar arasındaki eşitliğinin daha güçlü koşulu bu denkliğin yerini alırsa, sıralama (içindeki tüm öğelerin birbirine göre sıralanması anlamında) toplam haline gelir ve eşleşen anahtarlar birbirinden ayırt edilemez olacaktır.  
  
 Denetlenen sıradaki öğelerin gerçek sırası karma işlevi, sıralama işlevi ve kapsayıcı nesnesinde depolanan karma tablosu boyutunu bağlıdır. Denetlenen sıradaki öğelerin sırasını genel tahmin edilemez şekilde karma tablo geçerli boyutu saptanamaz. Öğelerin eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; öğelerin kaldırılması yalnızca özellikle kaldırılan öğeleri gösteren yineleyicileri geçersiz kılar.  
  
 Çift yönlü yineleyici hash_multiset sınıfı tarafından sağlanan yineleyici ancak sınıf üyesi işlevleri eklemek ve hash_multiset sahip olan işlevselliği gereksinimlerini daha fazla en az bir daha zayıf bir giriş yineleyici şablonu parametreleri olarak ele sürümleri Bu çift yönlü yineleyiciler sınıfı tarafından garanti. Farklı yineleyici kavramları, işlevselliklerindeki iyileştirmelere göre ilgili bir aile biçimlendirir. Kendi hash_multiset gereksinimlerinin her yineleyici kavramına sahiptir ve bunlarla çalışmak algoritmaları yineleyici türü tarafından sağlanan gereksinimlerini için kendi varsayımlar sınırlamanız gerekir. Bir giriş yineleyicinin bazı nesnelere başvurusunun kaldırılacağı ve dizideki sonraki yineleyiciye artırılabileceği varsayılabilir. Bu işlevlerin en az bir hash_multiset olur, ancak anlamlı yineleyiciler çeşitli hakkında iletişim kurabilmesi için yeterlidir [ `first`, `last`) sınıf üyesi işlevleri bağlamında.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[hash_multiset](#hash_multiset)|Oluşturan bir `hash_multiset` diğer bir deyişle boş veya diğer bir deyişle tüm kopyasını veya başka bir parçası `hash_multiset`.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|Temsil eden bir tür `allocator` için sınıf `hash_multiset` nesnesi.|  
|[const_iterator](#const_iterator)|Çift yönlü yineleyici bu can sağlayan bir türü okuma bir `const` öğesinde `hash_multiset`.|  
|[const_pointer](#const_pointer)|Bir işaretçi sağlayan bir türü bir `const` öğesinde bir `hash_multiset`.|  
|[const_reference](#const_reference)|Bir başvuru sağlayan bir türü bir `const` öğesi saklanan bir `hash_multiset` okumak ve gerçekleştirmek için `const` işlemleri.|  
|[const_reverse_iterator](#const_reverse_iterator)|Herhangi bir çift yönlü yineleyici bu can sağlayan bir türü okuma `const` öğesinde `hash_multiset`.|  
|[difference_type](#difference_type)|Aynı içinde öğelerin adres iki yineleyiciler arasındaki farkı sağlayan bir imzalı tamsayı türü `hash_multiset`.|  
|[iterator](#iterator)|Çift yönlü yineleyici sağlayan bir tür okuma veya herhangi bir öğe değiştirme bir `hash_multiset`.|  
|[key_compare](#key_compare)|Göreli içinde iki öğe sırasını belirlemek için iki sıralama anahtarları karşılaştırabilirsiniz bir işlev nesnesi sağlayan bir türü `hash_multiset`.|  
|[key_type](#key_type)|Bir öğe depolanan bir nesne açıklayan türü bir `hash_set` kapasitesi sıralama anahtarı olarak içinde.|  
|[pointer](#pointer)|Bir öğe için bir işaretçi sağlayan bir türü bir `hash_multiset`.|  
|[reference](#reference)|Depolanmış bir öğe için bir başvuru sağlayan bir türü bir `hash_multiset`.|  
|[reverse_iterator](#reverse_iterator)|Çift yönlü yineleyici sağlayan bir tür okuma veya bir öğedeki bir ters değiştirme `hash_multiset`.|  
|[size_type](#size_type)|Öğe sayısı gösterebilir bir işaretsiz tamsayı türü bir `hash_multiset`.|  
|[value_compare](#value_compare)|İki işlev nesneleri, iki öğenin değerleri karşılaştırabilirsiniz sınıfı karşılaştırma, ikili koşulu sağlayan bir türü bir `hash_multiset` göreli belirlemek için sırası ve bir birli öğeleri karmaları koşul.|  
|[value_type](#value_type)|Bir öğe depolanan bir nesne açıklayan türü bir `hash_multiset` kapasitesi değeri olarak içinde.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[Başlangıç](#begin)|İlk öğe adresleri yineleyici döndürür `hash_multiset`.|  
|[cbegin](#cbegin)|İlk öğe adresleme const yineleyici döndürür `hash_multiset`.|  
|[cend](#cend)|Son öğesi başarılı konumu adresleri const bir yineleyici döndüren bir `hash_multiset`.|  
|[Temizle](#clear)|Tüm öğeleri sildiği bir `hash_multiset`.|  
|[Sayısı](#count)|Öğelerin sayısını döndürür bir `hash_multiset` parametresi belirtilen bir anahtarı olan anahtar eşleşir|  
|[crbegin](#crbegin)|İlk öğe bir ters adresleme const yineleyici döndürür `hash_multiset`.|  
|[crend](#crend)|Son öğesi bir ters başarılı konumu adresleri const bir yineleyici döndürür `hash_multiset`.|  
|[emplace](#emplace)|Yerinde oluşturulan bir öğe ekler bir `hash_multiset`.|  
|[emplace_hint](#emplace_hint)|Yerinde oluşturulan bir öğe ekler bir `hash_multiset`, yerleştirme İpucu ile.|  
|[empty](#empty)|Testleri bir `hash_multiset` boş.|  
|[Bitiş](#end)|Son öğesi başarılı konumu adresleri yineleyici döndüren bir `hash_multiset`.|  
|[equal_range](#equal_range)|Yineleyiciler çifti sırasıyla ilk öğe döndürür bir `hash_multiset` ilk öğe için ve belirtilen anahtar daha büyük bir anahtarla `hash_multiset` eşit veya bundan büyük anahtarı bir anahtara sahip.|  
|[silme](#erase)|Bir öğenin veya bir dizi öğeleri kaldırır bir `hash_multiset` belirtilen konumları veya belirtilen anahtar eşleşen kaldırır öğeleri.|  
|[find](#find)|Bir öğedeki konumunu adresleme yineleyici döndüren bir `hash_multiset` , belirtilen anahtar için eşdeğer bir anahtara sahip.|  
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` oluşturmak için kullanılan nesne `hash_multiset`.|  
|[insert](#insert)|Bir öğenin veya bir dizi elemanlara ekler bir `hash_multiset`.|  
|[key_comp](#key_compare)|Sipariş anahtarlarında kullanılacak karşılaştırma nesnesinin bir kopyasını alır bir `hash_multiset`.|  
|[lower_bound](#lower_bound)|Yineleyici ilk öğe döndürür bir `hash_multiset` eşit veya bundan büyük belirtilen anahtar bir anahtara sahip.|  
|[max_size](#max_size)|En büyük uzunluğunu döndürür `hash_multiset`.|  
|[rbegin](#rbegin)|İlk öğe bir ters adresleme yineleyici döndürür `hash_multiset`.|  
|[rend](#rend)|Son öğesi bir ters başarılı konumu adresleri yineleyici döndürür `hash_multiset`.|  
|[Boyutu](#size)|Öğelerin sayısını döndürür `hash_multiset`.|  
|[Değiştirme](#swap)|İki öğelerini alış verişleri `hash_multiset`s.|  
|[upper_bound](#upper_bound)|Yineleyici ilk öğe döndürür bir `hash_multiset` eşit veya belirtilen anahtar daha büyük bir anahtar ile.|  
|[value_comp](#value_comp)|Karma ve öğe anahtarı değerleri sıralamak için kullanılan karma nitelikler nesnesinin bir kopyasını alır bir `hash_multiset`.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[hash_multiset::operator=](#op_eq)|Hash_multiset öğelerini başka bir hash_multiset bir kopyası ile değiştirir.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<hash_set >  
  
 **Namespace:** stdext  
  
##  <a name="allocator_type"></a>  hash_multiset::allocator_type  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Allocator sınıfı hash_multiset nesnesinin temsil eden tür.  
  
```  
typedef list<typename Traits::value_type, typename Traits::allocator_type>::allocator_type allocator_type;  
```  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [get_allocator](#get_allocator) bir örnek kullanmak için `allocator_type`  
  
##  <a name="begin"></a>  hash_multiset::Begin  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Hash_multiset ilk öğe adresleri yineleyici döndürür.  
  
```  
const_iterator begin() const;

iterator begin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hash_multiset ya da boş bir hash_multiset başarılı konumu ilk öğe adresleme çift yönlü yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa dönüş değerini **başlamak** atanmış bir `const_iterator`, hash_multiset nesnesindeki öğelerin değiştirilemez. Varsa dönüş değerini **başlamak** atanmış bir **yineleyici**, hash_multiset nesnesindeki öğelerin değiştirilebilir.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_begin.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hms1;  
   hash_multiset <int>::iterator hms1_Iter;  
   hash_multiset <int>::const_iterator hms1_cIter;  
  
   hms1.insert( 1 );  
   hms1.insert( 2 );  
   hms1.insert( 3 );  
  
   hms1_Iter = hms1.begin( );  
   cout << "The first element of hms1 is " << *hms1_Iter << endl;  
  
   hms1_Iter = hms1.begin( );  
   hms1.erase( hms1_Iter );  
  
   // The following 2 lines would err because the iterator is const  
   // hms1_cIter = hms1.begin( );  
   // hms1.erase( hms1_cIter );  
  
   hms1_cIter = hms1.begin( );  
   cout << "The first element of hms1 is now " << *hms1_cIter << endl;  
}  
```  
  
```Output  
The first element of hms1 is 1  
The first element of hms1 is now 2  
```  
  
##  <a name="cbegin"></a>  hash_multiset::cbegin  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Hash_multiset ilk öğe adresleri const bir yineleyici döndürür.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk öğe adresleme const bir çift yönlü yineleyici [hash_multiset](../standard-library/hash-multiset-class.md) ya da boş bir başarılı konumu `hash_multiset`.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri ile `cbegin`, öğeleri `hash_multiset` nesnesi değiştirilemez.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_cbegin.cpp  
// compile with: /EHsc  
#include <hash_multiset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hs1;  
   hash_multiset <int>::const_iterator hs1_cIter;  
  
   hs1.insert( 1 );  
   hs1.insert( 2 );  
   hs1.insert( 3 );  
  
   hs1_cIter = hs1.cbegin( );  
   cout << "The first element of hs1 is " << *hs1_cIter << endl;  
}  
```  
  
```Output  
The first element of hs1 is 1  
```  
  
##  <a name="cend"></a>  hash_multiset::cend  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Bir hash_multiset son öğesi başarılı konumu adresleri const bir yineleyici döndürür.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Son öğesi başarılı konumu adresleri const bir çift yönlü yineleyici bir [hash_multiset](../standard-library/hash-multiset-class.md). Varsa `hash_multiset` boş olduğundan `hash_multiset::cend == hash_multiset::begin`.  
  
### <a name="remarks"></a>Açıklamalar  
 `cend` Yineleyici sonuna ulaştı olup olmadığını sınamak için kullanılan kendi `hash_multiset`. Tarafından döndürülen değer `cend` değil başvuru yapıldı.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_cend.cpp  
// compile with: /EHsc  
#include <hash_multiset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hs1;  
   hash_multiset <int> :: const_iterator hs1_cIter;  
  
   hs1.insert( 1 );  
   hs1.insert( 2 );  
   hs1.insert( 3 );  
  
   hs1_cIter = hs1.cend( );  
   hs1_cIter--;  
   cout << "The last element of hs1 is " << *hs1_cIter << endl;  
}  
```  
  
```Output  
The last element of hs1 is 3  
```  
  
##  <a name="clear"></a>  hash_multiset::Clear  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Bir hash_multiset tüm öğeleri siler.  
  
```  
void clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_clear.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hms1;  
  
   hms1.insert( 1 );  
   hms1.insert( 2 );  
  
   cout << "The size of the hash_multiset is initially " << hms1.size( )  
        << "." << endl;  
  
   hms1.clear( );  
   cout << "The size of the hash_multiset after clearing is "   
        << hms1.size( ) << "." << endl;  
}  
```  
  
```Output  
The size of the hash_multiset is initially 2.  
The size of the hash_multiset after clearing is 0.  
```  
  
##  <a name="const_iterator"></a>  hash_multiset::const_iterator  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Çift yönlü yineleyici bu can sağlayan bir türü okuma bir **const** hash_multiset öğesinde.  
  
```  
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_iterator const_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_iterator` bir öğenin değerini değiştirmek için kullanılamaz.  
  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [başlamak](#begin) kullanarak bir örnek için `const_iterator`.  
  
##  <a name="const_pointer"></a>  hash_multiset::const_pointer  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Bir işaretçi sağlayan bir türü bir **const** bir hash_multiset öğesinde.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_pointer` bir öğenin değerini değiştirmek için kullanılamaz.  
  
 Çoğu durumda, bir [const_iterator](#const_iterator) öğeleri erişmek üzere kullanılması bir **const** hash_multiset nesnesi.  
  
   
  
##  <a name="const_reference"></a>  hash_multiset::const_reference  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Bir başvuru sağlayan bir türü bir **const** okumak ve gerçekleştirmek için bir hash_multiset depolanan öğesi **const** işlemleri.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_const_reference.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hms1;  
  
   hms1.insert( 10 );  
   hms1.insert( 20 );  
  
   // Declare and initialize a const_reference &Ref1   
   // to the 1st element  
   const int &Ref1 = *hms1.begin( );  
  
   cout << "The first element in the hash_multiset is "  
        << Ref1 << "." << endl;  
  
   // The following line would cause an error because the   
   // const_reference cannot be used to modify the hash_multiset  
   // Ref1 = Ref1 + 5;  
}  
```  
  
```Output  
The first element in the hash_multiset is 10.  
```  
  
##  <a name="const_reverse_iterator"></a>  hash_multiset::const_reverse_iterator  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Herhangi bir çift yönlü yineleyici bu can sağlayan bir türü okuma **const** hash_multiset öğesinde.  
  
```  
typedef list<typename Traits::value_type, typename Traits::allocator_type>::const_reverse_iterator const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_reverse_iterator` bir öğenin değerini değiştiremez ve kullanın ters hash_multiset yinelemek için.  
  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [rend](#rend) bildirme ve kullanma konusunda bir örnek için `const_reverse_iterator`.  
  
##  <a name="count"></a>  hash_multiset::count  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Parametresi belirtilen bir anahtarı olan anahtarla eşleşen bir hash_multiset öğe sayısını döndürür.  
  
```  
size_type count(const Key& key) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Öğeleri hash_multiset eşleştirilmesi için anahtar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hash_multiset parametresi belirtilen anahtara sahip öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi aşağıdaki aralıkta öğe sayısını döndürür:  
  
 [ `lower_bound` (_ `Key` ), `upper_bound` (\_ `Key` ) ).  
  
   
  
### <a name="example"></a>Örnek  
  Aşağıdaki örnek hash_multiset::count üye fonksiyonu kullanımını göstermektedir.  
  
```  
// hash_multiset_count.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
    using namespace std;  
    using namespace stdext;  
    hash_multiset<int> hms1;  
    hash_multiset<int>::size_type i;  
  
    hms1.insert(1);  
    hms1.insert(1);  
  
    // Keys do not need to be unique in hash_multiset,  
    // so duplicates may exist.  
    i = hms1.count(1);  
    cout << "The number of elements in hms1 with a sort key of 1 is: "  
         << i << "." << endl;  
  
    i = hms1.count(2);  
    cout << "The number of elements in hms1 with a sort key of 2 is: "  
         << i << "." << endl;  
}  
```  
  
```Output  
The number of elements in hms1 with a sort key of 1 is: 2.  
The number of elements in hms1 with a sort key of 2 is: 0.  
```  
  
##  <a name="crbegin"></a>  hash_multiset::crbegin  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Ters hash_multiset ilk öğe adresleme const yineleyici döndürür.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir const ters ilk öğe bir ters adresleme çift yönlü yineleyici [hash_multiset](../standard-library/hash-multiset-class.md) veya ne son öğesi unreversed olsaydı adresleme `hash_multiset`.  
  
### <a name="remarks"></a>Açıklamalar  
 `crbegin` kullanılan bir ters ile `hash_multiset` gibi [hash_multiset::begin](#begin) ile kullanılan bir `hash_multiset`.  
  
 Dönüş değeri ile `crbegin`, `hash_multiset` nesnesi değiştirilemez.  
  
 `crbegin` yinelemek için kullanılabilecek bir `hash_multiset` geriye doğru.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_crbegin.cpp  
// compile with: /EHsc  
#include <hash_multiset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hs1;  
   hash_multiset <int>::const_reverse_iterator hs1_crIter;  
  
   hs1.insert( 10 );  
   hs1.insert( 20 );  
   hs1.insert( 30 );  
  
   hs1_crIter = hs1.crbegin( );  
   cout << "The first element in the reversed hash_multiset is "  
        << *hs1_crIter << "." << endl;  
}  
```  
  
```Output  
The first element in the reversed hash_multiset is 30.  
```  
  
##  <a name="crend"></a>  hash_multiset::crend  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Ters hash_multiset son öğesi başarılı konumu adresleri const bir yineleyici döndürür.  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir const ters son öğesi bir ters başarılı konumu adresleri çift yönlü yineleyici [hash_multiset](../standard-library/hash-multiset-class.md) (ilk öğe unreversed öncesinde konumu `hash_multiset`).  
  
### <a name="remarks"></a>Açıklamalar  
 `crend` kullanılan bir ters ile `hash_multiset` gibi [hash_multiset::end](#end) ile kullanılan bir `hash_multiset`.  
  
 Dönüş değeri ile `crend`, `hash_multiset` nesnesi değiştirilemez.  
  
 `crend` Ters yineleyici kendi hash_multiset sonuna olup ulaştı için test etmek için kullanılabilir.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_crend.cpp  
// compile with: /EHsc  
#include <hash_multiset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hs1;  
   hash_multiset <int>::const_reverse_iterator hs1_crIter;  
  
   hs1.insert( 10 );  
   hs1.insert( 20 );  
   hs1.insert( 30 );  
  
   hs1_crIter = hs1.crend( );  
   hs1_crIter--;  
   cout << "The last element in the reversed hash_multiset is "  
        << *hs1_crIter << "." << endl;  
}  
```  
  
```Output  
The last element in the reversed hash_multiset is 10.  
```  
  
##  <a name="difference_type"></a>  hash_multiset::difference_type  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Aynı hash_multiset içinde öğelerin adres iki yineleyiciler arasındaki farkı sağlayan imzalı tamsayı türü.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `difference_type` Türü çıkarılmasıyla veya kapsayıcı yineleyiciler artırma döndürülür. `difference_type` Genellikle aralığında öğe sayısını temsil etmek için kullanılan [ `first`, `last`) yineleyiciler arasında `first` ve `last`, gösterdiği öğesi içerir `first` ve öğeleri kadar aralığı , ancak değil de dahil olmak üzere, gösterdiği öğesi `last`.  
  
 Ancak unutmayın `difference_type` kümesi gibi ters çevrilebilir kapsayıcıları tarafından desteklenen çift yönlü yineleyiciler sınıfı içeren bir giriş yineleyici gereksinimlerini karşılayan tüm yineleyiciler için kullanılabilir. Çıkarma yineleyiciler arasında yalnızca bir rastgele erişim kapsayıcı vektör veya deque gibi tarafından sağlanan rasgele erişim yineleyiciler tarafından desteklenir.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <hash_set>  
#include <algorithm>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
  
   hash_multiset <int> hms1;  
   hash_multiset <int>::iterator hms1_Iter, hms1_bIter, hms1_eIter;  
  
   hms1.insert( 20 );  
   hms1.insert( 10 );  
  
   // hash_multiset elements need not be unique  
   hms1.insert( 20 );  
  
   hms1_bIter = hms1.begin( );  
   hms1_eIter = hms1.end( );  
  
   hash_multiset <int>::difference_type   df_typ5, df_typ10,  
        df_typ20;  
  
   df_typ5 = count( hms1_bIter, hms1_eIter, 5 );  
   df_typ10 = count( hms1_bIter, hms1_eIter, 10 );  
   df_typ20 = count( hms1_bIter, hms1_eIter, 20 );  
  
   // The keys & hence the elements of a hash_multiset  
   // need not be unique and may occur multiple times  
   cout << "The number '5' occurs " << df_typ5  
        << " times in hash_multiset hms1.\n";  
   cout << "The number '10' occurs " << df_typ10  
        << " times in hash_multiset hms1.\n";  
   cout << "The number '20' occurs " << df_typ20  
        << " times in hash_multiset hms1.\n";  
  
   // Count the number of elements in a hash_multiset  
   hash_multiset <int>::difference_type  df_count = 0;  
   hms1_Iter = hms1.begin( );  
   while ( hms1_Iter != hms1_eIter)  
   {  
      df_count++;  
      hms1_Iter++;  
   }  
  
   cout << "The number of elements in the hash_multiset hms1 is "   
        << df_count << "." << endl;  
}  
```  
  
```Output  
The number '5' occurs 0 times in hash_multiset hms1.  
The number '10' occurs 1 times in hash_multiset hms1.  
The number '20' occurs 2 times in hash_multiset hms1.  
The number of elements in the hash_multiset hms1 is 3.  
```  
  
##  <a name="emplace"></a>  hash_multiset::emplace  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Hash_multiset yerinde oluşturulan bir öğe ekler.  
  
```  
template <class ValTy>  
iterator insert(ValTy&& val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`val`|İçine Eklenecek öğenin değerini [hash_multiset](../standard-library/hash-multiset-class.md) sürece `hash_multiset` o öğeye veya daha genel anahtar eşdeğer sıralanmış bir öğe zaten içeriyor.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `emplace` Üye işlevi yeni öğe eklenir burada konumuna işaret eden bir yineleyici döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_emplace.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
#include <string>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset<string> hms3;  
   string str1("a");  
  
   hms3.emplace(move(str1));  
   cout << "After the emplace insertion, hms3 contains "  
      << *hms3.begin() << "." << endl;  
}  
```  
  
```Output  
After the emplace insertion, hms3 contains a.  
```  
  
##  <a name="emplace_hint"></a>  hash_multiset::emplace_hint  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Yerleştirme İpucu ile bir hash_multiset içine yerinde oluşturulan bir öğe ekler.  
  
```  
template <class ValTy>  
iterator insert(
    const_iterator _Where,  
    ValTy&& val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`val`|İçine Eklenecek öğenin değerini [hash_multiset](../standard-library/hash-multiset-class.md) sürece `hash_multiset` o öğeye veya daha genel anahtar eşdeğer sıralanmış bir öğe zaten içeriyor.|  
|`_Where`|Ekleme için doğru noktası aramaya başlamak için koyun. (Ekleme gerçekleşebilir Logaritmik zaman yerine amortized sabit zaman ekleme noktasını hemen izleyen `_Where`.)|  
  
### <a name="return-value"></a>Dönüş Değeri  
 [Hash_multiset::emplace](#emplace) üye işlevinin döndürdüğü burada yeni öğe eklenir içine konumuna işaret eden bir yineleyici `hash_multiset`.  
  
### <a name="remarks"></a>Açıklamalar  
 Ekleme gerçekleşebilir Logaritmik zaman yerine amortized sabit zaman ekleme noktasını hemen izleyen `_Where`.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_emplace_hint.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
#include <string>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset<string> hms1;  
   string str1("a");  
  
   hms1.insert(hms1.begin(), move(str1));  
   cout << "After the emplace insertion, hms1 contains "  
      << *hms1.begin() << "." << endl;  
}  
```  
  
```Output  
After the emplace insertion, hms1 contains a.  
```  
  
##  <a name="empty"></a>  hash_multiset::empty  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Bir hash_multiset boşsa, testleri.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** hash_multiset boşsa; **false** hash_multiset boş olmayan ise.  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_empty.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hms1, hms2;  
   hms1.insert ( 1 );  
  
   if ( hms1.empty( ) )  
      cout << "The hash_multiset hms1 is empty." << endl;  
   else  
      cout << "The hash_multiset hms1 is not empty." << endl;  
  
   if ( hms2.empty( ) )  
      cout << "The hash_multiset hms2 is empty." << endl;  
   else  
      cout << "The hash_multiset hms2 is not empty." << endl;  
}  
```  
  
```Output  
The hash_multiset hms1 is not empty.  
The hash_multiset hms2 is empty.  
```  
  
##  <a name="end"></a>  hash_multiset::End  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Bir hash_multiset son öğesi başarılı konumu adresleri yineleyici döndürür.  
  
```  
const_iterator end() const;

iterator end();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir hash_multiset son öğesi başarılı konumu adresleri çift yönlü yineleyici. Hash_multiset boş, hash_multiset::end ise hash_multiset::begin ==.  
  
### <a name="remarks"></a>Açıklamalar  
 **Son** yineleyici kendi hash_multiset sonuna ulaştı olup olmadığını test etmek için kullanılır. Tarafından döndürülen değer **son** değil başvuru yapıldı.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_end.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hms1;  
   hash_multiset <int> :: iterator hms1_Iter;  
   hash_multiset <int> :: const_iterator hms1_cIter;  
  
   hms1.insert( 1 );  
   hms1.insert( 2 );  
   hms1.insert( 3 );  
  
   hms1_Iter = hms1.end( );  
   hms1_Iter--;  
   cout << "The last element of hms1 is " << *hms1_Iter << endl;  
  
   hms1.erase( hms1_Iter );  
  
   // The following 3 lines would err because the iterator is const  
   // hms1_cIter = hms1.end( );  
   // hms1_cIter--;  
   // hms1.erase( hms1_cIter );  
  
   hms1_cIter = hms1.end( );  
   hms1_cIter--;  
   cout << "The last element of hms1 is now " << *hms1_cIter << endl;  
}  
```  
  
```Output  
The last element of hms1 is 3  
The last element of hms1 is now 2  
```  
  
##  <a name="equal_range"></a>  hash_multiset::equal_range  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Yineleyiciler çifti sırasıyla hash_multiset belirtilen anahtar daha büyük bir anahtarla ilk öğe ve eşit veya bundan büyük anahtarı bir anahtarla hash_multiset ilk öğe döndürür.  
  
```  
pair <const_iterator, const_iterator> equal_range (const Key& key) const;

pair <iterator, iterator> equal_range (const Key& key);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Aranmakta hash_multiset öğeden sıralama anahtarı ile Karşılaştırılacak bağımsız değişkeni anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk olduğu yineleyiciler çifti [lower_bound](#lower_bound) anahtarı ve ikincisi [upper_bound](#upper_bound) anahtarı.  
  
 İlk yineleyici çiftinin erişmek için `pr` üye işlevi tarafından döndürülen, kullanmak `pr`. **İlk** ve alt sınır yineleyici başvurulacak kullanmak \*( `pr`. **first**). İkinci yineleyici çiftinin erişmek için `pr` üye işlevi tarafından döndürülen, kullanmak `pr`. **İkinci** ve üst sınır yineleyici başvurulacak kullanmak \*( `pr`. **İkinci**).  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_equal_range.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   typedef hash_multiset<int> IntHSet;  
   IntHSet hms1;  
   hash_multiset <int> :: const_iterator hms1_RcIter;  
  
   hms1.insert( 10 );  
   hms1.insert( 20 );  
   hms1.insert( 30 );  
  
   pair <IntHSet::const_iterator, IntHSet::const_iterator> p1, p2;  
   p1 = hms1.equal_range( 20 );  
  
   cout << "The upper bound of the element with "  
        << "a key of 20\nin the hash_multiset hms1 is: "  
        << *(p1.second) << "." << endl;  
  
   cout << "The lower bound of the element with "  
        << "a key of 20\nin the hash_multiset hms1 is: "  
        << *(p1.first) << "." << endl;  
  
   // Compare the upper_bound called directly   
   hms1_RcIter = hms1.upper_bound( 20 );  
   cout << "A direct call of upper_bound( 20 ) gives "  
        << *hms1_RcIter << "," << endl  
        << "matching the 2nd element of the pair"  
        << " returned by equal_range( 20 )." << endl;  
  
   p2 = hms1.equal_range( 40 );  
  
   // If no match is found for the key,  
   // both elements of the pair return end( )  
   if ( ( p2.first == hms1.end( ) )   
      && ( p2.second == hms1.end( ) ) )  
      cout << "The hash_multiset hms1 doesn't have an element "  
           << "with a key less than 40." << endl;  
   else  
      cout << "The element of hash_multiset hms1"  
           << "with a key >= 40 is: "  
           << *(p1.first) << "." << endl;  
}  
```  
  
```Output  
The upper bound of the element with a key of 20  
in the hash_multiset hms1 is: 30.  
The lower bound of the element with a key of 20  
in the hash_multiset hms1 is: 20.  
A direct call of upper_bound( 20 ) gives 30,  
matching the 2nd element of the pair returned by equal_range( 20 ).  
The hash_multiset hms1 doesn't have an element with a key less than 40.  
```  
  
##  <a name="erase"></a>  hash_multiset::ERASE  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Bir öğenin veya bir dizi öğeleri hash_multiset belirtilen konumlardan kaldırır veya belirtilen anahtar eşleşen öğeleri kaldırır.  
  
```  
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);

size_type erase(const key_type& key);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Where`  
 Hash_multiset kaldırılacak öğe konumu.  
  
 `first`  
 İlk öğenin konumunu hash_multiset kaldırıldı.  
  
 `last`  
 Yalnızca son öğenin ötesinde konumu hash_multiset kaldırıldı.  
  
 `key`  
 Hash_multiset kaldırılacak öğe anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk iki üye işlevleri için çift yönlü Yineleyici, böyle bir öğe varsa, kaldırılan öğelerin ya da bir işaretçi hash_multiset sonuna dışında kalan ilk öğe belirler. Üçüncü üye fonksiyonu için hash_multiset kaldırılan öğelerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevleri hiçbir zaman bir özel durum.  
  
   
  
### <a name="example"></a>Örnek  
  Aşağıdaki örnek hash_multiset::erase üye fonksiyonu kullanımını göstermektedir.  
  
```  
// hash_multiset_erase.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    using namespace stdext;  
    hash_multiset<int> hms1, hms2, hms3;  
    hash_multiset<int> :: iterator pIter, Iter1, Iter2;  
    int i;  
    hash_multiset<int>::size_type n;  
  
    for (i = 1; i < 5; i++)  
    {  
        hms1.insert(i);  
        hms2.insert(i * i);  
        hms3.insert(i - 1);  
    }  
  
    // The 1st member function removes an element at a given position  
    Iter1 = ++hms1.begin();  
    hms1.erase(Iter1);  
  
    cout << "After the 2nd element is deleted,\n "  
         << "the hash_multiset hms1 is:" ;  
    for (pIter = hms1.begin(); pIter != hms1.end(); pIter++)  
        cout << " " << *pIter;  
    cout << "." << endl;  
  
    // The 2nd member function removes elements  
    // in the range [ first,  last)  
    Iter1 = ++hms2.begin();  
    Iter2 = --hms2.end();  
    hms2.erase(Iter1, Iter2);  
  
    cout << "After the middle two elements are deleted,\n "  
         << "the hash_multiset hms2 is:" ;  
    for (pIter = hms2.begin(); pIter != hms2.end(); pIter++)  
        cout << " " << *pIter;  
    cout << "." << endl;  
  
    // The 3rd member function removes elements with a given  key  
    n = hms3.erase(2);  
  
    cout << "After the element with a key of 2 is deleted,\n "  
         << "the hash_multiset hms3 is:" ;  
    for (pIter = hms3.begin(); pIter != hms3.end(); pIter++)  
        cout << " " << *pIter;  
    cout << "." << endl;  
  
    // The 3rd member function returns the number of elements removed  
    cout << "The number of elements removed from hms3 is: "  
         << n << "." << endl;  
  
    // The dereferenced iterator can also be used to specify a key  
    Iter1 = ++hms3.begin();  
    hms3.erase(Iter1);  
  
    cout << "After another element with a key "  
         << "equal to that of the 2nd element\n is deleted, "  
         << "the hash_multiset hms3 is:" ;  
    for (pIter = hms3.begin(); pIter != hms3.end(); pIter++)  
        cout << " " << *pIter;  
    cout << "." << endl;  
}  
```  
  
```Output  
After the 2nd element is deleted,  
 the hash_multiset hms1 is: 1 3 4.  
After the middle two elements are deleted,  
 the hash_multiset hms2 is: 16 4.  
After the element with a key of 2 is deleted,  
 the hash_multiset hms3 is: 0 1 3.  
The number of elements removed from hms3 is: 1.  
After another element with a key equal to that of the 2nd element  
 is deleted, the hash_multiset hms3 is: 0 3.  
```  
  
##  <a name="find"></a>  hash_multiset::Find  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Belirtilen anahtar için eşdeğer bir anahtara sahip bir hash_multiset bir öğedeki konumunu adresleme yineleyici döndürür.  
  
```  
iterator find(const Key& key);

const_iterator find(const Key& key) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Aranmakta hash_multiset öğeden sıralama anahtarı tarafından eşleştirilmesini bağımsız değişkeni anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir [yineleyici](#iterator) veya [const_iterator](#const_iterator) belirtilen anahtar için eşdeğer bir öğe konumu adresleri veya eşleşme yoksa hash_multiset son öğesi başarılı konumu adresleri için anahtar bulunamadı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi olan sıralama anahtarı hash_multiset bir öğedeki adresleri yineleyici döndürür **eşdeğer** bağımsız değişkeni üzerinde daha az bir sıralama uygulanmasını ikili bir koşul altında anahtar temel-comparability ilişkisi daha.  
  
 Varsa dönüş değerini **Bul** atanmış bir `const_iterator`, hash_multiset nesnesi değiştirilemez. Varsa dönüş değerini **Bul** atanmış bir **yineleyici**, hash_multiset nesne değiştirilebilir.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_find.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hms1;  
   hash_multiset <int> :: const_iterator hms1_AcIter, hms1_RcIter;  
  
   hms1.insert( 10 );  
   hms1.insert( 20 );  
   hms1.insert( 30 );  
  
   hms1_RcIter = hms1.find( 20 );  
   cout << "The element of hash_multiset hms1 with a key of 20 is: "  
        << *hms1_RcIter << "." << endl;  
  
   hms1_RcIter = hms1.find( 40 );  
  
   // If no match is found for the key, end( ) is returned  
   if ( hms1_RcIter == hms1.end( ) )  
      cout << "The hash_multiset hms1 doesn't have an element "  
           << "with a key of 40." << endl;  
   else  
      cout << "The element of hash_multiset hms1 with a key of 40 is: "  
           << *hms1_RcIter << "." << endl;  
  
   // The element at a specific location in the hash_multiset can be found   
   // by using a dereferenced iterator addressing the location  
   hms1_AcIter = hms1.end( );  
   hms1_AcIter--;  
   hms1_RcIter = hms1.find( *hms1_AcIter );  
   cout << "The element of hms1 with a key matching "  
        << "that of the last element is: "  
        << *hms1_RcIter << "." << endl;  
}  
```  
  
```Output  
The element of hash_multiset hms1 with a key of 20 is: 20.  
The hash_multiset hms1 doesn't have an element with a key of 40.  
The element of hms1 with a key matching that of the last element is: 30.  
```  
  
##  <a name="get_allocator"></a>  hash_multiset::get_allocator  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Hash_multiset oluşturmak için kullanılan ayırıcısı nesnesinin bir kopyasını döndürür.  
  
```  
Allocator get_allocator() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hash_multiset tarafından sınıfının şablon parametresi bellek yönetmek için kullanılan ayırıcısı `Allocator`.  
  
 Daha fazla bilgi için `Allocator`, Açıklamalar bölümüne bakın [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konu.  
  
### <a name="remarks"></a>Açıklamalar  
 Allocators hash_multiset sınıfı için sınıf depolama nasıl yönettiğini belirtin. C++ Standart Kitaplığı kapsayıcı sınıfları ile sağlanan varsayılan allocators çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak ileri düzeyde C++ bir konudur.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_get_allocator.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
  
   // The following lines declare objects  
   // that use the default allocator.  
   hash_multiset <int, hash_compare <int, less<int> > > hms1;  
   hash_multiset <int, hash_compare <int, greater<int> > > hms2;  
   hash_multiset <double, hash_compare <double,  
      less<double> >, allocator<double> > hms3;  
  
   hash_multiset <int, hash_compare <int,  
      greater<int> > >::allocator_type hms2_Alloc;  
   hash_multiset <double>::allocator_type hms3_Alloc;  
   hms2_Alloc = hms2.get_allocator( );  
  
   cout << "The number of integers that can be allocated"  
        << endl << "before free memory is exhausted: "  
        << hms1.max_size( ) << "." << endl;  
  
   cout << "The number of doubles that can be allocated"  
        << endl << "before free memory is exhausted: "  
        << hms3.max_size( ) <<  "." << endl;  
  
   // The following lines create a hash_multiset hms4  
   // with the allocator of hash_multiset hms1.  
   hash_multiset <int>::allocator_type hms4_Alloc;  
   hash_multiset <int> hms4;  
   hms4_Alloc = hms2.get_allocator( );  
  
   // Two allocators are interchangeable if  
   // storage allocated from each can be  
   // deallocated by the other  
   if( hms2_Alloc == hms4_Alloc )  
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
  
##  <a name="hash_multiset"></a>  hash_multiset::hash_multiset  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Oluşturan bir `hash_multiset` diğer bir deyişle boş veya diğer bir deyişle tüm kopyasını veya başka bir parçası `hash_multiset`.  
  
```  
hash_multiset();

explicit hash_multiset(
    const Traits& Comp);

hash_multiset(
    const Traits& Comp,  
    const Allocator& Al);

hash_multiset(
    const hash_multiset<Key, Traits, Allocator>& Right);

hash_multiset(
    hash_multiset&& Right  
};  
hash_multiset (initializer_list<Type> IList);

hash_multiset(
    initializer_list<Tu[e> IList, const Compare& Comp):  
hash_multiset(
    initializer_list<Type> IList, const Compare& Comp, const Allocator& Al);

template <class InputIterator>  
hash_multiset(
 InputIterator First,  
    InputIterator Last);

template <class InputIterator>  
hash_multiset(
 InputIterator First,  
    InputIterator Last,  
    const Traits& Comp);

template <class InputIterator>  
hash_multiset(
 InputIterator First,  
    InputIterator Last,  
    const Traits& Comp,  
    const Allocator& Al);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Al`|Bunun için kullanılacak depolama allocator sınıfı `hash_multiset` varsayılan olarak nesne `Allocator`.|  
|`Comp`|Türü karşılaştırma işlevinden `const Traits` öğeleri sıralamak için kullanılan `hash_multiset`, varsayılan olarak `hash_compare`.|  
|`Right`|`hash_multiset` Biri oluşturulan `hash_multiset` kopyasını olacak.|  
|`First`|Kopyalanacak öğe aralığını ilk öğe konumu.|  
|`Last`|Kopyalanacak öğeleri aralık ötesinde ilk öğe konumu.|  
|`IList`|Kopyalanacak öğeleri içeren initializer_list.|  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm oluşturucular depolamak için bellek depolama yönetir ayırıcısı nesne türünü `hash_multiset` ve, daha sonra döndürülüp döndürülmediğini çağırarak [hash_multiset::get_allocator](#get_allocator). Allocator parametresi, sınıf bildirimleri ve diğer allocators yerine kullanılacak önişlem makroları genellikle atlanır.  
  
 Tüm oluşturucular kendi hash_multisets başlatır.  
  
 İşlev nesnesi türündeki tüm oluşturucular depolamak `Traits` bir sipariş anahtarlar oluşturmak için kullanılan `hash_multiset` ve, daha sonra döndürülüp döndürülmediğini çağırarak [hash_multiset::key_comp](#key_comp). Daha fazla bilgi için `Traits` bkz [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konu.  
  
 Boş bir başlangıç ilk üç oluşturucular belirleyin `hash_multiset`, ikinci karşılaştırma işlev türünü belirtme ( `Comp`) öğeleri ve üçüncü sırasını açıkça oluşturmada kullanılacak ayırıcı belirtme yazın ( `Al`) kullanılacak. Anahtar sözcüğü `explicit` otomatik tür dönüştürme belirli türdeki gizler.  
  
 Dördüncü Oluşturucusu taşır `hash_multiset` `Right`.  
  
 Beşinci, altıncı ve yedinci oluşturucular bir initializer_list kullanın.  
  
 Aralığın son üç oluşturucuları kopyalama [ `First`, `Last`), bir `hash_multiset` karşılaştırma işlevinden sınıfının Karşılaştır ve ayırıcısı türünü belirleyen içinde explicitness artan.  
  
 Gerçek bir karma kümesi kapsayıcıda öğelerin sırasını sıralama işlevi ve karma tablo boyutunu karma işlevi üzerinde bağlıdır ve sıralama işlevi tarafından belirlendiği kümesi kapsayıcısı ile verebilir gibi genel olarak, tahmin edilemez tek başına.  
  
##  <a name="insert"></a>  hash_multiset::insert  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Bir öğenin veya bir dizi öğeleri hash_multiset ekler.  
  
```  
iterator insert(
    const Type& Val);

iterator insert(
    iterator Where,  
    const Type& Al);

void insert(
    initializer_list<Type> IList);

iterator insert(
    const Type& Val);

iterator insert(
    Iterator Where,   
    const Type& Val);

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
|`Val`|Hash_multiset, öğenin veya daha genel anahtar eşdeğer sıralanmış bir öğe zaten var. sürece hash_multiset Eklenecek öğenin değeri.|  
|`Where`|Ekleme için doğru noktası aramaya başlamak için koyun. (Ekleme gerçekleşebilir Logaritmik zaman yerine amortized sabit zaman ekleme noktasını hemen izleyen `_Where`.)|  
|`First`|Hash_multiset kopyalanacak ilk öğe konumu.|  
|`Last`|Hash_multiset kopyalanmasını yalnızca son öğenin ötesinde konumu.|  
|`IList`|Kopyalanacak öğe içeren initializer_list.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk iki Ekle üye işlevleri burada yeni öğe eklendi konumuna işaret eden bir yineleyici döndür.  
  
 Sonraki üç üye işlevleri bir initializer_list kullanın.  
  
 Üçüncü üye işlevi bir dizi öğesi değerlerini yineleyici aralığında tarafından ele her öğesine karşılık gelen bir hash_multiset ekler [ `First`, `Last`), belirtilen hash_multiset.  
  
### <a name="remarks"></a>Açıklamalar  
 Ekleme gerçekleşebilir Logaritmik zaman yerine INSERT ipucu sürümü amortized sabit zamanında ekleme noktasını hemen izleyen `Where`.  
  
##  <a name="iterator"></a>  hash_multiset::iterator  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Okuma veya herhangi bir hash_multiset öğesinde değiştirmek için bir çift yönlü yineleyici sağlayan türü.  
  
```  
typedef list<typename Traits::value_type, typename Traits::allocator_type>::iterator iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür **yineleyici** bir öğenin değerini değiştirmek için kullanılabilir.  
  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [başlamak](#begin) bildirme ve kullanma konusunda bir örnek için **yineleyici**.  
  
##  <a name="key_comp"></a>  hash_multiset::key_comp  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Bir hash_multiset sipariş anahtarlarında kullanılacak karşılaştırma nesnesinin bir kopyasını alır.  
  
```  
key_compare key_comp() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hash_multiset şablon parametresi döndürür `Traits`, karma ve kapsayıcı öğeleri sıralamak için kullanılan işlev nesneleri içerir.  
  
 Daha fazla bilgi için `Traits` bkz [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konu.  
  
### <a name="remarks"></a>Açıklamalar  
 Saklanan nesne üye işlevi tanımlar:  
  
 **bool işleci**( **const anahtar &** *_xVal,* **const anahtar &** _ `yVal`);  
  
 döndüren **true** varsa `_xVal` önündeki ve eşit değil `_yVal` sıralama düzeninde.  
  
 Unutmayın her ikisi de [key_compare](#key_compare) ve [value_compare](#value_compare) şablon parametresi için eş anlamlı sözcükleri olan **nitelikler**. Her iki tür hash_multiset ve hash_multiset sınıfları, burada ayrı hash_map ve hash_multimap sınıfları ile uyumluluk için aynı oldukları için sağlanır.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_key_comp.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
  
   hash_multiset <int, hash_compare < int, less<int> > >hms1;  
   hash_multiset<int, hash_compare < int, less<int> > >::key_compare kc1  
          = hms1.key_comp( ) ;  
   bool result1 = kc1( 2, 3 ) ;  
   if( result1 == true )  
   {  
      cout << "kc1( 2,3 ) returns value of true, "  
           << "where kc1 is the function object of hms1."  
           << endl;  
   }  
   else  
   {  
      cout << "kc1( 2,3 ) returns value of false "  
           << "where kc1 is the function object of hms1."  
        << endl;  
   }  
  
   hash_multiset <int, hash_compare < int, greater<int> > > hms2;  
   hash_multiset<int, hash_compare < int, greater<int> > >::key_compare  
         kc2 = hms2.key_comp( ) ;  
   bool result2 = kc2( 2, 3 ) ;  
   if( result2 == true )  
   {  
      cout << "kc2( 2,3 ) returns value of true, "  
           << "where kc2 is the function object of hms2."  
           << endl;  
   }  
   else  
   {  
      cout << "kc2( 2,3 ) returns value of false, "  
           << "where kc2 is the function object of hms2."  
           << endl;  
   }  
}  
```  
  
##  <a name="key_compare"></a>  hash_multiset::key_compare  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 İki işlev nesneleri sağlayan bir türü göreli sıralarına belirlemek için bir hash_multiset iki öğenin değerleri karşılaştırabilirsiniz sınıfı karşılaştırma, ikili bir koşul ve öğeleri karmaları birli koşul.  
  
```  
typedef Traits key_compare;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 **key_compare** şablon parametresi için bir eş anlamlı olduğundan `Traits`.  
  
 Daha fazla bilgi için `Traits` bkz [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konu.  
  
 Unutmayın her ikisi de `key_compare` ve value_compare şablon parametresi için eş anlamlı sözcükleri **nitelikler**. Her iki tür ayrı nerede hash_map ve hash_multimap sınıfları ile uyumluluk için aynı oldukları hash_set ve hash_multiset sınıfları için sağlanır.  
  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [key_comp](#key_comp) bildirme ve kullanma konusunda bir örnek için `key_compare`.  
  
##  <a name="key_type"></a>  hash_multiset::key_type  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 İşlev nesnesi sağlayan bir türü göreli hash_multiset içinde iki öğe sırasını belirlemek için sıralama anahtarları karşılaştırabilirsiniz.  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 **key_type** şablon parametresi için bir eş anlamlı olduğundan `Key`.  
  
 Unutmayın her ikisi de `key_type` ve [value_type](../standard-library/hash-set-class.md#value_type) şablon parametresi için eş anlamlı sözcükleri olan **anahtar**. Her iki tür kümesi ve burada ayrı multimap sınıfların ve eşleme ile uyumluluk için aynı oldukları çok kümeli sınıfları için sağlanır.  
  
 Daha fazla bilgi için `Key`, Açıklamalar bölümüne bakın [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konu.  
  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [value_type](#value_type) bildirme ve kullanma konusunda bir örnek için `key_type`.  
  
##  <a name="lower_bound"></a>  hash_multiset::lower_bound  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Yineleyici eşit veya bundan büyük belirtilen anahtar bir anahtarı olan bir hash_multiset ilk öğe döndürür.  
  
```  
const_iterator lower_bound(const Key& key) const;

iterator lower_bound(const Key& key);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Aranmakta hash_multiset öğeden sıralama anahtarı ile Karşılaştırılacak bağımsız değişkeni anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir [yineleyici](#iterator) veya [const_iterator](#const_iterator) eşit veya bundan büyük bağımsız değişkeni anahtar veya konum başarılı adresleri bir anahtarla bir hash_multiset ilk öğe konumu adresleri anahtar için bir eşleşme varsa hash_multiset son öğesi.  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_lower_bound.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main() {  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hms1;  
   hash_multiset <int> :: const_iterator hms1_AcIter, hms1_RcIter;  
  
   hms1.insert( 10 );  
   hms1.insert( 20 );  
   hms1.insert( 30 );  
  
   hms1_RcIter = hms1.lower_bound( 20 );  
   cout << "The element of hash_multiset hms1 with a key of 20 is: "  
        << *hms1_RcIter << "." << endl;  
  
   hms1_RcIter = hms1.lower_bound( 40 );  
  
   // If no match is found for the key, end( ) is returned  
   if ( hms1_RcIter == hms1.end( ) )  
      cout << "The hash_multiset hms1 doesn't have an element "  
           << "with a key of 40." << endl;  
   else  
      cout << "The element of hash_multiset hms1 with a key of 40 is: "  
           << *hms1_RcIter << "." << endl;  
  
   // An element at a specific location in the hash_multiset can be found   
   // by using a dereferenced iterator that addresses the location  
   hms1_AcIter = hms1.end( );  
   hms1_AcIter--;  
   hms1_RcIter = hms1.lower_bound( *hms1_AcIter );  
   cout << "The element of hms1 with a key matching "  
        << "that of the last element is: "  
        << *hms1_RcIter << "." << endl;  
}  
```  
  
##  <a name="max_size"></a>  hash_multiset::max_size  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Hash_multiset en büyük uzunluğunu döndürür.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hash_multiset en fazla olası uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_max_size.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hms1;  
   hash_multiset <int>::size_type i;  
  
   i = hms1.max_size( );     
   cout << "The maximum possible length "  
        << "of the hash_multiset is " << i << "." << endl;  
}  
```  
  
##  <a name="op_eq"></a>  hash_multiset::operator =  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Hash_multiset öğelerini başka bir hash_multiset bir kopyası ile değiştirir.  
  
```  
hash_multiset& operator=(const hash_multiset& right);

hash_multiset& operator=(hash_multiset&& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`right`|[Hash_multiset](../standard-library/hash-multiset-class.md) içine kopyalanmasını `hash_multiset`.|  
  
### <a name="remarks"></a>Açıklamalar  
 Var olan öğeleri silindikten sonra bir `hash_multiset`, `operator=` kopyalar ya da içeriğini taşır `right` içine `hash_multiset`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_operator_as.cpp  
// compile with: /EHsc  
#include <hash_multiset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset<int> v1, v2, v3;  
   hash_multiset<int>::iterator iter;  
  
   v1.insert(10);  
  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << iter << " ";  
   cout << endl;  
  
   v2 = v1;  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << iter << " ";  
   cout << endl;  
  
// move v1 into v2  
   v2.clear();  
   v2 = move(v1);  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << iter << " ";  
   cout << endl;  
}  
```  
  
##  <a name="pointer"></a>  hash_multiset::pointer  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Bir hash_multiset bir öğe için bir işaretçi sağlayan türü.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::pointer pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür **işaretçi** bir öğenin değerini değiştirmek için kullanılabilir.  
  
 Çoğu durumda, bir [yineleyici](#iterator) çok kümeli nesnesindeki öğelerin erişmek için kullanılmalıdır.  
  
   
  
##  <a name="rbegin"></a>  hash_multiset::rbegin  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Yineleyici ters hash_multiset ilk öğe adresleme döndürür.  
  
```  
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ters hash_multiset ilk öğe adresleme veya ne adresleme ters çift yönlü yineleyici unreversed hash_multiset son öğesi eklenmiştir.  
  
### <a name="remarks"></a>Açıklamalar  
 `rbegin` Ters hash_multiset ile kullanılan gibi [başlamak](#begin) hash_multiset ile kullanılır.  
  
 Varsa dönüş değerini `rbegin` atanmış bir `const_reverse_iterator`, sonra da hash_multiset nesnesi değiştirilemez. Varsa dönüş değerini `rbegin` atandığı bir `reverse_iterator`, sonra hash_multiset nesne değiştirilebilir.  
  
 `rbegin` hash_multiset geriye doğru yinelemek için kullanılabilir.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_rbegin.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hms1;  
   hash_multiset <int>::iterator hms1_Iter;  
   hash_multiset <int>::reverse_iterator hms1_rIter;  
  
   hms1.insert( 10 );  
   hms1.insert( 20 );  
   hms1.insert( 30 );  
  
   hms1_rIter = hms1.rbegin( );  
   cout << "The first element in the reversed hash_multiset is "  
        << *hms1_rIter << "." << endl;  
  
   // begin can be used to start an iteration   
   // throught a hash_multiset in a forward order  
   cout << "The hash_multiset is: ";  
   for ( hms1_Iter = hms1.begin( ) ; hms1_Iter != hms1.end( );  
         hms1_Iter++ )  
      cout << *hms1_Iter << " ";  
   cout << endl;  
  
   // rbegin can be used to start an iteration   
   // throught a hash_multiset in a reverse order  
   cout << "The reversed hash_multiset is: ";  
   for ( hms1_rIter = hms1.rbegin( ) ; hms1_rIter != hms1.rend( );  
         hms1_rIter++ )  
      cout << *hms1_rIter << " ";  
   cout << endl;  
  
   // A hash_multiset element can be erased by dereferencing to its key   
   hms1_rIter = hms1.rbegin( );  
   hms1.erase ( *hms1_rIter );  
  
   hms1_rIter = hms1.rbegin( );  
   cout << "After the erasure, the first element "  
        << "in the reversed hash_multiset is "<< *hms1_rIter << "."  
        << endl;  
}  
```  
  
```Output  
The first element in the reversed hash_multiset is 30.  
The hash_multiset is: 10 20 30   
The reversed hash_multiset is: 30 20 10   
After the erasure, the first element in the reversed hash_multiset is 20.  
```  
  
##  <a name="reference"></a>  hash_multiset::Reference  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Hash_multiset içinde depolanan bir öğe için bir başvuru sağlar türü.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::reference reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_reference.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   using namespace stdext;  
   hash_multiset <int> hms1;  
  
   hms1.insert( 10 );  
   hms1.insert( 20 );  
  
   // Declare and initialize a reference &Ref1 to the 1st element  
   int &Ref1 = *hms1.begin( );  
  
   cout << "The first element in the hash_multiset is "  
        << Ref1 << "." << endl;  
  
   // The value of the 1st element of the hash_multiset can be  
   // changed by operating on its (non const) reference  
   Ref1 = Ref1 + 5;  
  
   cout << "The first element in the hash_multiset is now "  
        << *hms1.begin() << "." << endl;  
}  
```  
  
```Output  
The first element in the hash_multiset is 10.  
The first element in the hash_multiset is now 15.  
```  
  
##  <a name="rend"></a>  hash_multiset::rend  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Ters hash_multiset son öğesi başarılı konumu adresleri yineleyici döndürür.  
  
```  
const_reverse_iterator rend() const;

reverse_iterator rend();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ters hash_multiset (ilk öğe unreversed hash_multiset öncesinde konum) son öğesi başarılı konumu adresleri ters çift yönlü yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 `rend` Ters hash_multiset ile kullanılan gibi [son](#end) hash_multiset ile kullanılır.  
  
 Varsa dönüş değerini `rend` atanmış bir `const_reverse_iterator`, sonra da hash_multiset nesnesi değiştirilemez. Varsa dönüş değerini `rend` atandığı bir `reverse_iterator`, sonra hash_multiset nesne değiştirilebilir. Tarafından döndürülen değer `rend` değil başvuru yapıldı.  
  
 `rend` Ters yineleyici kendi hash_multiset sonuna olup ulaştı için test etmek için kullanılabilir.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_rend.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hms1;  
   hash_multiset <int>::iterator hms1_Iter;  
   hash_multiset <int>::reverse_iterator hms1_rIter;  
   hash_multiset <int>::const_reverse_iterator hms1_crIter;  
  
   hms1.insert( 10 );  
   hms1.insert( 20 );  
   hms1.insert( 30 );  
  
   hms1_rIter = hms1.rend( );  
   hms1_rIter--;  
   cout << "The last element in the reversed hash_multiset is "  
        << *hms1_rIter << "." << endl;  
  
   // end can be used to terminate an iteration   
   // through a hash_multiset in a forward order  
   cout << "The hash_multiset is: ";  
   for ( hms1_Iter = hms1.begin( ) ; hms1_Iter != hms1.end( );  
         hms1_Iter++ )  
      cout << *hms1_Iter << " ";  
   cout << "." << endl;  
  
   // rend can be used to terminate an iteration   
   // throught a hash_multiset in a reverse order  
   cout << "The reversed hash_multiset is: ";  
   for ( hms1_rIter = hms1.rbegin( ) ; hms1_rIter != hms1.rend( );  
         hms1_rIter++ )  
      cout << *hms1_rIter << " ";  
   cout << "." << endl;  
  
   hms1_rIter = hms1.rend( );  
   hms1_rIter--;  
   hms1.erase ( *hms1_rIter );  
  
   hms1_rIter = hms1.rend( );  
   hms1_rIter--;  
   cout << "After the erasure, the last element in the "  
        << "reversed hash_multiset is " << *hms1_rIter << "."  
        << endl;  
}  
```  
  
```Output  
The last element in the reversed hash_multiset is 10.  
The hash_multiset is: 10 20 30 .  
The reversed hash_multiset is: 30 20 10 .  
After the erasure, the last element in the reversed hash_multiset is 20.  
```  
  
##  <a name="reverse_iterator"></a>  hash_multiset::reverse_iterator  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Okuma veya ters hash_multiset bir öğedeki değiştirmek için bir çift yönlü yineleyici sağlayan türü.  
  
```  
typedef list<typename Traits::value_type, typename Traits::allocator_type>::reverse_iterator reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `reverse_iterator` kullanın ters hash_multiset yinelemek için.  
  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [rbegin](#rbegin) bildirme ve kullanma konusunda bir örnek için `reverse_iterator`.  
  
##  <a name="size"></a>  hash_multiset::size  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Hash_multiset öğe sayısını döndürür.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hash_multiset geçerli uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_size.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hms1;  
   hash_multiset <int> :: size_type i;  
  
   hms1.insert( 1 );  
   i = hms1.size( );  
   cout << "The hash_multiset length is " << i << "." << endl;  
  
   hms1.insert( 2 );  
   i = hms1.size( );  
   cout << "The hash_multiset length is now " << i << "." << endl;  
}  
```  
  
```Output  
The hash_multiset length is 1.  
The hash_multiset length is now 2.  
```  
  
##  <a name="size_type"></a>  hash_multiset::size_type  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Bir hash_multiset öğe sayısı gösterebilir bir işaretsiz tamsayı türü.  
  
```  
typedef list<typename _Traits::value_type, typename _Traits::allocator_type>::size_type size_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [boyutu](#size) bildirme ve kullanma örneği `size_type`  
  
##  <a name="swap"></a>  hash_multiset::Swap  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 İki hash_multisets öğelerini değiş tokuş eder.  
  
```  
void swap(hash_multiset& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Bağımsız değişken hash_multiset öğeleri ile hedef hash_multiset takas için sağlama.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini hiçbir başvuruları, işaretçileri veya öğeleri arasında alınıp verilen iki hash_multisets öğelerinde tanımladığınız yineleyiciler geçersiz kılar.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_swap.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hms1, hms2, hms3;  
   hash_multiset <int>::iterator hms1_Iter;  
  
   hms1.insert( 10 );  
   hms1.insert( 20 );  
   hms1.insert( 30 );  
   hms2.insert( 100 );  
   hms2.insert( 200 );  
   hms3.insert( 300 );  
  
   cout << "The original hash_multiset hms1 is:";  
   for ( hms1_Iter = hms1.begin( ); hms1_Iter != hms1.end( );  
         hms1_Iter++ )  
         cout << " " << *hms1_Iter;  
   cout   << "." << endl;  
  
   // This is the member function version of swap  
   hms1.swap( hms2 );  
  
   cout << "After swapping with hms2, list hms1 is:";  
   for ( hms1_Iter = hms1.begin( ); hms1_Iter != hms1.end( );  
         hms1_Iter++ )  
         cout << " " << *hms1_Iter;  
   cout  << "." << endl;  
  
   // This is the specialized template version of swap  
   swap( hms1, hms3 );  
  
   cout << "After swapping with hms3, list hms1 is:";  
   for ( hms1_Iter = hms1.begin( ); hms1_Iter != hms1.end( );  
         hms1_Iter++ )  
         cout << " " << *hms1_Iter;  
   cout   << "." << endl;  
}  
```  
  
```Output  
The original hash_multiset hms1 is: 10 20 30.  
After swapping with hms2, list hms1 is: 200 100.  
After swapping with hms3, list hms1 is: 300.  
```  
  
##  <a name="upper_bound"></a>  hash_multiset::upper_bound  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Belirtilen anahtar daha büyük bir anahtara sahip bir hash_multiset ilk öğe yineleyici döndürür.  
  
```  
const_iterator upper_bound(const Key& key) const;

iterator upper_bound(const Key& key);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Aranmakta hash_multiset öğeden sıralama anahtarı ile Karşılaştırılacak bağımsız değişkeni anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir [yineleyici](#iterator) veya [const_iterator](#const_iterator) bağımsız değişkeni anahtarından daha büyük bir anahtarla bir hash_multiset ilk öğe konumu adresleri ya da son öğesi başarılı konumu adresleri hash_multiset anahtar için bir eşleşme.  
  
### <a name="remarks"></a>Açıklamalar  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_upper_bound.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hms1;  
   hash_multiset <int> :: const_iterator hms1_AcIter, hms1_RcIter;  
  
   hms1.insert( 10 );  
   hms1.insert( 20 );  
   hms1.insert( 30 );  
  
   hms1_RcIter = hms1.upper_bound( 20 );  
   cout << "The first element of hash_multiset hms1" << endl  
        << " with a key greater than 20 is: "  
        << *hms1_RcIter << "." << endl;  
  
   hms1_RcIter = hms1.upper_bound( 30 );  
  
   // If no match is found for the key, end( ) is returned  
   if ( hms1_RcIter == hms1.end( ) )  
      cout << "The hash_multiset hms1 doesn't have an element "  
           << "\n with a key greater than 30." << endl;  
   else  
      cout << "The element of hash_multiset hms1"  
           << "with a key > 40 is: "  
           << *hms1_RcIter << "." << endl;  
  
   // An element at a specific location in the hash_multiset can be  
   // found by using a dereferenced iterator addressing the location  
   hms1_AcIter = hms1.begin( );  
   hms1_RcIter = hms1.upper_bound( *hms1_AcIter );  
   cout << "The first element of hms1\n with a key greater than "  
        << endl << "that of the initial element of hms1 is: "  
        << *hms1_RcIter << "." << endl;  
}  
```  
  
```Output  
The first element of hash_multiset hms1  
 with a key greater than 20 is: 30.  
The hash_multiset hms1 doesn't have an element   
 with a key greater than 30.  
The first element of hms1  
 with a key greater than   
that of the initial element of hms1 is: 20.  
```  
  
##  <a name="value_comp"></a>  hash_multiset::value_comp  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Bir hash_multiset sipariş öğesi değerleri için kullanılan karşılaştırma nesnesinin bir kopyasını alır.  
  
```  
value_compare value_comp() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hash_multiset şablon parametresi döndürür `Traits`, karma ve kapsayıcının sipariş öğeleri için kullanılan işlev nesneleri içerir.  
  
 Daha fazla bilgi için `Traits` bkz [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konu.  
  
### <a name="remarks"></a>Açıklamalar  
 Saklanan nesne üye işlevi tanımlar:  
  
 **bool işleci**( **constKey &**`_xVal`, **const anahtar &** *_yVal*);  
  
 döndüren **true** varsa `_xVal` önündeki ve eşit değil `_yVal` sıralama düzeninde.  
  
 Unutmayın her ikisi de [key_compare](#key_compare) ve [value_compare](#value_compare) şablon parametresi için eş anlamlı sözcükleri olan **nitelikler**. Her iki tür hash_multiset ve hash_multiset sınıfları, burada ayrı hash_map ve hash_multimap sınıfları ile uyumluluk için aynı oldukları için sağlanır.  
  
   
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_value_comp.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
  
   hash_multiset <int, hash_compare < int, less<int> > > hms1;  
   hash_multiset <int, hash_compare < int, less<int> > >::value_compare  
      vc1 = hms1.value_comp( );  
   bool result1 = vc1( 2, 3 );  
   if( result1 == true )  
   {  
      cout << "vc1( 2,3 ) returns value of true, "  
           << "where vc1 is the function object of hms1."  
           << endl;  
   }  
   else  
   {  
      cout << "vc1( 2,3 ) returns value of false, "  
           << "where vc1 is the function object of hms1."  
           << endl;  
   }  
  
   hash_multiset <int, hash_compare < int, greater<int> > > hms2;  
   hash_multiset<int, hash_compare < int, greater<int> > >::  
           value_compare vc2 = hms2.value_comp( );  
   bool result2 = vc2( 2, 3 );  
   if( result2 == true )  
   {  
      cout << "vc2( 2,3 ) returns value of true, "  
           << "where vc2 is the function object of hms2."  
           << endl;  
   }  
   else  
   {  
      cout << "vc2( 2,3 ) returns value of false, "  
           << "where vc2 is the function object of hms2."  
           << endl;  
   }  
}  
```  
  
```Output  
vc1( 2,3 ) returns value of true, where vc1 is the function object of hms1.  
vc2( 2,3 ) returns value of false, where vc2 is the function object of hms2.  
```  
  
##  <a name="value_compare"></a>  hash_multiset::value_compare  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 İki işlev nesneleri sağlayan bir türü göreli sıralarına belirlemek için bir hash_multiset iki öğenin değerleri karşılaştırabilirsiniz sınıfı karşılaştırma, ikili bir koşul ve öğeleri karmaları birli koşul.  
  
```  
typedef key_compare value_compare;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 **value_compare** şablon parametresi için bir eş anlamlı olduğundan `Traits`.  
  
 Daha fazla bilgi için `Traits` bkz [hash_multiset sınıfı](../standard-library/hash-multiset-class.md) konu.  
  
 Unutmayın her ikisi de [key_compare](#key_compare) ve **value_compare** şablon parametresi için eş anlamlı sözcükleri olan **nitelikler**. Her iki tür sınıfları harita ve burada ayrı multimap ile uyumluluk için aynı oldukları, multiset ve sınıfları kümesi için sağlanır.  
  
   
  
### <a name="example"></a>Örnek  
  Örneğin bkz [value_comp](#value_comp) bildirme ve kullanma konusunda bir örnek için `value_compare`.  
  
##  <a name="value_type"></a>  hash_multiset::value_type  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multiset sınıfı](../standard-library/unordered-multiset-class.md).  
  
 Hash_multiset kapasitesi değer olarak, bir öğe olarak saklanan bir nesneyi tanımlayan bir türü.  
  
```  
typedef Key value_type;  
```  
  
### <a name="example"></a>Örnek  
  
```cpp  
// hash_multiset_value_type.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hms1;  
   hash_multiset <int>::iterator hms1_Iter;  
  
   // Declare value_type  
   hash_multiset <int> :: value_type hmsvt_Int;   
  
   hmsvt_Int = 10;   // Initialize value_type  
  
   // Declare key_type  
   hash_multiset <int> :: key_type hmskt_Int;  
   hmskt_Int = 20;             // Initialize key_type  
  
   hms1.insert( hmsvt_Int );         // Insert value into s1  
   hms1.insert( hmskt_Int );         // Insert key into s1  
  
   // A hash_multiset accepts key_types or value_types as elements  
   cout << "The hash_multiset has elements:";  
   for ( hms1_Iter = hms1.begin() ; hms1_Iter != hms1.end( );  
         hms1_Iter++)  
      cout << " " << *hms1_Iter;  
      cout << "." << endl;  
}  
```  
  
```Output  
The hash_multiset has elements: 10 20.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

