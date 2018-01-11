---
title: "forward_list sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- forward_list/std::forward_list
- forward_list/std::forward_list::allocator_type
- forward_list/std::forward_list::const_iterator
- forward_list/std::forward_list::const_pointer
- forward_list/std::forward_list::const_reference
- forward_list/std::forward_list::difference_type
- forward_list/std::forward_list::iterator
- forward_list/std::forward_list::pointer
- forward_list/std::forward_list::reference
- forward_list/std::forward_list::size_type
- forward_list/std::forward_list::value_type
- forward_list/std::forward_list::assign
- forward_list/std::forward_list::before_begin
- forward_list/std::forward_list::begin
- forward_list/std::forward_list::cbefore_begin
- forward_list/std::forward_list::cbegin
- forward_list/std::forward_list::cend
- forward_list/std::forward_list::clear
- forward_list/std::forward_list::emplace_after
- forward_list/std::forward_list::emplace_front
- forward_list/std::forward_list::empty
- forward_list/std::forward_list::end
- forward_list/std::forward_list::erase_after
- forward_list/std::forward_list::front
- forward_list/std::forward_list::get_allocator
- forward_list/std::forward_list::insert_after
- forward_list/std::forward_list::max_size
- forward_list/std::forward_list::merge
- forward_list/std::forward_list::pop_front
- forward_list/std::forward_list::push_front
- forward_list/std::forward_list::remove
- forward_list/std::forward_list::remove_if
- forward_list/std::forward_list::resize
- forward_list/std::forward_list::reverse
- forward_list/std::forward_list::sort
- forward_list/std::forward_list::splice_after
- forward_list/std::forward_list::swap
- forward_list/std::forward_list::unique
dev_langs: C++
helpviewer_keywords:
- std::forward_list
- std::forward_list::allocator_type
- std::forward_list::const_iterator
- std::forward_list::const_pointer
- std::forward_list::const_reference
- std::forward_list::difference_type
- std::forward_list::iterator
- std::forward_list::pointer
- std::forward_list::reference
- std::forward_list::size_type
- std::forward_list::value_type
- std::forward_list::assign
- std::forward_list::before_begin
- std::forward_list::begin
- std::forward_list::cbefore_begin
- std::forward_list::cbegin
- std::forward_list::cend
- std::forward_list::clear
- std::forward_list::emplace_after
- std::forward_list::emplace_front
- std::forward_list::empty
- std::forward_list::end
- std::forward_list::erase_after
- std::forward_list::front
- std::forward_list::get_allocator
- std::forward_list::insert_after
- std::forward_list::max_size
- std::forward_list::merge
- std::forward_list::pop_front
- std::forward_list::push_front
- std::forward_list::remove
- std::forward_list::remove_if
- std::forward_list::resize
- std::forward_list::reverse
- std::forward_list::sort
- std::forward_list::splice_after
- std::forward_list::swap
- std::forward_list::unique
ms.assetid: 89a3b805-ab60-4858-b772-5855130c11b1
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 36354e8b6e6e0c456334caed402a700129b32dae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="forwardlist-class"></a>forward_list Sınıfı
Öğe değişen uzunluk dizisi denetleyen bir nesne açıklar. Sıralı her türünün bir üyesi içeren düğümler, ayrı olarak bağlı listesi olarak depolanan `Type`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Type,   
    class Allocator = allocator<Type>>  
