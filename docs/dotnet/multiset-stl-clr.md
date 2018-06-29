---
title: multiset (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multiset
- cliext::multiset::begin
- cliext::multiset::clear
- cliext::multiset::const_iterator
- cliext::multiset::const_reference
- cliext::multiset::const_reverse_iterator
- cliext::multiset::count
- cliext::multiset::difference_type
- cliext::multiset::empty
- cliext::multiset::end
- cliext::multiset::equal_range
- cliext::multiset::erase
- cliext::multiset::find
- cliext::multiset::generic_container
- cliext::multiset::generic_iterator
- cliext::multiset::generic_reverse_iterator
- cliext::multiset::generic_value
- cliext::multiset::insert
- cliext::multiset::iterator
- cliext::multiset::key_comp
- cliext::multiset::key_compare
- cliext::multiset::key_type
- cliext::multiset::lower_bound
- cliext::multiset::make_value
- cliext::multiset::multiset
- cliext::multiset::operator=
- cliext::multiset::rbegin
- cliext::multiset::reference
- cliext::multiset::rend
- cliext::multiset::reverse_iterator
- cliext::multiset::size
- cliext::multiset::size_type
- cliext::multiset::swap
- cliext::multiset::to_array
- cliext::multiset::upper_bound
- cliext::multiset::value_comp
- cliext::multiset::value_compare
- cliext::multiset::value_type
- cliext::multiset::operator!=
- cliext::multiset::operator<
- cliext::multiset::operator<=
- cliext::multiset::operator==
- cliext::multiset::operator>
- cliext::multiset::operator>=
dev_langs:
- C++
helpviewer_keywords:
- <cliext/set> header [STL/CLR]
- <set> header [STL/CLR]
- multiset class [STL/CLR]
- begin member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- count member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- equal_range member [STL/CLR]
- erase member [STL/CLR]
- find member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- key_comp member [STL/CLR]
- key_compare member [STL/CLR]
- key_type member [STL/CLR]
- lower_bound member [STL/CLR]
- make_value member [STL/CLR]
- map member [STL/CLR]
- mapped_type member [STL/CLR]
- operator= member [STL/CLR]
- operator member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- upper_bound member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> member [STL/CLR]
- operator>= member [STL/CLR]
ms.assetid: 7c46e2b4-cd88-49b7-a9e6-63ad5ae7feb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b3c81bc3fd5068f8269476608cc870272a0ef2e4
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079805"
---
# <a name="multiset-stlclr"></a>çoklu set (STL/CLR)
Şablon sınıfı çift yönlü erişimi olan öğeleri değişen uzunluk dizisi denetleyen bir nesne tanımlar. Kapsayıcı kullandığınız `multiset` öğeleri dizisi (neredeyse) dengeli sıralı ağacı düğümleri olarak her bir öğe depolamak yönetmek için.  
  
 Aşağıda, açıklamada `GValue` aynı `GKey`, sırayla olduğu aynı `Key` ikinci ref türü olmadıkça olmasından; bu durumda `Key^`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Key>  
    ref class multiset  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>  
    { ..... };  
```  
  
### <a name="parameters"></a>Parametreler  
 Anahtar  
 Anahtar bileşeni denetlenen sıradaki öğenin türü.  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kümesi >  
  
 **Namespace:** cliext  

## <a name="declarations"></a>Bildirimler  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|[multiset::const_iterator (STL/CLR)](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|  
|[multiset::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|  
|[multiset::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Denetimli sırası için sabit bir ters yineleyici türü.|  
|[multiset::difference_type (STL/CLR)](#difference_type)|İki öğeler arasında (büyük olasılıkla imzalanmış) bir uzaklık türü.|  
|[multiset::generic_container (STL/CLR)](#generic_container)|Genel arabirim kapsayıcının türü.|  
|[multiset::generic_iterator (STL/CLR)](#generic_iterator)|Yineleyici kapsayıcısı için genel arabirimi türü.|  
|[multiset::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Kapsayıcı için genel arabirimini ters yineleyici türü.|  
|[multiset::generic_value (STL/CLR)](#generic_value)|Kapsayıcı için genel arabirimini öğenin türü.|  
|[multiset::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|  
|[multiset::key_compare (STL/CLR)](#key_compare)|İki anahtar sıralama temsilcisi.|  
|[multiset::key_type (STL/CLR)](#key_type)|Bir sıralama anahtarının türü.|  
|[multiset::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|  
|[multiset::reverse_iterator (STL/CLR)](#reverse_iterator)|Denetimli sırası için ters yineleyici türü.|  
|[multiset::size_type (STL/CLR)](#size_type)|İki öğe arasındaki (negatif olmayan) uzaklığı türü.|  
|[multiset::value_compare (STL/CLR)](#value_compare)|İki öğenin değerleri için sıralama temsilcisi.|  
|[multiset::value_type (STL/CLR)](#value_type)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[multiset::begin (STL/CLR)](#begin)|Denetlenen dizinin başlangıcını belirtir.|  
|[multiset::clear (STL/CLR)](#clear)|Tüm öğeleri kaldırır.|  
|[multiset::count (STL/CLR)](#count)|Belirtilen anahtar eşleşen öğeleri sayar.|  
|[multiset::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|  
|[multiset::end (STL/CLR)](#end)|Denetlenen dizinin bitişini belirtir.|  
|[multiset::equal_range (STL/CLR)](#equal_range)|Belirtilen bir anahtarla eşleşen aralığı bulur.|  
|[multiset::erase (STL/CLR)](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|  
|[multiset::find (STL/CLR)](#find)|Belirtilen bir anahtarla eşleşen bir öğeyi bulur.|  
|[multiset::insert (STL/CLR)](#insert)|Öğeleri ekler.|  
|[multiset::key_comp (STL/CLR)](#key_comp)|İki anahtar sıralama temsilcisi kopyalar.|  
|[multiset::lower_bound (STL/CLR)](#lower_bound)|Belirtilen anahtarla eşleşen aralığının başlangıcını bulur.|  
|[multiset::make_value (STL/CLR)](#make_value)|Bir değer nesnesi oluşturur.|  
|[multiset::multiset (STL/CLR)](#multiset)|Bir kapsayıcı nesnesi oluşturur.|  
|[multiset::rbegin (STL/CLR)](#rbegin)|Ters denetimli dizisi başlangıcını belirtir.|  
|[multiset::rend (STL/CLR)](#rend)|Ters denetimli dizinin sonuna belirler.|  
|[multiset::size (STL/CLR)](#size)|Öğe sayısını sayar.|  
|[multiset::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|  
|[multiset::to_array (STL/CLR)](#to_array)|Denetimli sırası yeni bir diziye kopyalar.|  
|[multiset::upper_bound (STL/CLR)](#upper_bound)|Belirtilen anahtarla eşleşen aralığın sonuna bulur.|  
|[multiset::value_comp (STL/CLR)](#value_comp)|İki öğenin değerleri için sıralama temsilci kopyalar.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[multiset::operator= (STL/CLR)](#op_as)|Denetimli dizisi yerini alır.|  
|[operator!= (multiset) (STL/CLR)](#op_neq)|Belirler bir `multiset` nesne diğerine eşit değil `multiset` nesnesi.|  
|[operator< (multiset) (STL/CLR)](#op_lt)|Belirler bir `multiset` nesnesi, başka değerinden `multiset` nesnesi.|  
|[operator<= (multiset) (STL/CLR)](#op_lteq)|Belirler bir `multiset` nesnesidir değerinden küçük veya eşit başka `multiset` nesnesi.|  
|[operator== (multiset) (STL/CLR)](#op_eq)|Belirler bir `multiset` nesnesidir diğerine eşit `multiset` nesnesi.|  
|[operator> (multiset) (STL/CLR)](#op_gt)|Belirler bir `multiset` nesnesidir diğerinden daha büyük `multiset` nesnesi.|  
|[operator>= (multiset) (STL/CLR)](#op_gteq)|Belirler bir `multiset` nesnesidir büyük veya ona eşit diğerine `multiset` nesnesi.|  
  
## <a name="interfaces"></a>Arabirimler  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Yinelenen bir nesne.|  
|<xref:System.Collections.IEnumerable>|Öğeleri dizisi.|  
|<xref:System.Collections.ICollection>|Öğeleri grubunu koruyun.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılan öğeleri dizisi.|  
|<xref:System.Collections.Generic.ICollection%601>|Yazılı öğeleri grubunu koruyun.|  
|ITree\<anahtar, değer >|Genel kapsayıcı korur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne ayırır ve bireysel düğümleri olarak denetimleri dizisi için depolama boşaltır. Hiçbir zaman kopyalayarak bir düğümün içeriğini başka düğümler arasındaki bağlantılar değiştirilerek sıralı tutar (neredeyse) dengeli bir ağaç öğeleri ekler. INSERT ve rahatsız edici kalan öğeleri olmadan serbestçe öğeleri Kaldır anlamına gelir.  
  
 Nesne denetleyen bir saklı temsilci nesne türü çağırarak dizisi siparişleri [multiset::key_compare (STL/CLR)](../dotnet/multiset-key-compare-stl-clr.md). Multiset yapısı oluştururken saklı temsilci nesnesini belirtebilirsiniz; hiçbir temsilci nesnesi belirtirseniz, karşılaştırma varsayılandır `operator<(key_type, key_type)`. Üye işlevini çağırarak saklı bu nesneye erişim [multiset::key_comp (STL/CLR)](../dotnet/multiset-key-comp-stl-clr.md)`()`.  
  
 Böyle bir temsilci nesnenin katı bir zayıf türü anahtarları sıralama zorunlu tuttukları gerekir [multiset::key_type (STL/CLR)](../dotnet/multiset-key-type-stl-clr.md). Yani, herhangi iki tuşları `X` ve `Y`:  
  
 `key_comp()(X, Y)` Her çağrıda aynı Boolean sonucu döndürür.  
  
 Varsa `key_comp()(X, Y)` true ise `key_comp()(Y, X)` false olmalıdır.  
  
 Varsa `key_comp()(X, Y)` true ise `X` önce sıralanmalıdır söylenir `Y`.  
  
 Varsa `!key_comp()(X, Y) && !key_comp()(Y, X)` true ise `X` ve `Y` eşdeğer sıralama sahip söylenir.  
  
 Herhangi bir öğe için `X` , önündeki `Y` denetlenen sıradaki `key_comp()(Y, X)` false olur. (Varsayılan temsilci nesnesi için anahtarları hiçbir zaman değerini azaltın.) Şablon sınıfı aksine [(STL/CLR) ayarlamak](../dotnet/set-stl-clr.md), şablon sınıfın bir nesnesi `multiset` anahtarları tüm öğelerin benzersiz olmasını gerektirmez. (İki veya daha fazla anahtarı eşdeğer sıralama olabilir.)  
  
 Her öğe bir tuş hem de bir değer olarak görev yapar. Sıra, arama, ekleme ve kaldırma işlemlerini öğe sayısını logaritmasını orantılı çeşitli rasgele bir öğenin dizisi (Logaritmik saati) izin veren şekilde gösterilir. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.  
  
 Bir çoklu küme çift yönlü yineleyiciler denetlenen sıradaki öğenin atayan bir yineleyici verilen bitişik öğelerine adım anlamı destekler. Özel bir baş düğüm tarafından döndürülen yineleyici karşılık gelen [multiset::end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)`()`. Denetlenen sıradaki son öğe ulaşmak için bu yineleyici varsa azaltma. Baş düğüm ulaşmak için birden çok küme yineleyici artırabilirsiniz ve bu ardından eşit karşılaştırır `end()`. Ancak tarafından döndürülen yineleyici başvuramaz `end()`.  
  
 Rasgele erişim yineleyici gerektiren sayısal konumunu--doğrudan verilen çok kümeli bir öğeye başvuramaz unutmayın.  
  
 Çok kümeli yineleyici ilişkili kapsayıcısı için bir tanıtıcı sırayla depolayan onun ilişkili birden fazla küme düğümü için bir tanıtıcı depolar. Yalnızca ilişkili kapsayıcı nesneleri ile yineleyiciler kullanabilirsiniz. İlişkili birden fazla küme düğümü bazı multiset ile ilişkili olduğu sürece multiset yineleyici geçerli kalır. Ayrıca, geçerli bir yineleyici dereferencable--erişmek veya eşit değil sürece bunu atayan--öğe değeri değiştirmek için kullanmak `end()`.  
  
 Silme veya bir öğe kaldırıldığında yıkıcı depolanan değeri için çağırır. Kapsayıcı yok etme tüm öğeleri siler. Bu nedenle, hiçbir öğe kapsayıcı outlive ref sınıfı öğe türü olan bir kapsayıcı sağlar. Ancak, bir kapsayıcı, tanıtıcısı algılamadığı unutmayın `not` öğeleri yok.  
  
## <a name="members"></a>Üyeler

## <a name="begin"></a> multiset::Begin (STL/CLR)
Denetlenen dizinin başlangıcını belirtir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
iterator begin();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi, ilk öğe denetimli dizisi ya da yalnızca boş bir dizi ötesinde atayan bir çift yönlü yineleyici döndürür. Atayan bir yineleyici almak için kullandığınız `current` denetimli dizisi ancak durumunu başında denetimli sırası uzunluğu değişirse değiştirebilirsiniz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_begin.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Mymultiset::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*begin() = a  
*++begin() = b  
```  

## <a name="clear"></a> multiset::Clear (STL/CLR)
Tüm öğeleri kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void clear();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini etkili bir şekilde çağırır [multiset::erase (STL/CLR)](../dotnet/multiset-erase-stl-clr.md) `(` [multiset::begin (STL/CLR)](../dotnet/multiset-begin-stl-clr.md) `(),` [multiset::end (STL/CLR)](../dotnet/multiset-end-stl-clr.md) `())`. Denetimli sırası boş olduğundan emin olmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_clear.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.insert(L'a');   
    c1.insert(L'b');   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 0  
 a b  
size() = 0  
```  

## <a name="const_iterator"></a> multiset::const_iterator (STL/CLR)
Denetlenen dizi için bir sabit yineleyici türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef T2 const_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilmeyen türünde bir nesne türünü açıklayan `T2` hizmet eden bir sabit çift yönlü yineleyici denetlenen dizisi olarak.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_const_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    Mymultiset::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" {0}", *cit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="const_reference"></a> multiset::const_reference (STL/CLR)
Bir öğe için sabit bir başvuru türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef value_type% const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğe için sabit bir başvuru türü açıklanmaktadır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_const_reference.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    Mymultiset::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        {   // get a const reference to an element   
        Mymultiset::const_reference cref = *cit;   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
``` 

## <a name="const_reverse_iterator"></a> multiset::const_reverse_iterator (STL/CLR)
Denetimli sırası için sabit bir ters yineleyici türü...  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilmeyen türünde bir nesne türünü açıklayan `T4` hizmet eden sabit bir ters yineleyici denetlenen dizisi olarak.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" reversed   
    Mymultiset::const_reverse_iterator crit = c1.rbegin();   
    for (; crit != c1.rend(); ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="count"></a> multiset::Count (STL/CLR)
Belirtilen bir anahtar ile eşleşen öğe sayısını bulur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
size_type count(key_type key);  
```  
  
#### <a name="parameters"></a>Parametreler  
 anahtar  
 Aranacak anahtar değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi ile eşdeğer sıralama sahip denetlenen sıradaki öğelerin sayısını döndürür. `key`. Belirtilen anahtar eşleşen öğe şu anda denetlenen sıradaki sayısını belirlemek için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_count.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));   
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));   
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
count(L'A') = 0  
count(L'b') = 1  
count(L'C') = 0  
```  
  
## <a name="difference_type"></a> multiset::difference_type (STL/CLR)
İki öğe arasındaki imzalı uzaklığı türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Türünü büyük olasılıkla negatif öğe sayısını tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_difference_type.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Mymultiset::difference_type diff = 0;   
    for (Mymultiset::iterator it = c1.begin(); it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
  
// compute negative difference   
    diff = 0;   
    for (Mymultiset::iterator it = c1.end(); it != c1.begin(); --it)   
        --diff;   
    System::Console::WriteLine("begin()-end() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
begin()-end() = -3  
```  

## <a name="empty"></a> multiset::Empty (STL/CLR)
Bir öğe olup olmadığını sınar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool empty();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi boş denetimli dizisi için true değerini döndürür. Eşdeğer olan [multiset::size (STL/CLR)](../dotnet/multiset-size-stl-clr.md)`() == 0`. Multiset boş olup olmadığını sınamak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_empty.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  
  
## <a name="end"></a> multiset::End (STL/CLR)
Denetlenen dizinin bitişini belirtir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
iterator end();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi yalnızca denetimli dizisi ötesinde işaret çift yönlü yineleyici döndürür. Denetimli bitişinde atayan bir yineleyici almak için kullanın; kendi durumu denetimli sırası uzunluğu değişirse değiştirmek içermiyor.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_end.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    Mymultiset::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --end() = b  
*--end() = c  
```  

## <a name="equal_range"></a> multiset::equal_range (STL/CLR)
Belirtilen bir anahtarla eşleşen aralığı bulur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
cliext::pair<iterator, iterator> equal_range(key_type key);  
```  
  
#### <a name="parameters"></a>Parametreler  
 anahtar  
 Aranacak anahtar değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini yineleyiciler çifti döndürür `cliext::pair<iterator, iterator>(` [multiset::lower_bound (STL/CLR)](../dotnet/multiset-lower-bound-stl-clr.md) `(key),` [multiset::upper_bound (STL/CLR)](../dotnet/multiset-upper-bound-stl-clr.md)`(key))`. Belirtilen anahtar eşleşen öğeleri şu anda denetlenen sıradaki aralığını belirlemek için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_equal_range.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
typedef Mymultiset::pair_iter_iter Pairii;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display results of failed search   
    Pairii pair1 = c1.equal_range(L'x');   
    System::Console::WriteLine("equal_range(L'x') empty = {0}",   
        pair1.first == pair1.second);   
  
// display results of successful search   
    pair1 = c1.equal_range(L'b');   
    for (; pair1.first != pair1.second; ++pair1.first)   
        System::Console::Write(" {0}", *pair1.first);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
equal_range(L'x') empty = True  
 b  
```  

## <a name="erase"></a> multiset::ERASE (STL/CLR)
Belirtilen konumlardaki öğeleri kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
size_type erase(key_type key)  
```  
  
#### <a name="parameters"></a>Parametreler  
 ilk  
 Silme aralığını başlangıcı.  
  
 anahtar  
 Silmek için anahtar değeri.  
  
 Son  
 Silinecek aralığı sonu.  
  
 Burada  
 Silinecek öğe.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi gösterdiği denetimli sırasının öğeyi kaldırır `where`ve kaldırıldı, öğenin dışında kalan ilk öğe atayan bir yineleyici döndürür veya [multiset::end (STL/CLR)](../dotnet/multiset-end-stl-clr.md) `()` böyle bir öğe varsa. Tek bir öğe kaldırmak için kullanın.  
  
 İkinci üye işlevi denetlenen sıradaki aralığında kaldırır [`first`, `last`) ve kaldırıldı, herhangi bir öğenin dışında kalan ilk öğe atayan bir yineleyici döndürür veya `end()` böyle bir öğe varsa mevcut... Sıfır veya daha fazla bitişik öğeleri kaldırmak için kullanın.  
  
 Üçüncü üye işlevi olan anahtara sahip eşdeğer sıralama denetimli sırasının herhangi bir öğeyi kaldırır için `key`ve kaldırılan öğelerin sayısını döndürür. Kaldırmak ve belirtilen bir anahtarı eşleşen tüm öğeleri saymak için kullanın.  
  
 Her öğe Silinme zaman öğe sayısını logaritmasını orantılı denetimli sırayla alır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_erase.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.insert(L'd');   
    c1.insert(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    Mymultiset::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
erase(begin()) = b  
 b c d e  
erase(begin(), end()-1) = e  
size() = 1  
```  

## <a name="find"></a> multiset::Find (STL/CLR)
Belirtilen bir anahtarla eşleşen bir öğeyi bulur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
iterator find(key_type key);  
```  
  
#### <a name="parameters"></a>Parametreler  
 anahtar  
 Aranacak anahtar değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetlenen sıradaki en az bir öğe ile eşdeğer sıralama varsa `key`, bu öğelerden birine belirleme yineleyici üyesi fonksiyonunu döndürür; Aksi halde döner [multiset::end (STL/CLR)](../dotnet/multiset-end-stl-clr.md) `()`. Bir öğe şu anda belirtilen anahtarla eşleşen denetimli sırayla bulmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_find.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
    System::Console::WriteLine("find {0} = {1}",   
        L'b', *c1.find(L'b'));   
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
find A = False  
find b = b  
find C = False  
```  

## <a name="generic_container"></a> multiset::generic_container (STL/CLR)
Genel arabirim kapsayıcının türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef Microsoft::VisualC::StlClr::  
    ITree<GKey, GValue>  
    generic_container;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu şablon kapsayıcı sınıfı için genel arabirimi türünü tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_generic_container.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mymultiset::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->insert(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.insert(L'e');   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a b c d  
a b c d e  
```  

## <a name="generic_iterator"></a> multiset::generic_iterator (STL/CLR)
Yineleyici kullanmak için genel arabirimi kapsayıcının türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ContainerBidirectionalIterator<generic_value>  
    generic_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Genel arabirim ile bu şablon kapsayıcı sınıfı için kullanılabilen genel bir yineleyici türünü tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_generic_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mymultiset::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Mymultiset::generic_iterator gcit = gc1->begin();   
    Mymultiset::generic_value gcval = *gcit;   
    System::Console::WriteLine(" {0}", gcval);   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a  
```  

## <a name="generic_reverse_iterator"></a> multiset::generic_reverse_iterator (STL/CLR)
Kullanmak için ters yineleyici kapsayıcısı için genel arabirimi türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ReverseRandomAccessIterator<generic_value>  
    generic_reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Genel arabirim ile bu şablon kapsayıcı sınıfı için kullanılabilen genel bir ters yineleyici türünü tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_generic_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mymultiset::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Mymultiset::generic_reverse_iterator gcit = gc1->rbegin();   
    Mymultiset::generic_value gcval = *gcit;   
    System::Console::WriteLine(" {0}", gcval);   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
c  
``` 

## <a name="generic_value"></a> multiset::generic_value (STL/CLR)
Kapsayıcı için genel arabirimi ile kullanmak için öğenin türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef GValue generic_value;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Türünde bir nesne türünü açıklayan `GValue` kullanmak için saklı öğesi değeri bu şablonu kapsayıcı sınıfı için genel arabirimi açıklar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_generic_value.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mymultiset::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get an element and display it   
    Mymultiset::generic_iterator gcit = gc1->begin();   
    Mymultiset::generic_value gcval = *gcit;   
    System::Console::WriteLine(" {0}", gcval);   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a  
```   

## <a name="insert"></a> multiset::insert (STL/CLR)
Öğeleri ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
iterator insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 ilk  
 Eklenecek Aralık başlangıcı.  
  
 Son  
 Eklenecek aralık sonu.  
  
 sağ  
 Eklenecek numaralandırması.  
  
 VAL  
 Eklenecek anahtar değeri.  
  
 Burada  
 WHERE (yalnızca ipucu) eklemek için kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Her üye işlevleri kalan işlenen tarafından belirtilen sıra ekler.  
  
 İlk üye işlevi değeri olan bir öğe ekler `val`ve yeni eklenen öğesi atayan bir yineleyici döndürür. Tek bir öğe eklemek için kullanın.  
  
 İkinci üye işlevi değeri olan bir öğe ekler `val`kullanarak `where` (performansını artırmak için) bağlı olarak, bir ipucu olarak ve yeni eklenen öğesi atayan bir yineleyici döndürür. Bildiğiniz bir öğeye bitişik olabilecek tek bir öğe eklemek için kullanın.  
  
 Üçüncü üye işlevi dizisi ekler [`first`, `last`). Başka bir sırasından kopyalanan sıfır veya daha fazla öğe eklemek için kullanın.  
  
 Dördüncü üye fonksiyonu tarafından belirlenen dizisi ekler `right`. Bir numaralandırıcı tarafından tanımlanan bir dizi eklemek için kullanın.  
  
 Her öğe ekleme zaman öğe sayısını logaritmasını orantılı denetimli sırasını alır. Ekleme, bir öğe ekleme noktasını bitişik atayan bir ipucu verilen amortized sabit zamanında bir ancak ortaya çıkabilir.  
  
### <a name="example"></a>Örnek  
  
```cpp
// cliext_multiset_insert.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    System::Console::WriteLine("insert(L'x') = {0}",   
        *c1.insert(L'x'));   
  
    System::Console::WriteLine("insert(L'b') = {0}",   
        *c1.insert(L'b'));   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    System::Console::WriteLine("insert(begin(), L'y') = {0}",   
        *c1.insert(c1.begin(), L'y'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Mymultiset c2;   
    Mymultiset::iterator it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Mymultiset c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
insert(L'x') = x  
insert(L'b') = b  
 a b b c x  
insert(begin(), L'y') = y  
 a b b c x y  
 a b b c x  
 a b b c x y  
```  

## <a name="iterator"></a> multiset::iterator (STL/CLR)
Denetlenen dizi için bir yineleyici türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef T1 iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilmeyen türünde bir nesne türünü açıklayan `T1` hizmet eden bir çift yönlü yineleyici denetlenen dizisi olarak.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    Mymultiset::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="key_comp"></a> multiset::key_comp (STL/CLR)
İki anahtar sıralama temsilcisi kopyalar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
key_compare^key_comp();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sırasını belirlemek için kullanılan sıralama temsilci döndürür. İki anahtar karşılaştırmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp 
// cliext_multiset_key_comp.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    Mymultiset::key_compare^ kcomp = c1.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Mymultiset c2 = cliext::greater<wchar_t>();   
    kcomp = c2.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    return (0);   
    }  
  
```  
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
  
compare(L'a', L'a') = False  
compare(L'a', L'b') = False  
compare(L'b', L'a') = True  
```  

## <a name="key_compare"></a> multiset::key_compare (STL/CLR)
İki anahtar sıralama temsilcisi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>  
    key_compare;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Anahtar değişkenlerinin sıralama belirler temsilci eşanlamlısı türüdür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_key_compare.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    Mymultiset::key_compare^ kcomp = c1.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Mymultiset c2 = cliext::greater<wchar_t>();   
    kcomp = c2.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    return (0);   
    }  
  
```  
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
  
compare(L'a', L'a') = False  
compare(L'a', L'b') = False  
compare(L'b', L'a') = True  
```  

## <a name="key_type"></a> multiset::key_type (STL/CLR)
Bir sıralama anahtarının türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Key`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_key_type.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" using key_type   
    for (Mymultiset::iterator it = c1.begin(); it != c1.end(); ++it)   
        {   // store element in key_type object   
        Mymultiset::key_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="lower_bound"></a> multiset::lower_bound (STL/CLR)
Belirtilen anahtarla eşleşen aralığının başlangıcını bulur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
iterator lower_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Parametreler  
 anahtar  
 Aranacak anahtar değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye fonksiyonu ilk öğe belirler `X` için eşdeğer sıralama sahip denetlenen sıradaki `key`. Böyle bir öğe var olup olmadığını döndürür [multiset::end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)`()`; Aksi takdirde, atayan yineleyici döndürür `X`. Öğe dizisi başına şu anda belirtilen bir anahtar ile denetlenen sırayla bulmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_lower_bound.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",   
        c1.lower_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*lower_bound(L'a') = {0}",   
        *c1.lower_bound(L'a'));   
    System::Console::WriteLine("*lower_bound(L'b') = {0}",   
        *c1.lower_bound(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
lower_bound(L'x')==end() = True  
*lower_bound(L'a') = a  
*lower_bound(L'b') = b  
```  

## <a name="make_value"></a> multiset::make_value (STL/CLR)
Bir değer nesnesi oluşturur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
static value_type make_value(key_type key);  
```  
  
#### <a name="parameters"></a>Parametreler  
 anahtar  
 Kullanılacak anahtar değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndüren bir `value_type` , anahtar nesne `key`. Diğer birçok üye işlevleri ile kullanım için uygun bir nesne oluşturmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_make_value.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(Mymultiset::make_value(L'a'));   
    c1.insert(Mymultiset::make_value(L'b'));   
    c1.insert(Mymultiset::make_value(L'c'));   
  
// display contents " a b c"   
    for each (Mymultiset::value_type elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="multiset"></a> multiset::multiset (STL/CLR)
Bir kapsayıcı nesnesi oluşturur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
multiset();  
explicit multiset(key_compare^ pred);  
multiset(multiset<Key>% right);  
multiset(multiset<Key>^ right);  
template<typename InIter>  
    multisetmultiset(InIter first, InIter last);  
template<typename InIter>  
    multiset(InIter first, InIter last,  
        key_compare^ pred);  
multiset(System::Collections::Generic::IEnumerable<GValue>^ right);  
multiset(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
```  
  
#### <a name="parameters"></a>Parametreler  
 ilk  
 Eklenecek Aralık başlangıcı.  
  
 Son  
 Eklenecek aralık sonu.  
  
 Pred  
 Denetimli sırası için koşulu sıralaması.  
  
 sağ  
 Nesne veya eklemek için aralık.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucusu:  
  
 `multiset();`  
  
 hiçbir öğe ile denetlenen dizisi koşulu sıralama varsayılan başlatır `key_compare()`. Bir boş ilk denetlenen dizisi koşulu sıralama varsayılan belirtmek için kullanın.  
  
 Oluşturucusu:  
  
 `explicit multiset(key_compare^ pred);`  
  
 sıralama koşulu ile hiçbir öğe ile denetlenen dizisi başlatır `pred`. Bir boş ilk denetlenen sıra ile belirtilen sıralama koşulu belirtmek için kullanın.  
  
 Oluşturucusu:  
  
 `multiset(multiset<Key>% right);`  
  
 denetimli dizisi dizisiyle başlatır [`right.begin()`, `right.end()`), koşulu sıralama varsayılan. Çok kümeli nesne tarafından denetlenen sırasının bir kopyasını bir ilk denetlenen sırası belirtmek için kullandığınız `right`, koşulu sıralama varsayılan.  
  
 Oluşturucusu:  
  
 `multiset(multiset<Key>^ right);`  
  
 denetimli dizisi dizisiyle başlatır [`right->begin()`, `right->end()`), koşulu sıralama varsayılan. Çok kümeli nesne tarafından denetlenen sırasının bir kopyasını bir ilk denetlenen sırası belirtmek için kullandığınız `right`, koşulu sıralama varsayılan.  
  
 Oluşturucusu:  
  
 `template<typename InIter> multiset(InIter first, InIter last);`  
  
 denetimli dizisi dizisiyle başlatır [`first`, `last`), koşulu sıralama varsayılan. Denetimli sırası başka bir dizi koşul sıralama varsayılan kopyası için kullanın.  
  
 Oluşturucusu:  
  
 `template<typename InIter> multiset(InIter first, InIter last, key_compare^ pred);`  
  
 denetimli dizisi dizisiyle başlatır [`first`, `last`), sıralama koşulu ile `pred`. Denetimli sırası belirtilen sıralama koşulu ile başka bir dizi bir kopya yapmak için kullanın.  
  
 Oluşturucusu:  
  
 `multiset(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 Numaralandırıcı tarafından belirtilen sıra ile denetlenen dizisi başlatır `right`, koşulu sıralama varsayılan. Denetimli sırası başka bir dizi koşul sıralama varsayılan bir numaralandırıcı tarafından açıklanan bir kopya yapmak için kullanın.  
  
 Oluşturucusu:  
  
 `multiset(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 Numaralandırıcı tarafından belirtilen sıra ile denetlenen dizisi başlatır `right`, sıralama koşulu ile `pred`. Denetimli sırası belirtilen sıralama koşulu ile bir numaralandırıcı tarafından açıklanan başka bir dizi bir kopya yapmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_construct.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
// construct an empty container   
    Mymultiset c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mymultiset c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mymultiset c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mymultiset c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Mymultiset c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Mymultiset c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mymultiset c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mymultiset c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 a b c  
size() = 0  
 c b a  
 a b c  
 c b a  
 a b c  
 c b a  
 c b a  
 a b c  
```  

## <a name="op_as"></a> multiset::operator (STL/CLR) =
Denetimli dizisi yerini alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
multiset<Key>% operator=(multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 sağ  
 Kopyalamak için kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci kopyaları `right` nesnesine sonra döndürür `*this`. Denetimli sırayla kopyası ile denetlenen sırasını değiştirmek için kullanın `right`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_operator_as.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (Mymultiset::value_type elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2 = c1;   
// display contents " a b c"   
    for each (Mymultiset::value_type elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  

## <a name="rbegin"></a> multiset::rbegin (STL/CLR)
Ters denetimli dizisi başlangıcını belirtir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
reverse_iterator rbegin();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli dizisi ya da boş bir dizi başına ötesinde yalnızca son öğesi atar ters bir yineleyici döndürür. Bu nedenle, atar `beginning` ters dizisi. Atayan bir yineleyici almak için kullandığınız `current` ters sırada görülen denetimli dizisi ancak durumunu başında denetimli sırası uzunluğu değişirse değiştirebilirsiniz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_rbegin.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    Mymultiset::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*rbegin() = c  
*++rbegin() = b  
```  
  
## <a name="reference"></a> multiset::Reference (STL/CLR)
Bir öğe için bir başvuru türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğe için bir başvuru türü açıklanmaktadır.  
  
### <a name="example"></a>Örnek  
  
```  
// cliext_multiset_reference.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    Mymultiset::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        Mymultiset::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="rend"></a> multiset::rend (STL/CLR)
Ters denetimli dizinin sonuna belirler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
reverse_iterator rend();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini ters yineleyici başına yalnızca ötesinde işaret denetimli dizisi döndürür. Bu nedenle, atar `end` ters dizisi. Atayan bir yineleyici almak için kullandığınız `current` ters sırada görülen denetimli dizisi ancak durumunu sonuna denetimli sırası uzunluğu değişirse değiştirebilirsiniz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_rend.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Mymultiset::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --rend() = b  
*--rend() = a  
```  

## <a name="reverse_iterator"></a> multiset::reverse_iterator (STL/CLR)
Denetimli sırası için ters yineleyici türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef T3 reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilmeyen türünde bir nesne türünü açıklayan `T3` hizmet eden bir ters yineleyici denetimli sırası için farklı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" reversed   
    Mymultiset::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="size"></a> multiset::size (STL/CLR)
Öğe sayısını sayar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
size_type size();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sırası uzunluğunu döndürür. Şu anda denetlenen sıradaki öğelerinin sayısını belirlemek için kullanın. Tüm önem verdiğiniz ise dizisi bkz sıfır olmayan boyutu olup [multiset::empty (STL/CLR)](../dotnet/multiset-empty-stl-clr.md)`()`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_size.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.insert(L'a');   
    c1.insert(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3 starting with 3  
size() = 0 after clearing  
size() = 2 after adding 2  
```  
  
## <a name="size_type"></a> multiset::size_type (STL/CLR)
İki öğe arasındaki imzalı uzaklığı türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Türünü negatif olmayan öğe sayısını tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_size_type.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Mymultiset::size_type diff = 0;   
    for (Mymultiset::iterator it = c1.begin(); it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
```  

## <a name="swap"></a> multiset::Swap (STL/CLR)
İki kapsayıcının içeriğinin yerini değiştirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void swap(multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 sağ  
 İçeriği ile değiştirilecek kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sıraları arasında değiştirir `this` ve `right`. Bunu Sabit sürede yapar ve hiçbir özel durum oluşturur. Bunu iki kapsayıcı içeriğini exchange hızlı bir şekilde kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_swap.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    Mymultiset c2;   
    c2.insert(L'd');   
    c2.insert(L'e');   
    c2.insert(L'f');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
d e f  
d e f  
a b c  
```  

## <a name="to_array"></a> multiset::to_array (STL/CLR)
Denetimli sırası yeni bir diziye kopyalar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
cli::array<value_type>^ to_array();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi denetimli sırası içeren bir dizi döndürür. Dizi formunda denetimli sırasının bir kopyasını almak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_to_array.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.insert(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c d  
a b c  
```  

## <a name="upper_bound"></a> multiset::upper_bound (STL/CLR)
Belirtilen anahtarla eşleşen aralığın sonuna bulur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Parametreler  
 anahtar  
 Aranacak anahtar değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye fonksiyonu son öğe belirler `X` için eşdeğer sıralama sahip denetlenen sıradaki `key`. Böyle bir öğe varsa veya `X` Son denetlenen sıradaki döndürdüğü öğedir [multiset::end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)`()`; Aksi takdirde, ilk öğe ötesindeatayanyineleyicidöndürür`X`. Öğelerin dizinin sonuna şu anda belirtilen bir anahtar ile denetlenen sırayla bulmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_upper_bound.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*upper_bound(L'a') = {0}",   
        *c1.upper_bound(L'a'));   
    System::Console::WriteLine("*upper_bound(L'b') = {0}",   
        *c1.upper_bound(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
upper_bound(L'x')==end() = True  
*upper_bound(L'a') = b  
*upper_bound(L'b') = c  
```  
  
## <a name="value_comp"></a> multiset::value_comp (STL/CLR)
İki öğenin değerleri için sıralama temsilci kopyalar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
value_compare^ value_comp();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sırasını belirlemek için kullanılan sıralama temsilci döndürür. İki öğenin değerleri karşılaştırmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_value_comp.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    Mymultiset::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
```  

## <a name="value_compare"></a> multiset::value_compare (STL/CLR)
İki öğenin değerleri için sıralama temsilcisi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>  
    value_compare;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kendi değer bağımsız değişkenleri sıralama belirler temsilci eşanlamlısı türüdür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_value_compare.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    Mymultiset::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
```  

## <a name="value_type"></a> multiset::value_type (STL/CLR)
Öğenin türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef generic_value value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türüdür `generic_value`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_value_type.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" using value_type   
    for (Mymultiset::iterator it = c1.begin(); it != c1.end(); ++it)   
        {   // store element in value_type object   
        Mymultiset::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="op_neq"></a> operator! = (multiset) (STL/CLR)
Eşit değildir karşılaştırma listeleyin.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Key>  
    bool operator!=(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `!(left == right)`. Test etmek için kullandığınız olup olmadığını `left` aynı sıralı değil `right` iki multisets öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_operator_ne.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] != [a b c] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[a b c] != [a b d] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] != [a b c] is False  
[a b c] != [a b d] is True  
```  

## <a name="op_lt"></a> İşleç&lt; (multiset) (STL/CLR)
Liste değerinden karşılaştırma.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Key>  
    bool operator<(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleci işlevi döndürür true ise, en düşük konumunun `i` kendisi için `!(right[i] < left[i])` Ayrıca, true olan `left[i] < right[i]`. Aksi takdirde, döndürür `left->size() < right->size()` test etmek için kullandığınız olup olmadığını `left` önce sıralı `right` iki multisets öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_operator_lt.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] < [a b c] is False  
[a b c] < [a b d] is True  
```  

## <a name="op_lteq"></a> İşleç&lt;= (multiset) (STL/CLR)
Küçük veya buna eşit listesinde karşılaştırma.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Key>  
    bool operator<=(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `!(right < left)`. Test etmek için kullandığınız olup olmadığını `left` sonra sıralı değil `right` iki multisets öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_operator_le.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] <= [a b c] is {0}",   
        c1 <= c1);   
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",   
        c2 <= c1);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] <= [a b c] is True  
[a b d] <= [a b c] is False  
```  

## <a name="op_eq"></a> operator == (multiset) (STL/CLR)
Eşit karşılaştırma listeleyin.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Key>  
    bool operator==(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi sıraları denetlediği yalnızca, true değerini döndürür `left` ve `right` aynı uzunlukta olması ve her konum için `i`, `left[i] ==` `right[i]`. Test etmek için kullandığınız olup olmadığını `left` aynı sıralı `right` iki multisets öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_operator_eq.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] == [a b c] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[a b c] == [a b d] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] == [a b c] is True  
[a b c] == [a b d] is False  
```  

## <a name="op_gt"></a> İşleç&gt; (multiset) (STL/CLR)
Liste karşılaştırma büyük.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Key>  
    bool operator>(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `right` `<` `left`. Test etmek için kullandığınız olup olmadığını `left` sonra sıralanmış `right` iki multisets öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_operator_gt.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] > [a b c] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[a b d] > [a b c] is {0}",   
        c2 > c1);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] > [a b c] is False  
[a b d] > [a b c] is True  
```  

## <a name="op_gteq"></a> İşleç&gt;= (multiset) (STL/CLR)
Karşılaştırma eşit veya daha büyük listesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Key>  
    bool operator>=(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `!(left < right)`. Test etmek için kullandığınız olup olmadığını `left` önce sıralı değil `right` iki multisets öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_multiset_operator_ge.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] >= [a b c] is {0}",   
        c1 >= c1);   
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",   
        c1 >= c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] >= [a b c] is True  
[a b c] >= [a b d] is False  
```  
  