class forward_list   
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Type`|Forward_list depolanması için öğe veri türü.|  
|`Allocator`|Forward_list ayırma ve bellek ayırmayı kaldırma ayrıntılarını yalıtan saklı ayırıcısı nesne. Bu parametre isteğe bağlıdır. Varsayılan değer ayırıcısı: < `Type`>.|  
  
## <a name="remarks"></a>Açıklamalar  
 A `forward_list` nesne ayırır ve sınıfın saklı nesnesi denetlediği dizisi için depolama boşaltır `Allocator` temel [allocator sınıfı](../standard-library/allocator-class.md) (genellikle olarak bilinen `std::allocator)`. Daha fazla bilgi için bkz: [Allocators](../standard-library/allocators.md). Bir ayırıcı nesne şablonu sınıfın bir nesnesi olarak aynı dış arabirimi olmalıdır `allocator`.  
  
> [!NOTE]
>  Kapsayıcı nesnesinin atandığında saklı ayırıcısı nesne kopyalanmaz.  
  
 Yineleyiciler, işaretçiler ve başvurular geçersiz hale kendi denetlenen sıradaki aracılığıyla silinir zaman `forward_list`. Eklemeleri ve splices gerçekleştirilen denetlenen sırasındaki `forward_list` yineleyiciler geçersiz değil.  
  
 Denetimli dizisi eklemeler yapılan çağrılar tarafından oluşabilir [forward_list::insert_after](#insert_after), oluşturucuyu çağırır yalnızca üye işlevi olduğu `Type(const  T&)`. `forward_list`Çağrı oluşturucular taşımak da. Bu tür bir ifadenin bir özel durum oluşturursa, kapsayıcı nesnesinin yeni öğe ekler ve özel durumu yeniden oluşturur. Bu nedenle, şablon sınıfın bir nesnesi `forward_list` gibi özel durumları oluştuğunda bilinen bir durumda bırakılır.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[forward_list](#forward_list)|Türünde bir nesne oluşturur `forward_list`.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|Allocator sınıfı bir iletme listesi nesnesi için temsil eden tür.|  
|[const_iterator](#const_iterator)|İleriye doğru listesi için bir sabit yineleyici sağlayan türü.|  
|[const_pointer](#const_pointer)|Bir işaretçi sağlayan bir türü bir `const` iletme listesindeki öğe.|  
|[const_reference](#const_reference)|İletme listesindeki bir öğeyi sabit başvuru sağlayan türü.|  
|[difference_type](#difference_type)|Yineleyiciler tarafından işaret öğeler arasındaki bir aralıkta iletme listesini öğe sayısını temsil etmek için kullanılan bir imzalı tamsayı türü.|  
|[Yineleyici](#iterator)|Yineleyici ileriye doğru listesi için sağlayan türü.|  
|[İşaretçi](#pointer)|İletme listedeki bir öğe için bir işaretçi sağlayan türü.|  
|[başvuru](#reference)|İletme listedeki bir öğe için bir başvuru sağlar türü.|  
|[size_type](#size_type)|İki öğe arasındaki imzasız uzaklığı temsil eden tür.|  
|[value_type](#value_type)|İletme listede depolanmış öğenin türünü temsil eden tür.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[Ata](#assign)|Öğeleri iletme listeden siler ve bir hedef iletme listesine yeni bir öğeleri kümesini kopyalar.|  
|[before_begin](#before_begin)|Bir iletme listesindeki ilk öğesinden önce konumu adresleme yineleyici döndürür.|  
|[başlayın](#begin)|Yineleyici iletme listesindeki ilk öğeyi adresleme döndürür.|  
|[cbefore_begin](#cbefore_begin)|Bir iletme listesindeki ilk öğesinden önce konumu adresleme const yineleyici döndürür.|  
|[cbegin](#cbegin)|İletme listesindeki ilk öğeyi adresleme const yineleyici döndürür.|  
|[cend](#cend)|İletme listesindeki son öğeyi başarılı konumu adresleri const bir yineleyici döndürür.|  
|[Temizle](#clear)|İleriye doğru listesini tüm öğeleri siler.|  
|[emplace_after](#emplace_after)|Taşıma sonra belirtilen bir konuma yeni bir öğesi oluşturur.|  
|[emplace_front](#emplace_front)|Listenin başına yerinde oluşturulan bir öğe ekler.|  
|[boş](#empty)|İleriye doğru listesini boş olup olmadığını sınar.|  
|[Bitiş](#end)|İletme listesindeki son öğeyi başarılı konumu adresleri yineleyici döndürür.|  
|[erase_after](#erase_after)|Öğeleri sonra belirtilen bir konuma iletme listesinden kaldırır.|  
|[Ön](#front)|İlk öğe başvuru ileriye doğru bir liste döndürür.|  
|[get_allocator](#get_allocator)|İleriye doğru listesini oluşturmak için kullanılan ayırıcısı nesnesinin bir kopyasını döndürür.|  
|[insert_after](#insert_after)|Öğeleri sonra belirtilen bir konuma iletme listesine ekler.|  
|[max_size](#max_size)|Uzunluk iletme listesini döndürür.|  
|[Birleştirme](#merge)|Öğeleri bağımsız değişkeni listeden kaldırır, bunları hedef iletme listesine ekler ve öğeleri artan düzende veya başka bir belirtilen sırayla yeni, birleştirilmiş kümesini sıralar.|  
|[pop_front](#pop_front)|İletme listesinin başında öğeyi siler.|  
|[push_front](#push_front)|Bir öğeyi iletme listesini başlangıcına ekler.|  
|[remove](#remove)|Belirtilen bir değerle eşleşen bir iletme listesindeki öğeleri siler.|  
|[remove_if](#remove_if)|Öğeleri belirtilen bir koşulu karşılanıp iletme listeden siler.|  
|[yeniden boyutlandırma](#resize)|İleriye doğru listesi için yeni bir boyutunu belirtir.|  
|[geriye doğru](#reverse)|Öğeleri bir iletme listesinde nasıl sırayla tersine çevirir.|  
|[Sıralama](#sort)|Artan düzende veya bir koşul tarafından belirtilen bir düzende öğeleri düzenler.|  
|[splice_after](#splice_after)|Düğümler arasındaki bağlantıları restitches.|  
|[değiştirme](#swap)|İki iletme liste öğelerini değiş tokuş eder.|  
|[benzersiz](#unique)|Belirtilen bir sınamadan bitişik öğeleri kaldırır.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](#op_eq)|İleriye doğru liste öğelerini, başka bir iletme listesinin bir kopyasını yerini alır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<forward_list >  
  
 **Namespace:** std  
  
##  <a name="allocator_type"></a>forward_list::allocator_type  
 Allocator sınıfı bir iletme listesi nesnesi için temsil eden tür.  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `allocator_type`Şablon parametresi ayırıcısı eşanlamlısı olur.  
  
##  <a name="assign"></a>forward_list::Assign  
 Öğeleri iletme listeden siler ve bir hedef iletme listesine yeni bir öğeleri kümesini kopyalar.  
  
```  
void assign(
    size_type Count,   
    const Type& Val);

void assign(
    initializer_list<Type> IList);

template <class InputIterator>  
void assign(InputIterator First, InputIterator Last);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`first`|Değiştirme aralığı başlangıcı.|  
|`last`|Değiştirme aralığı sonu.|  
|`count`|Atanacak öğe sayısı.|  
|`val`|Her öğe atanacak değer.|  
|`Type`|Değerin türü.|  
|`IList`|Kopyalamak için initializer_list.|  
  
### <a name="remarks"></a>Açıklamalar  
 Forward_list bir tamsayı türü ise, ilk üye işlevi aynı şekilde davranır `assign((size_type)First, (Type)Last)`. Aksi durumda, ilk üye işlevi tarafından denetlenen dizisi değiştirir `*this` dizisiyle [ `First, Last)`, ilk denetlenen dizisi çakışmamalıdır.  
  
 İkinci üye fonksiyonu tarafından denetlenen dizisi değiştirir `*this` bir yinelenmesinin ile `Count` değerinin öğeleri `Val`.  
  
 Üçüncü üye işlevi initializer_list öğelerini forward_list kopyalar.  
  
##  <a name="before_begin"></a>forward_list::before_begin  
 Bir iletme listesindeki ilk öğesinden önce konumu adresleme yineleyici döndürür.  
  
```  
const_iterator before_begin() const;
iterator before_begin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizinin ilk öğesi hemen önce (veya boş bir dizi sonuna hemen önce) işaret iletme yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="begin"></a>forward_list::Begin  
 Yineleyici iletme listesindeki ilk öğeyi adresleme döndürür.  
  
```  
const_iterator begin() const;
iterator begin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk öğede dizisi (veya yalnızca boş bir dizi ötesinde) işaret iletme yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="cbefore_begin"></a>forward_list::cbefore_begin  
 Bir iletme listesindeki ilk öğesinden önce konumu adresleme const yineleyici döndürür.  
  
```  
const_iterator cbefore_begin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizinin ilk öğesi hemen önce (veya boş bir dizi sonuna hemen önce) işaret iletme yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="cbegin"></a>forward_list::cbegin  
 Döndürür bir `const` aralığın ilk öğe adresleri yineleyici.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `const` ilk öğede aralığı ya da yalnızca boş bir aralığın ötesinde konumunu işaret İleri erişim yineleyici (boş bir aralığın için `cbegin() == cend()`).  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri ile `cbegin`, öğeleri aralığında değiştirilemez.  
  
 Bu üye işlevi yerine kullanabileceğiniz `begin()` üye işlevi dönüş değeri garanti `const_iterator`. Genellikle, ile birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` bir değiştirilebilir için (olmayan `const`) destekleyen herhangi bir türde kapsayıcı `begin()` ve `cbegin()`.  
  
```cpp  
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();
// i2 is Container<T>::const_iterator  
```  
  
##  <a name="cend"></a>forward_list::cend  
 Döndürür bir `const` konumun yalnızca bir aralıkta son öğenin ötesinde adresleri yineleyici.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aralığının hemen sonunu gösteren bir ileriye doğru erişim yineleyicisi.  
  
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
  
##  <a name="clear"></a>forward_list::Clear  
 İleriye doğru listesini tüm öğeleri siler.  
  
```  
void clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi çağırır`erase_after(before_begin(), end()).`  
  
##  <a name="const_iterator"></a>forward_list::const_iterator  
 İleriye doğru listesi için bir sabit yineleyici sağlayan türü.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `const_iterator`denetimli sırası için sabit bir iletme yineleyici olarak hizmet verebilir nesneyi açıklar. Bunu açıklanan burada bir uygulama tanımlı türü eşanlamlısı olarak.  
  
##  <a name="const_pointer"></a>forward_list::const_pointer  
 Bir işaretçi sağlayan bir türü bir `const` iletme listesindeki öğe.  
  
```  
typedef typename Allocator::const_pointer  
    const_pointer; 
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="const_reference"></a>forward_list::const_reference  
 İletme listesindeki bir öğeyi sabit başvuru sağlayan türü.  
  
```  
typedef typename Allocator::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="difference_type"></a>forward_list::difference_type  
 Yineleyiciler tarafından işaret öğeler arasındaki bir aralıkta iletme listesini öğe sayısını temsil etmek için kullanılan bir imzalı tamsayı türü.  
  
```  
typedef typename Allocator::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `difference_type`Denetlenen sıradaki herhangi iki öğe adreslerini arasındaki farkı temsil eden bir nesne açıklar.  
  
##  <a name="emplace_after"></a>forward_list::emplace_after  
 Taşıma sonra belirtilen bir konuma yeni bir öğesi oluşturur.  
  
```  
template <class T>  
iterator emplace_after(const_iterator Where, Type&& val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Where`|Yeni öğe burada oluşturulan konumu hedef iletme listesi.|  
|`val`|Oluşturucu bağımsız değişkeni.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni eklenen öğesi atayan bir yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlev oluşturucu bağımsız değişkenleri olan bir öğe ekler `val` gösterdiği öğesinden sonra `Where` denetlenen sıradaki. Davranışını yoksa aynı olan [forward_list::insert_after](#insert_after).  
  
##  <a name="emplace_front"></a>forward_list::emplace_front  
 Listenin başına yerinde oluşturulan bir öğe ekler.  
  
```  
template <class Type>  
void emplace_front(Type&& val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`val`|Öğe iletme listenin başına eklenir.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlev oluşturucu bağımsız değişkenleri olan bir öğe ekler `_ val` denetimli dizisi sonunda.  
  
 Bir özel durum, kapsayıcı sol değiştirilmemiş ve özel durum işlenemezse.  
  
##  <a name="empty"></a>forward_list::empty  
 İleriye doğru listesini boş olup olmadığını sınar.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`ileriye doğru liste boşsa; Aksi takdirde `false`.  
  
##  <a name="end"></a>forward_list::End  
 İletme listesindeki son öğeyi başarılı konumu adresleri yineleyici döndürür.  
  
```  
const_iterator end() const;
iterator end();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yalnızca dizisi sonunu aşan işaret iletme yineleyici.  
  
##  <a name="erase_after"></a>forward_list::erase_after  
 Öğeleri sonra belirtilen bir konuma iletme listesinden kaldırır.  
  
```  
iterator erase_after(const_iterator Where);
iterator erase_after(const_iterator first, const_iterator last);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Where`|Hedef iletme listesindeki öğe burada silinmeden konumu.|  
|`first`|Silme aralığını başlangıcı.|  
|`last`|Silinecek aralığı sonu.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaldırılan herhangi bir öğenin dışında kalan ilk öğe atar yineleyici veya [forward_list::end](#end) böyle bir öğe varsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimli bir öğenin ilk üye işlevi kaldırır hemen sonra sıra `Where`.  
  
 İkinci üye işlevi denetlenen sıradaki aralığında kaldırır `( first,  last)` (hiçbiri uç noktası bulunur).  
  
 Silme `N` öğeleri nedenler `N` yıkıcı çağrıları. [Yeniden ayırma](../standard-library/forward-list-class.md) yineleyiciler ve başvuruları için silinen öğeleri geçersiz hale şekilde gerçekleşir.  
  
 Üye işlevleri hiçbir zaman bir özel durum.  
  
##  <a name="forward_list"></a>forward_list::forward_list  
 Türünde bir nesne oluşturur `forward_list`.  
  
```  
forward_list();
explicit forward_list(const Allocator& Al);
explicit forward_list(size_type Count);
forward_list(size_type Count, const Type& Val);
forward_list(size_type Count, const Type& Val, const Allocator& Al);
forward_list(const forward_list& Right);
forward_list(const forward_list& Right, const Allocator& Al);
forward_list(forward_list&& Right);
forward_list(forward_list&& Right, const Allocator& Al);
forward_list(initializer_list<Type> IList, const Alloc& Al);
template <class InputIterator>  
forward_list(InputIterator First, InputIterator Last);
template <class InputIterator>  
forward_list(InputIterator First, InputIterator Last, const Allocator& Al);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Al`|Bu nesneyle kullanılacak kaynak ayırıcı sınıfı.|  
|`Count`|Oluşturulan listedeki öğe sayısı.|  
|`Val`|Oluşturulan listesindeki öğeleri değeri.|  
|`Right`|Oluşturulan listenin bir kopyasını olmasını olduğu listesi.|  
|`First`|Kopyalanacak öğe aralığını ilk öğe konumu.|  
|`Last`|Kopyalanacak öğeleri aralık ötesinde ilk öğe konumu.|  
|`IList`|Kopyalamak için initializer_list.|  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm oluşturucular depolamak bir [ayırıcısı](../standard-library/allocator-class.md) ve denetlenen sırası başlatılamıyor. Bağımsız değişken ayırıcısı nesnesidir `Al`, varsa. Kopya Oluşturucu için olmasından ` right.get_allocator()`. Aksi takdirde, değer `Allocator()`.  
  
 İlk iki oluşturucular boş ilk denetlenen dizisi belirtin.  
  
 Bir yineleme sayısını üçüncü Oluşturucusu belirtir `Count` değerinin öğeleri `Type()`.  
  
 Dördüncü ve beşinci oluşturucular yineleme sayısını belirtme `Count` değerinin öğeleri `Val`.  
  
 Altıncı oluşturucusu tarafından denetlenen sırasının bir kopyasını belirtir `Right`. Varsa `InputIterator` bir tamsayı türü sonraki iki oluşturucular yineleme sayısını belirtme `(size_type)First` değerinin öğeleri `(Type)Last`. Aksi halde, sonraki iki oluşturucular sırayı belirtmek `[First, Last)`.  
  
 Dokuzuncu ve onuncu oluşturucular ile altıncı, ancak aynı olan bir [rvalue](../cpp/rvalue-reference-declarator-amp-amp.md) başvuru.  
  
 Son Oluşturucusu sınıfın bir nesnesi ilk denetlenen dizisi belirtir `initializer_list<Type>`.  
  
##  <a name="front"></a>forward_list::Front  
 İlk öğe başvuru ileriye doğru bir liste döndürür.  
  
```  
reference front();
const_reference front() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Boş olması gerekir denetlenen dizisinin ilk öğesi referansı.  
  
##  <a name="get_allocator"></a>forward_list::get_allocator  
 İleriye doğru listesini oluşturmak için kullanılan ayırıcısı nesnesinin bir kopyasını döndürür.  
  
```  
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Saklı [ayırıcısı](../standard-library/allocator-class.md) nesnesi.  
  
##  <a name="insert_after"></a>forward_list::insert_after  
 Öğeleri sonra belirtilen bir konuma iletme listesine ekler.  
  
```  
iterator insert_after(const_iterator Where, const Type& Val);
void insert_after(const_iterator Where, size_type Count, const Type& Val);
void insert_after(const iterator Where, initializer_list<Type> IList);
iterator insert_after(const_iterator Where, Type&& Val);
template <class InputIterator>  
void insert_after(const_iterator Where, InputIterator First, InputIterator Last);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Where`|Hedef iletme listesindeki ilk öğe burada eklenen konumu.|  
|`Count`|Eklenecek öğe sayısı.|  
|`First`|Ekleme Aralık başlangıcı.|  
|`Last`|Ekleme aralığı sonu.|  
|`Val`|İletme listesine eklenen öğesi.|  
|`IList`|Eklenecek initializer_list.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni eklenen öğesi atayan bir yineleyici (yalnızca ilk ve son üye işlevlerini).  
  
### <a name="remarks"></a>Açıklamalar  
 Her üyesinin eklemeleri işlevleri — yalnızca gösterdiği öğesinden sonra `Where` denetlenen sıradaki — bir sırası, ' kalan işlenen tarafından belirtilen.  
  
 İlk üye işlevi değerine sahip bir öğe ekler `Val` ve yeni eklenen öğesi atayan bir yineleyici döndürür.  
  
 İkinci üye işlevi bir yinelenmesinin ekler `Count` değerinin öğeleri `Val`.  
  
 Varsa `InputIterator` bir tamsayı türü üçüncü üye işlevi aynı şekilde davranır `insert(it, (size_type)First, (Type)Last)`. Aksi takdirde dizisi ekler `[First, Last)`, ilk denetlenen dizisi çakışmamalıdır.  
  
 Sınıfın bir nesnesi tarafından belirtilen sıra dördüncü üye işlevi ekler `initializer_list<Type>`.  
  
 Son üye işlevi ile ilk, ancak aynı olan bir [rvalue](../cpp/rvalue-reference-declarator-amp-amp.md) başvuru.  
  
 Ekleme `N` öğeleri nedenler `N` Oluşturucu çağrıları. [Yeniden ayırma](../standard-library/forward-list-class.md) oluşur, ancak hiçbir yineleyiciler veya başvuruları geçersiz hale gelir.  
  
 Bir ekleme sırasında bir özel durum ya da daha fazla öğe, kapsayıcı ise sol değiştirilmemiş ve özel durum işlenemezse.  
  
##  <a name="iterator"></a>forward_list::iterator  
 Yineleyici ileriye doğru listesi için sağlayan türü.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `iterator`iletme yineleyici denetlenen dizisi olarak hizmet verebilir nesneyi açıklar. Bunu açıklanan burada bir uygulama tanımlı türü eşanlamlısı olarak.  
  
##  <a name="max_size"></a>forward_list::max_size  
 Uzunluk iletme listesini döndürür.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne denetleyebilirsiniz uzun sırası uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="merge"></a>forward_list::Merge  
 Tek bir sıralanmış sırası iki sıralanmış dizilere doğrusal zamanında birleştirir. Öğeleri bağımsız değişkeni listeden kaldırır ve bu ekler `forward_list`. İki liste çağırmadan önce aynı karşılaştırma işlev nesnesi tarafından sıralanması gerektiğini `merge`. Birleşik listeyi tarafından işlev nesnesi karşılaştıran sıralanır.  
  
```  
void merge(forward_list& right);
template <class Predicate>  
void merge(forward_list& right, Predicate comp);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`right`|Gelen birleştirmek için ileriye doğru listesi.|  
|`comp`|Öğeleri sıralama için kullanılan karşılaştırma işlev nesnesi.|  
  
### <a name="remarks"></a>Açıklamalar  
 `forward_list::merge`öğeleri kaldırır `forward_list` `right`ve bu ekler `forward_list`. Her iki dizileri aynı önerme tarafından sıralanmalıdır aşağıda açıklanmıştır. Birleşik dizisi de bu karşılaştırma işlev nesnesi tarafından sıralanır.  
  
 Yineleyiciler için `Pi` ve `Pj` konumlarda öğeleri belirleme `i` ve `j`, ilk üye işlevi sırasını uygular `!(*Pj < *Pi)` her `i < j`. (Öğeleri sıralanır `ascending` sipariş.) İkinci üye işlevi sırasını uygular `! comp(*Pj, *Pi)` her `i < j`.  
  
 Özgün denetlenen sıradaki öğelerin hiçbir çiftleri elde edilen denetimli sırayla alınır. Elde edilen içinde çiftlerini dizisi denetlenen varsa eşit karşılaştırır ( `!(*Pi < *Pj) && !(*Pj < *Pi)`), öğenin özgün denetimli serisinden denetlediği sırasından önce bir öğe görünür `right`.  
  
 Yalnızca bir özel durum oluşur `comp` bir özel durum oluşturur. Bu durumda, denetlenen dizisi belirtilmeyen sırada bırakılır ve özel durum işlenemezse.  
  
##  <a name="op_eq"></a>forward_list::operator =  
 İleriye doğru liste öğelerini, başka bir iletme listesinin bir kopyasını yerini alır.  
  
```  
forward_list& operator=(const forward_list& right);
forward_list& operator=(initializer_list<Type> IList);
forward_list& operator=(forward_list&& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`right`|İletme listesine kopyalanmasını iletme listesi.|  
|`IList`|Yalnızca türündeki öğeler bir dizi gibi davranır parantez içine Başlatıcı listesini `Type`.|  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işleci denetlediği sırasının bir kopyasını ile denetlenen dizisi değiştirir `right`.  
  
 İkinci üye işleci sınıfın bir nesnesi denetimli dizisinden değiştirir `initializer_list<Type>`.  
  
 Üçüncü üye işleci ile ilk, ancak aynı olan bir [rvalue](../cpp/rvalue-reference-declarator-amp-amp.md) başvuru.  
  
##  <a name="pointer"></a>forward_list::pointer  
 İletme listedeki bir öğe için bir işaretçi sağlayan türü.  
  
```  
typedef typename Allocator::pointer pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="pop_front"></a>forward_list::pop_front  
 İletme listesinin başında öğeyi siler.  
  
```  
void pop_front();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İletme listesinin ilk öğe boş olmalıdır.  
  
 Üye işlevi hiçbir zaman bir özel durum oluşturur.  
  
##  <a name="push_front"></a>forward_list::push_front  
 Bir öğeyi iletme listesini başlangıcına ekler.  
  
```  
void push_front(const Type& val);
void push_front(Type&& val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`val`|Öğe iletme listenin başına eklenir.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bir özel durum, kapsayıcı sol değiştirilmemiş ve özel durum işlenemezse.  
  
##  <a name="reference"></a>forward_list::Reference  
 İletme listedeki bir öğe için bir başvuru sağlar türü.  
  
```  
typedef typename Allocator::reference reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="remove"></a>forward_list::Remove  
 Belirtilen bir değerle eşleşen bir iletme listesindeki öğeleri siler.  
  
```  
void remove(const Type& val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`val`|Bu öğenin kaldırma listeden bir öğe tarafından tutulan varsa sonuçlanır değeri.|  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi denetlenen dizisinden yineleyici tarafından atanan tüm öğeleri kaldırır `P`, kendisi için `*P ==  val`.  
  
 Üye işlevi hiçbir zaman bir özel durum oluşturur.  
  
##  <a name="remove_if"></a>forward_list::remove_if  
 Öğeleri belirtilen bir koşulu karşılanıp iletme listeden siler.  
  
```  
template <class Predicate>  
void remove_if(Predicate pred);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`pred`|Bir öğe tarafından karşılanan varsa bu öğe listeden silinmesini sonuçlanır hangi birli koşul.|  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi denetlenen dizisinden yineleyici tarafından atanan tüm öğeleri kaldırır `P`, kendisi için ` pred(*P)` doğrudur.  
  
 Yalnızca bir özel durum oluşur `pred` bir özel durum oluşturur. Bu durumda, denetlenen dizisi belirtilmeyen bir durumda kalır ve özel durum işlenemezse.  
  
##  <a name="resize"></a>forward_list::Resize  
 İleriye doğru listesi için yeni bir boyutunu belirtir.  
  
```  
void resize(size_type _Newsize);
void resize(size_type _Newsize, const Type& val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`_Newsize`|Yeniden boyutlandırılan iletme listedeki öğe sayısı.|  
|`val`|Doldurma için kullanılacak bir değer.|  
  
### <a name="remarks"></a>Açıklamalar  
 Her ikisi de olun listedeki öğe sayısının henceforth olduğunu üye işlevleri `_Newsize`. Uzun denetimli dizisi yapmanız gerekiyorsa, ilk üye işlevi değer ile öğeleri ekler `Type()`değere sahip öğeleri ikinci üye işlevi ekler yaparken `val`. Daha kısa denetimli sıra yapmak için her iki üye işlevleri etkili bir şekilde çağırma `erase_after(begin() + _Newsize - 1, end())`.  
  
##  <a name="reverse"></a>forward_list::reverse  
 Öğeleri bir iletme listesinde nasıl sırayla tersine çevirir.  
  
```  
void reverse();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="size_type"></a>forward_list::size_type  
 İki öğe arasındaki imzasız uzaklığı temsil eden tür.  
  
```  
typedef typename Allocator::size_type size_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İşaretsiz tamsayı türünü herhangi denetimli sırası uzunluğu temsil eden bir nesne tanımlar.  
  
##  <a name="sort"></a>forward_list::sort  
 Artan düzende veya bir koşul tarafından belirtilen bir düzende öğeleri düzenler.  
  
```  
void sort();
template <class Predicate>  
void sort(Predicate pred);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`pred`|Sıralama koşul.|  
  
### <a name="remarks"></a>Açıklamalar  
 Her iki üye işlevleri öğeleri denetimli içinde bir koşul tarafından sırasını aşağıda açıklanmıştır.  
  
 Yineleyiciler için `Pi` ve `Pj` konumlarda öğeleri belirleme `i` ve `j`, ilk üye işlevi sırasını uygular `!(*Pj < *Pi)` her `i < j`. (Öğeleri sıralanır `ascending` sipariş.) Üye şablon işlevi sırasını uygular `! pred(*Pj, *Pi)` her `i < j`. Özgün denetlenen sıradaki öğelerin sıralı hiçbir çiftleri elde edilen denetimli sırayla alınır. (Sıralama kararlı olduğundan.)  
  
 Yalnızca bir özel durum oluşur `pred` bir özel durum oluşturur. Bu durumda, denetlenen dizisi belirtilmeyen sırada bırakılır ve özel durum işlenemezse.  
  
##  <a name="splice_after"></a>forward_list::splice_after  
 Bir kaynak forward_list öğeleri kaldırır ve hedef forward_list ekler.  
  
```  
// insert the entire source forward_list  
void splice_after(const_iterator Where, forward_list& Source);
void splice_after(const_iterator Where, forward_list&& Source);

// insert one element of the source forward_list  
void splice_after(const_iterator Where, forward_list& Source, const_iterator Iter);
void splice_after(const_iterator Where, forward_list&& Source, const_iterator Iter);

// insert a range of elements from the source forward_list  
void splice_after(
    const_iterator Where, 
    forward_list& Source,
    const_iterator First,
    const_iterator Last);

void splice_after(
    const_iterator Where,
    forward_list&& Source,
    const_iterator First,
    const_iterator Last);
```  
  
### <a name="parameters"></a>Parametreler  
 `Where`  
 Eklenecek sonra hedef forward_list konumu.  
  
 `Source`  
 Hedef forward_list eklenecek kaynak forward_list.  
  
 `Iter`  
 Kaynağı forward_list eklenecek öğe.  
  
 `First`  
 Kaynak forward_list eklenecek aralıktaki ilk öğe.  
  
 `Last`  
 Kaynağı forward_list eklenecek aralık ötesinde ilk konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevleri ilk çiftinin denetlediği dizisi ekler `Source` gösterdiği denetlenen sıradaki öğenin hemen sonra `Where`. Ayrıca tüm öğeleri kaldırır `Source`. ( `&Source` eşit değil gerekir `this`.)  
  
 Üye işlevleri ikinci çiftinin öğeyi kaldırır hemen sonra `Iter` tarafından denetlenen sıradaki `Source` ve yalnızca denetlenen sıradaki öğenin gösterdiği sonra ekler `Where`. (Varsa `Where == Iter || Where == ++Iter`, hiçbir değişiklik olmaz.)  
  
 Üye işlevleri (aralıklı splice) üçüncü çifti tarafından belirtilen alt aralığı ekler `(First, Last)` tarafından denetlenen serisinden `Source` gösterdiği denetlenen sıradaki öğenin hemen sonra `Where`. Tarafından denetlenen serisinden özgün alt aralığı da kaldırır `Source`. (Varsa `&Source == this`, aralığın `(First, Last)` gösterdiği öğesi içermemesi `Where`.)  
  
 Ranged splice ekliyorsa `N` öğeleri ve `&Source != this`, sınıfın bir nesnesi [yineleyici](#iterator) artırılır `N` kez.  
  
 Hiçbir yineleyiciler, işaretçileri veya spliced öğeleri belirleme başvuruları geçersiz hale gelir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// forward_list_splice_after.cpp  
// compile with: /EHsc /W4  
#include <forward_list>  
#include <iostream>  
  
using namespace std;  
  
template <typename S> void print(const S& s) {  
    for (const auto& p : s) {  
        cout << "(" << p << ") ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    forward_list<int> c1{ 10, 11 };  
    forward_list<int> c2{ 20, 21, 22 };  
    forward_list<int> c3{ 30, 31 };  
    forward_list<int> c4{ 40, 41, 42, 43 };  
  
    forward_list<int>::iterator where_iter;  
    forward_list<int>::iterator first_iter;  
    forward_list<int>::iterator last_iter;  
  
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
    c2.splice_after(where_iter, c1);  
    cout << "After splicing c1 into c2:" << endl;  
    cout << "c1 = ";  
    print(c1);  
    cout << "c2 = ";  
    print(c2);  
  
    first_iter = c3.begin();  
    c2.splice_after(where_iter, c3, first_iter);  
    cout << "After splicing the first element of c3 into c2:" << endl;  
    cout << "c3 = ";  
    print(c3);  
    cout << "c2 = ";  
    print(c2);  
  
    first_iter = c4.begin();  
    last_iter = c4.end();  
    // set up to get the middle elements  
    ++first_iter;  
    c2.splice_after(where_iter, c4, first_iter, last_iter);  
    cout << "After splicing a range of c4 into c2:" << endl;  
    cout << "c4 = ";  
    print(c4);  
    cout << "c2 = ";  
    print(c2);  
}  
  
```  
  
```Output  
Beginning state of lists:c1 = (10) (11)c2 = (20) (21) (22)c3 = (30) (31)c4 = (40) (41) (42) (43)After splicing c1 into c2:c1 =c2 = (20) (21) (10) (11) (22)After splicing the first element of c3 into c2:c3 = (30)c2 = (20) (21) (31) (10) (11) (22)After splicing a range of c4 into c2:c4 = (40) (41)c2 = (20) (21) (42) (43) (31) (10) (11) (22)  
```  
  
##  <a name="swap"></a>forward_list::Swap  
 İki iletme liste öğelerini değiş tokuş eder.  
  
```  
void swap(forward_list& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`right`|Öğeleri değiştirilebilmesi için sağlama iletme listesi.|  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sıraları arasında değiştirir `*this` ve `right`. Varsa `get_allocator() ==  right.get_allocator()`, bunu sabit sürede yapar, hiçbir özel durum oluşturur ve hiçbir başvuruları, işaretçileri veya iki denetimli sıraları öğelerinde tanımladığınız yineleyiciler geçersiz kılar. Aksi durumda, iki denetimli sıralarında öğesi atamaları ve oluşturucu çağrıları öğe sayısını orantılı çeşitli gerçekleştirir.  
  
##  <a name="unique"></a>forward_list::Unique  
 Eşit öğeler her ardışık ilk öğeden dışındaki tüm ortadan kaldırır.  
  
```  
void unique();
template <class BinaryPredicate>  
void unique(BinaryPredicate comp);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`comp`|Birbirini izleyen öğeleri karşılaştırmak için kullanılan ikili koşul.|  
  
### <a name="remarks"></a>Açıklamalar  
 Her benzersiz öğesinin ilk tutar ve rest kaldırır. Değerine eşit öğeleri listede bitişik; böylece öğeleri sıralanması gerekir.  
  
 İlk üye işlevi denetlenen dizisinden önceki öğesine eşit karşılaştırır her öğeyi kaldırır. Yineleyiciler için `Pi` ve `Pj` konumlarda öğeleri belirleme `i` ve `j`, ikinci üye işlevi her öğe için kaldıran `i + 1 == j &&  comp(*Pi, *Pj)`.  
  
 Denetimli sırası uzunluğu için `N` (> 0), koşul ` comp(*Pi, *Pj)` değerlendirilir `N - 1` kez.  
  
 Yalnızca bir özel durum oluşur `comp` bir özel durum oluşturur. Bu durumda, denetlenen dizisi belirtilmeyen bir durumda kalır ve özel durum işlenemezse.  
  
##  <a name="value_type"></a>forward_list::value_type  
 İletme listede depolanmış öğenin türünü temsil eden tür.  
  
```  
typedef typename Allocator::value_type value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi _ eşanlamlısı türüdür `Ty`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<forward_list>](../standard-library/forward-list.md)

