---
title: Liste (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list
- cliext::list::assign
- cliext::list::assign
- cliext::list::back
- cliext::list::back_item
- cliext::list::begin
- cliext::list::clear
- cliext::list::const_iterator
- cliext::list::const_reference
- cliext::list::const_reverse_iterator
- cliext::list::difference_type
- cliext::list::empty
- cliext::list::end
- cliext::list::erase
- cliext::list::front
- cliext::list::front_item
- cliext::list::generic_container
- cliext::list::generic_iterator
- cliext::list::generic_reverse_iterator
- cliext::list::generic_value
- cliext::list::insert
- cliext::list::iterator
- cliext::list::list
- cliext::list::merge
- cliext::list::operator=
- cliext::list::pop_back
- cliext::list::pop_front
- cliext::list::push_back
- cliext::list::push_front
- cliext::list::rbegin
- cliext::list::reference
- cliext::list::remove
- cliext::list::remove_if
- cliext::list::rend
- cliext::list::resize
- cliext::list::reverse
- cliext::list::reverse_iterator
- cliext::list::size
- cliext::list::size_type
- cliext::list::sort
- cliext::list::splice
- cliext::list::swap
- cliext::list::to_array
- cliext::list::unique
- cliext::list::value_type
- cliext::operator!=(list)
- cliext::operator<(list)
- cliext::operator<=(list)
- cliext::operator==(list)
- cliext::operator>(list)
- cliext::operator>=(list)
dev_langs:
- C++
helpviewer_keywords:
- <cliext/list> header [STL/CLR]
- list class [STL/CLR]
- <list> header [STL/CLR]
- assign member [STL/CLR]
- assign member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- begin member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- erase member [STL/CLR]
- front member [STL/CLR]
- front_item member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- list member [STL/CLR]
- merge member [STL/CLR]
- operator= member [STL/CLR]
- pop_back member [STL/CLR]
- pop_front member [STL/CLR]
- push_back member [STL/CLR]
- push_front member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- remove member [STL/CLR]
- remove_if member [STL/CLR]
- rend member [STL/CLR]
- resize member [STL/CLR]
- reverse member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- sort member [STL/CLR]
- splice member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- unique member [STL/CLR]
- value_type member [STL/CLR]
- operator!=(list) member [STL/CLR]
- operator<(list) member [STL/CLR]
- operator<=(list) member [STL/CLR]
- operator==(list) member [STL/CLR]
- operator>(list) member [STL/CLR]
- operator>=(list) member [STL/CLR]
ms.assetid: a70c45c8-a257-4f6b-8434-b27ff6685bac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8eb64c41db0e6062f2be636ddce7e8cefe0bb32b
ms.sourcegitcommit: bad2441d1930275ff506d44759d283d94cccd1c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2018
ms.locfileid: "39376296"
---
# <a name="list-stlclr"></a>liste (STL/CLR)
Şablon sınıfı, iki yönlü erişime sahip öğelerin değişen uzunluktaki dizisini denetleyen bir nesneyi tanımlar. Kapsayıcı kullandığınız `list` öğeleri dizisi olarak çift yönlü bağlı düğümlerin listesini, her bir öğe depolama yönetmek için.  
  
 Aşağıdaki açıklamada `GValue` aynı *değer* ikinci bir başvuru türü olmadığı sürece olduğu durumda `Value^`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename Value>  
    ref class list  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        Microsoft::VisualC::StlClr::IList<GValue>  
    { ..... };  
```  
  
### <a name="parameters"></a>Parametreler  
 *Değer*  
 Denetlenen sıradaki öğenin türü.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/listesi >  
  
 **Namespace:** cliext 

## <a name="declarations"></a>Bildirimler  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|[list::const_iterator (STL/CLR)](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|  
|[list::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|  
|[list::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Denetlenen dizi için bir sabit ters yineleyici türü.|  
|[list::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|  
|[list::generic_container (STL/CLR)](#generic_container)|Kapsayıcı için genel arabirim türü.|  
|[list::generic_iterator (STL/CLR)](#generic_iterator)|Kapsayıcı için genel arabirimi için bir yineleyici türü.|  
|[list::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Kapsayıcı için genel arabirimi için ters yineleyici türü.|  
|[list::generic_value (STL/CLR)](#generic_value)|Kapsayıcı için genel arabirimi için bir öğe türü.|  
|[list::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|  
|[list::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|  
|[list::reverse_iterator (STL/CLR)](#reverse_iterator)|Denetlenen dizi için bir ters yineleyici türü.|  
|[list::size_type (STL/CLR)](#size_type)|İki öğe arasındaki işaretli mesafenin türü.|  
|[list::value_type (STL/CLR)](#value_type)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[list::assign (STL/CLR)](#assign)|Tüm öğeleri değiştirir.|  
|[list::back (STL/CLR)](#back)|Son öğeyi erişir.|  
|[list::begin (STL/CLR)](#begin)|Denetlenen dizinin başlangıcını belirtir.|  
|[list::clear (STL/CLR)](#clear)|Tüm öğeleri kaldırır.|  
|[list::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|  
|[list::end (STL/CLR)](#end)|Denetlenen dizinin bitişini belirtir.|  
|[list::erase (STL/CLR)](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|  
|[list::front (STL/CLR)](#front)|İlk öğeyi erişir.|  
|[list::insert (STL/CLR)](#insert)|Öğeleri belirtilen konumda ekler.|  
|[list::list (STL/CLR)](#list)|Bir kapsayıcı nesnesi oluşturur.|  
|[list::merge (STL/CLR)](#merge)|İki denetimli dizileri sıralı birleştirir.|  
|[list::pop_back (STL/CLR)](#pop_back)|Son öğeyi kaldırır.|  
|[list::pop_front (STL/CLR)](#pop_front)|İlk öğeyi kaldırır.|  
|[list::push_back (STL/CLR)](#push_back)|Yeni bir son öğesi ekler.|  
|[list::push_front (STL/CLR)](#push_front)|Yeni bir ilk öğe ekler.|  
|[list::rbegin (STL/CLR)](#rbegin)|Ters çevrilen denetlenen dizinin başlangıç belirler.|  
|[list::remove (STL/CLR)](#remove)|Belirtilen bir değere sahip bir öğe kaldırır.|  
|[list::remove_if (STL/CLR)](#remove_if)|Belirtilen test geçen öğeleri kaldırır.|  
|[list::rend (STL/CLR)](#rend)|Ters çevrilen denetlenen dizinin sonuna belirler.|  
|[list::resize (STL/CLR)](#resize)|Öğe sayısını değiştirir.|  
|[list::reverse (STL/CLR)](#reverse)|Denetlenen dizi tersine çevirir.|  
|[list::size (STL/CLR)](#size)|Öğe sayısını sayar.|  
|[list::sort (STL/CLR)](#sort)|Denetlenen diziyi sıralar.|  
|[list::splice (STL/CLR)](#splice)|Düğümler arasındaki bağlantılar restitches.|  
|[list::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|  
|[list::to_array (STL/CLR)](#to_array)|Denetlenen dizideki, yeni bir diziye kopyalar.|  
|[list::unique (STL/CLR)](#unique)|Belirtilen testi geçmesi bitişik öğeyi kaldırır.|  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[list::back_item (STL/CLR)](#back_item)|Son öğeyi erişir.|  
|[list::front_item (STL/CLR)](#front_item)|İlk öğeyi erişir.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[list::operator= (STL/CLR)](#op_as)|Denetlenen dizi değiştirir.|  
|[operator!= (list) (STL/CLR)](#op_neq)|Belirler bir `list` nesnesi, diğerine eşit değil `list` nesne.|  
|[operator< (list) (STL/CLR)](#op_lt)|Belirler bir `list` nesnedir daha az `list` nesne.|  
|[operator<= (list) (STL/CLR)](#op_lteq)|Belirler bir `list` nesnedir küçüktür veya eşittir diğerine `list` nesne.|  
|[operator== (list) (STL/CLR)](#op_eq)|Belirler bir `list` nesnedir diğerine eşit `list` nesne.|  
|[operator> (list) (STL/CLR)](#op_gt)|Belirler bir `list` nesnedir diğerinden daha büyük `list` nesne.|  
|[operator>= (list) (STL/CLR)](#op_gteq)|Belirler bir `list` nesnedir büyüktür veya eşittir diğerine `list` nesne.|  
  
## <a name="interfaces"></a>Arabirimler  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Bir nesne çoğaltın.|  
|<xref:System.Collections.IEnumerable>|Öğeleri dizisi.|  
|<xref:System.Collections.ICollection>|Öğe grubunu koruyun.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Türü belirtilmiş öğelerini dizisi.|  
|<xref:System.Collections.Generic.ICollection%601>|Türü belirtilmiş bir öğe grubunu koruyun.|  
|IList\<değer >|Genel kapsayıcı korur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne ayırır ve bir çift yönlü bağlantı listesi tek tek düğümler olarak denetlediği dizi için depolama serbest bırakır. Bu, öğeleri hiçbir zaman bir düğüm içeriğini diğerine kopyalama tarafından düğümleri arasındaki bağlantıları değiştirerek yeniden düzenler. Bu, ekleyin ve özgürce rahatsız edici kalan öğeleri olmadan öğeleri kaldırın anlamına gelir. Bu nedenle, bir şablon sınıfı için temel alınan kapsayıcısı için iyi bir aday listedir [kuyruk (STL/CLR)](../dotnet/queue-stl-clr.md) veya şablon sınıfıdır [yığın (STL/CLR)](../dotnet/stack-stl-clr.md).  
  
 A `list` nesnesi bitişik öğelere denetlenen dizideki bir öğeyi belirleyen bir yineleyici verilen adım yani çift yönlü yineleyiciler destekler. Özel bir baş düğüm tarafından döndürülen yineleyici karşılık gelen [list::end (STL/CLR)](../dotnet/list-end-stl-clr.md)`()`. Denetlenen dizi içindeki son öğeden ulaşmak için bu yineleyici varsa azaltma. Baş düğüm erişmek için bir liste yineleyici artırabilirsiniz ve bu sonra eşittir karşılaştıracağız `end()`. Ancak tarafından döndürülen yineleyici başvurulamıyor `end()`.  
  
 Doğrudan bir rastgele erişim yineleyici gerektiren sayısal konumunu--belirtilen bir liste öğesine başvuramaz unutmayın. Bir liste, bu nedenle *değil* kullanılabilir şablon sınıfı için temel alınan kapsayıcı olarak [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md).  
  
 Sırayla ilişkilendirilmiş kapsayıcısı için bir tanıtıcı depolar, ilişkili liste düğümü için bir tanıtıcı bir liste yineleyici depolar. Yineleyiciler yalnızca ilişkili kapsayıcı nesneleri ile kullanabilirsiniz. Bir liste Yineleyici, onun ilişkili liste düğümü bazı listesiyle ilişkili olduğu sürece geçerli kalır. Ayrıca, geçerli bir yineleyici yineleyicisine--erişmek veya eşit değildir sürece bu atayan--öğe değeri değiştirmek için kullanabilirsiniz `end()`.  
  
 Silme veya bir öğenin kaldırılması için depolanan değerine yıkıcı çağırır. Kapsayıcı yok etme tüm öğelerini siler. Bu nedenle, hiçbir öğe'nin kapsayıcı daha uzun sürmesi başvuru sınıfı, öğe türü olan bir kapsayıcı sağlar. Ancak, bir kapsayıcı tutamaçlarından yaptığı unutmayın *değil* öğelerini yok edin.  
  
## <a name="members"></a>Üyeler

## <a name="assign"></a> List::Assign (STL/CLR)
Tüm öğeleri değiştirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Sayısı*  
 Eklenecek öğe sayısı.  
  
 *ilk*  
 Eklenecek Aralık başlangıcı.  
  
 *Son*  
 Eklenecek aralık sonu.  
  
 *sağ*  
 Eklemek için sabit listesi.  
  
 *VAL*  
 Eklenecek öğenin değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi bir yineleme ile denetlenen dizideki değiştirir *sayısı* değerin *val*. Öğelerle kapsayıcıyı doldurmak için tüm aynı değere sahip kullanırsınız.  
  
 Varsa `InIt` bir tamsayı türüdür ikinci üye işlevi gibi davranır `assign((size_type)first, (value_type)last)`. Aksi takdirde, denetlenen dizideki dizisiyle değiştirir [`first`, `last`). Denetlenen bir kopyasını sıra yapmak için başka bir dizisi kullanırsınız.  
  
 Üçüncü üye işlevi, numaralandırıcı tarafından belirtilen sıra ile denetlenen dizideki değiştirir. *doğru*. Denetlenen dizideki bir numaralandırıcı tarafından açıklanan bir sıralı bir kopyasını kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_assign.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::list<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    cliext::list<wchar_t>::iterator it = c1.end();   
    c2.assign(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an enumeration   
    c2.assign(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
x x x x x x  
a b  
a b c  
```  
 
## <a name="back"></a> List::Back (STL/CLR)
Son öğeyi erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
reference back();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi, denetlenen dizinin boş olması gereken son öğeye bir başvuru döndürür. Son öğe mevcut bildiğinizde erişmek için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_back.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back() = {0}", c1.back());   
  
// alter last item and reinspect   
    c1.back() = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
back() = c  
 a b x  
```  

## <a name="back_item"></a> List::back_item (STL/CLR)
Son öğeyi erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
property value_type back_item;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Özellik, son öğe boş olmalıdır denetlenen dizinin erişir. Okumak veya son öğe mevcut bildiğinizde yazmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_back_item.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back_item = {0}", c1.back_item);   
  
// alter last item and reinspect   
    c1.back_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
back_item = c  
 a b x  
```  

## <a name="begin"></a> List::Begin (STL/CLR)
Denetlenen dizinin başlangıcını belirtir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
iterator begin();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi, denetlenen dizinin ya da boş bir dizi bitiminin ötesinde yalnızca ilk öğeyi belirleyen bir rastgele erişim yineleyici döndürür. Gösteren bir yineleyici almak için kullandığınız `current` denetlenen dizideki ancak durumu başına denetlenen dizinin uzunluğu değişirse değiştirebilirsiniz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_begin.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
*begin() = a  
*++begin() = b  
 x y c  
```  

## <a name="clear"></a> List::Clear (STL/CLR)
Tüm öğeleri kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void clear();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi etkili bir şekilde çağıran [list::erase (STL/CLR)](../dotnet/list-erase-stl-clr.md) `(` [list::begin (STL/CLR)](../dotnet/list-begin-stl-clr.md) `(),` [list::end (STL/CLR)](../dotnet/list-end-stl-clr.md) `())`. Denetlenen dizi boş olduğundan emin olmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_clear.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
  
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

## <a name="const_iterator"></a> List::const_iterator (STL/CLR)
Denetlenen dizi için bir sabit yineleyici türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef T2 const_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bilinmeyen türde bir nesne tanımlayan bir tür `T2` denetlenen dizi için sabit bir rastgele erişim yineleyici olarak verebilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_const_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::list<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" {0}", *cit);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  

## <a name="const_reference"></a> List::const_reference (STL/CLR)
Bir öğe için sabit bir başvuru türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef value_type% const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğe için sabit bir başvuru türü açıklar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_const_reference.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::list<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        {   // get a const reference to an element   
        cliext::list<wchar_t>::const_reference cref = *cit;   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  

## <a name="const_reverse_iterator"></a> List::const_reverse_iterator (STL/CLR)
Denetlenen dizi için bir sabit ters yineleyici türü...  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef T4 const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bilinmeyen türde bir nesne tanımlayan bir tür `T4` denetlenen dizi için bir sabit ters yineleyici olarak verebilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::list<wchar_t>::const_reverse_iterator crit = c1.rbegin();   
    cliext::list<wchar_t>::const_reverse_iterator crend = c1.rend();   
    for (; crit != crend; ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c b a  
```  

## <a name="difference_type"></a> List::difference_type (STL/CLR)
İki öğe arasındaki işaretli mesafenin türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İmzalı öğe sayısını tanımlayan bir tür.  
  
### <a name="example"></a>Örnek  
  
```cpp 
// cliext_list_difference_type.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::list<wchar_t>::difference_type diff = 0;   
    for (cliext::list<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it) ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
  
// compute negative difference   
    diff = 0;   
    for (cliext::list<wchar_t>::iterator it = c1.end();   
        it != c1.begin(); --it) --diff;   
    System::Console::WriteLine("begin()-end() = {0}", diff);   
    return (0);   
    }  
```  
  
```Output  
 a b c  
end()-begin() = 3  
begin()-end() = -3  
```  

## <a name="empty"></a> List::Empty (STL/CLR)
Bir öğe olup olmadığını sınar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
bool empty();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi boş bir denetlenmiş dizi için true değerini döndürür. Eşdeğerdir [list::size (STL/CLR)](../dotnet/list-size-stl-clr.md)`() == 0`. Liste boş olup olmadığını sınamak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_empty.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
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

## <a name="end"></a> List::End (STL/CLR)
Denetlenen dizinin bitişini belirtir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
iterator end();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi, denetlenen dizinin sonuna hemen ötesine işaret eden bir rastgele erişim yineleyici döndürür. Denetlenen dizinin sonuna belirten bir yineleyici almak için kullanın. kendi durum eklenmemişse denetlenen dizinin uzunluğu değişirse değiştiremezsiniz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_end.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    cliext::list<wchar_t>::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
*-- --end() = b  
*--end() = c  
 a x y  
```  

## <a name="erase"></a> List::ERASE (STL/CLR)
Belirtilen konumlardaki öğeleri kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *ilk*  
 Silme aralığını başlangıcı.  
  
 *Son*  
 Silinecek aralığı sonu.  
  
 *Burada*  
 Silinecek öğe.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi tarafından denetlenen dizinin öğeyi kaldırır *nerede*. Tek bir öğe kaldırmak için kullanın.  
  
 İkinci üye işlevi öğeleri denetlenen dizinin aralıktaki kaldırır. [`first`, `last`). Sıfır veya daha fazla ardışık öğeleri kaldırmak için kullanın.  
  
 Her iki üye işlev kaldırılan tüm öğelerin ötesindeki ilk öğeyi belirleyen bir yineleyici döndürür veya [list::end (STL/CLR)](../dotnet/list-end-stl-clr.md) `()` böyle bir öğe varsa.  
  
 Öğeleri silme, öğe sayısıyla doğrusal silinme sonuna yakın son sırasının arasındaki öğelerin sayısı. (Bir veya daha fazla öğe dizisi sonunda ya da silme, hiçbir öğe kopya ortaya çıkar.)  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_erase.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.push_back(L'd');   
    c1.push_back(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    cliext::list<wchar_t>::iterator it = c1.end();   
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

## <a name="front"></a> List::Front (STL/CLR)
İlk öğeyi erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
reference front();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi, denetlenen dizinin boş olması gereken ilk öğeye bir başvuru döndürür. Okumak veya mevcut bildiğinizde ilk öğeyi yazmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_front.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first item   
    System::Console::WriteLine("front() = {0}", c1.front());   
  
// alter first item and reinspect   
    c1.front() = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
front() = a  
 x b c  
```  

## <a name="front_item"></a> List::front_item (STL/CLR)
İlk öğeyi erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
property value_type front_item;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliği ilk öğe boş olmalıdır denetlenen dizinin erişir. Okumak veya mevcut bildiğinizde ilk öğeyi yazmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_front_item.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first item   
    System::Console::WriteLine("front_item = {0}", c1.front_item);   
  
// alter first item and reinspect   
    c1.front_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
front_item = a  
 x b c  
```  

## <a name="generic_container"></a> List::generic_container (STL/CLR)
Kapsayıcı için genel arabirim türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef Microsoft::VisualC::StlClr::  
    IList<generic_value>  
    generic_container;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu şablon kapsayıcı sınıfı için genel arabirim tanımlayan bir tür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_generic_container.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->insert(gc1->end(), L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.push_back(L'e');   
  
    System::Collections::IEnumerator^ enum1 =   
        gc1->GetEnumerator();   
    while (enum1->MoveNext())   
        System::Console::Write(" {0}", enum1->Current);   
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

## <a name="generic_iterator"></a> List::generic_iterator (STL/CLR)
Kapsayıcı için genel arabirimi ile kullanmak için bir yineleyici türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef Microsoft::VisualC::StlClr::Generic::  
    ContainerBidirectionalIterator<generic_value>  
    generic_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Genel arabirim ile bu şablon kapsayıcı sınıfı için kullanılabilecek genel bir yineleyici türü açıklar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_generic_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::list<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::list<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
a a c  
```  

## <a name="generic_reverse_iterator"></a> List::generic_reverse_iterator (STL/CLR)
Kapsayıcı için genel arabirimi ile kullanmak için bir ters yineleyici türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef Microsoft::VisualC::StlClr::Generic::  
    ReverseBidirectionalIterator<generic_value> generic_reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Genel arabirim ile bu şablon kapsayıcı sınıfı için kullanılabilecek genel bir ters yineleyici türü açıklar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_generic_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::list<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();   
    cliext::list<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
a c c  
```  

## <a name="generic_value"></a> List::generic_value (STL/CLR)
Kapsayıcı için genel arabirimi ile kullanmak için bir öğe türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef GValue generic_value;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Türünde bir nesneyi tanımlayan bir tür `GValue` açıklayan yönelik genel arabirimi için bu şablonu kapsayıcı sınıfı ile kullanmak için depolanan öğenin değeri.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_generic_value.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::list<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::list<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
a a c  
```  

## <a name="insert"></a> List::insert (STL/CLR)
Öğeleri belirtilen konumda ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Sayısı*  
 Eklenecek öğe sayısı.  
  
 *ilk*  
 Eklenecek Aralık başlangıcı.  
  
 *Son*  
 Eklenecek aralık sonu.  
  
 *sağ*  
 Eklemek için sabit listesi.  
  
 *VAL*  
 Eklenecek öğenin değeri.  
  
 *Burada*  
 Öncesine İliştir kapsayıcısında yer.  
  
### <a name="remarks"></a>Açıklamalar  
 Eklemeleri, işaret ettiği öğesinden önce işlevlerin her üyenin *burada* denetlenen dizide bir dizisi, diğer işlenen tarafından belirtilen.  
  
 İlk üye işlevi değere sahip bir öğe ekler *val* ve yeni eklenen öğeyi belirleyen bir yineleyici döndürür. Bir yineleyici tarafından atanan bir yere önce tek bir öğe eklemek için kullanın.  
  
 İkinci üye işlevi bir tekrarını ekler *sayısı* değerin *val*. Tüm kopyaları aynı değeri sıfır veya daha fazla ardışık öğeleri eklemek için kullanın.  
  
 Varsa `InIt` bir tamsayı türüdür üçüncü üye işlevi gibi davranır `insert(where, (size_type)first, (value_type)last)`. Aksi takdirde, bunu dizisi ekler [`first`, `last`). Başka bir diziden kopyalanan sıfır veya daha fazla ardışık öğeleri eklemek için kullanın.  
  
 Dördüncü üye işlevi tarafından belirlenen dizisi ekler *doğru*. Bir numaralandırıcı tarafından açıklanan bir dizi eklemek için kullanın.  
  
 Tek bir öğe eklendiğinde öğe sayısıyla doğrusal noktasını yakın son sırasının arasındaki öğelerin sayısı. (Bir veya daha fazla öğe dizisi ya da sonunda eklerken, hiçbir öğe kopya gerçekleşir.) Varsa `InIt` bir giriş yineleyici üçüncü üye işlevi, tek bir ekleme dizideki her öğe için etkili bir şekilde gerçekleştirir. Aksi takdirde eklerken `N` öğeleri öğe sayısıyla doğrusal olarak `N` artı noktasını yakın son sırasının arasındaki öğelerin sayısı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_insert.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using iterator   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::list<wchar_t> c2;   
    c2.insert(c2.begin(), 2, L'y');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    it = c1.end();   
    c2.insert(c2.end(), c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    c2.insert(c2.begin(),   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using index   
    it = c2.begin();   
    ++it, ++it, ++it;   
    c2.insert(it, L'z');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
```  
  
```Output  
 a b c  
insert(begin()+1, L'x') = x  
 a x b c  
 y y  
 y y a x b  
 a x b c y y a x b  
```  

## <a name="iterator"></a> List::iterator (STL/CLR)
Denetlenen dizi için bir yineleyici türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef T1 iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bilinmeyen türde bir nesne tanımlayan bir tür `T1` denetlenen dizi için bir rastgele erişim yineleyici olarak verebilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    it = c1.begin();   
    *it = L'x';   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
x b c  
```  

## <a name="list"></a> List::List (STL/CLR)
Bir kapsayıcı nesnesi oluşturur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
list();  
list(list<Value>% right);  
list(list<Value>^ right);  
explicit list(size_type count);  
list(size_type count, value_type val);  
template<typename InIt>  
    list(InIt first, InIt last);  
list(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Sayısı*  
 Eklenecek öğe sayısı.  
  
 *ilk*  
 Eklenecek Aralık başlangıcı.  
  
 *Son*  
 Eklenecek aralık sonu.  
  
 *sağ*  
 Nesne veya eklenecek aralık.  
  
 *VAL*  
 Eklenecek öğenin değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
 Oluşturucu:  
  
 `list();`  
  
 Denetlenen dizideki herhangi bir öğesi ile başlatır. Boş bir başlangıç denetlenmiş dizi belirtmek için kullanın.  
  
 Oluşturucu:  
  
 `list(list<Value>% right);`  
  
 Denetlenen dizi sırası başlatır [`right.begin()`, `right.end()`). Liste nesnesi tarafından denetlenen dizinin bir kopyasını olan ilk denetimli bir sıra belirtmek için kullandığınız *doğru*.  
  
 Oluşturucu:  
  
 `list(list<Value>^ right);`  
  
 Denetlenen dizi sırası başlatır [`right->begin()`, `right->end()`). Olan tanıtıcısı liste nesnesi tarafından denetlenen dizinin bir kopyasını olan ilk denetimli bir sıra belirtmek için kullandığınız *doğru*.  
  
 Oluşturucu:  
  
 `explicit list(size_type count);`  
  
 Denetlenen dizi ile başlatır *sayısı* öğelerle her değer `value_type()`. Öğelerle kapsayıcıyı doldurmak için tüm varsayılan değer olan kullanırsınız.  
  
 Oluşturucu:  
  
 `list(size_type count, value_type val);`  
  
 Denetlenen dizi ile başlatır *sayısı* öğelerle her değer *val*. Öğelerle kapsayıcıyı doldurmak için tüm aynı değere sahip kullanırsınız.  
  
 Oluşturucu:  
  
 `template<typename InIt>`  
  
 `list(InIt first, InIt last);`  
  
 Denetlenen dizi sırası başlatır [`first`, `last`). Denetlenen dizi, başka bir dizisi kopyasını kullanın.  
  
 Oluşturucu:  
  
 `list(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 Denetlenen dizi numaralandırıcı tarafından belirtilen sıra başlatır *doğru*. Denetlenen dizi başka bir sıralı bir numaralandırıcı tarafından açıklanan bir kopyasını kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_construct.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container   
    cliext::list<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::list<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::list<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::list<wchar_t>::iterator it = c3.end();   
    cliext::list<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::list<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::list<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::list<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
```  
  
```Output  
size() = 0  
 0 0 0  
 x x x x x x  
 x x x x x  
 x x x x x x  
 x x x x x x  
 x x x x x x  
```  

## <a name="merge"></a> List::Merge (STL/CLR)
İki denetimli dizileri sıralı birleştirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void merge(list<Value>% right);  
template<typename Pred2>  
    void merge(list<Value>% right, Pred2 pred);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Pred*  
 Karşılaştırıcı öğesi çiftleri için.  
  
 *sağ*  
 Birleştirmeye kapsayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi tarafından denetlenen dizinin tüm öğeleri kaldırır *doğru* ve denetlenen dizide ekleyebilirsiniz. Her iki dizileri tarafından daha önce sıralanmalıdır `operator<` --öğeleri gerekir azaltamazsınız değeri ya da sırası boyunca ilerledikçe. Sonuç dizisi ayrıca göre sıralanmış `operator<`. Bu üye işlevi, değeri artıran dizisini değeri artıran iki diziyi birleştirme için kullanın.  
  
 Dizileri göre sıralanmış dışında ikinci üye işlevi, ilk olarak davranır `pred`  --  `pred(X, Y)` herhangi bir öğe için false olmalıdır `X` , öğesi izleyen `Y` sırada. Bir koşul işlevi veya belirttiğiniz temsilci tarafından sıralanan iki diziyi birleştirmek için kullanın.  
  
 Hem işlevler kararlı bir birleştirme--sonuç denetlenen dizide herhangi birini kullanarak özgün denetlenen sıralar öğe çiftinin ters çevrilir. Ayrıca, bir öğe çiftinin varsa `X` ve `Y` eşdeğer sıralamaya--sonuç denetlenen dizide sahip `!(X < Y) && !(X < Y)` -- tarafındandenetlenendizininözgündenetlenendizidekiöğedenöncebiröğegörüntülenir*doğru*.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_merge.cpp   
// compile with: /clr   
#include <cliext/list>   
  
typedef cliext::list<wchar_t> Mylist;   
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'c');   
    c1.push_back(L'e');   
  
// display initial contents " a c e"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    cliext::list<wchar_t> c2;   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
    c2.push_back(L'f');   
  
// display initial contents " b d f"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// merge and display   
    cliext::list<wchar_t> c3(c1);   
    c3.merge(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
  
// sort descending, merge descending, and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.merge(c1, cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    return (0);   
    }  
```  
  
```Output  
 a c e  
 b d f  
 a b c d e f  
c2.size() = 0  
 e c a  
 f e d c b a  
 f e e d c c b a a  
c1.size() = 0  
```  

## <a name="op_as"></a> List::operator (STL/CLR) =
Denetlenen dizi değiştirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
list<Value>% operator=(list<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *sağ*  
 Kopyalanacak kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci kopyaları *doğru* ardından nesneye döndürür `*this`. Denetlenen dizi denetlenen dizide bir kopyasını değiştirmek için kullandığınız *doğru*.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_operator_as.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
```  

## <a name="pop_back"></a> List::pop_back (STL/CLR)
Son öğeyi kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void pop_back();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi, denetlenen dizinin boş olması gereken son öğeyi kaldırır. Listenin arkasındaki bir öğe tarafından kısaltmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_pop_back.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop_back();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b  
```  

## <a name="pop_front"></a> List::pop_front (STL/CLR)
İlk öğeyi kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void pop_front();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi, denetlenen dizinin boş olması gereken ilk öğeyi kaldırır. Önündeki bir öğe listesi kısaltmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_pop_front.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop_front();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
b c  
```  

## <a name="push_back"></a> List::push_back (STL/CLR)
Yeni bir son öğesi ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void push_back(value_type val);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi değere sahip bir öğe ekler `val` denetlenen dizinin sonunda. Başka bir öğe listesine eklemek için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_push_back.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
```  
  
## <a name="push_front"></a> List::push_front (STL/CLR)
Yeni bir ilk öğe ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void push_front(value_type val);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi değere sahip bir öğe ekler `val` denetlenen dizinin başında. Başka bir öğe listesine önüne eklediğinizden kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_push_front.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_front(L'a');   
    c1.push_front(L'b');   
    c1.push_front(L'c');   
  
// display contents " c b a"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c b a  
```  

## <a name="rbegin"></a> List::rbegin (STL/CLR)
Ters çevrilen denetlenen dizinin başlangıç belirler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
reverse_iterator rbegin();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi, denetlenen dizinin ya da boş bir dizi başlangıcı hemen ötesinde son öğeyi belirleyen bir ters yineleyici döndürür. Bu nedenle, atayan `beginning` ters dizisi. Gösteren bir yineleyici almak için kullandığınız `current` denetlenen dizinin uzunluğu değişirse başlangıcına ters sırada görülen denetlenen dizideki ancak durumunu değiştirebilirsiniz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_rbegin.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
*rbegin() = c  
*++rbegin() = b  
 a y x  
```  

## <a name="reference"></a> List::Reference (STL/CLR)
Bir öğe için bir başvuru türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Öğeye bir başvuru türü açıklar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_reference.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::list<wchar_t>::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
  
// modify contents " a b c"   
    for (it = c1.begin(); it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::list<wchar_t>::reference ref = *it;   
  
        ref += (wchar_t)(L'A' - L'a');   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
A B C  
```  

## <a name="remove"></a> List::Remove (STL/CLR)
Belirtilen bir değere sahip bir öğe kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void remove(value_type val);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *VAL*  
 Kaldırılacak öğenin değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi bir öğe denetlenen dizide için kaldıran `((System::Object^)val)->Equals((System::Object^)x)` (varsa) geçerlidir. Rastgele bir öğe belirtilen değerle silmek için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_remove.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// fail to remove and redisplay   
    c1.remove(L'A');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();  
  
// remove and redisplay   
    c1.remove(L'b');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
a b c  
a c  
```  

## <a name="remove_if"></a> List::remove_if (STL/CLR)
Belirtilen test geçen öğeleri kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename Pred1>  
    void remove_if(Pred1 pred);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Pred*  
 Öğeleri kaldırmak test edin.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetlenen dizi (siler) üye işlevi kaldırır her öğe `X` hangi `pred(X)` geçerlidir. Bir işlev veya temsilci belirlediğiniz bir koşulu karşılayan tüm öğeleri kaldırmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_remove_if.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'b');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b b b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// fail to remove and redisplay   
    c1.remove_if(cliext::binder2nd<cliext::equal_to<wchar_t> >(   
        cliext::equal_to<wchar_t>(), L'd'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// remove and redisplay   
    c1.remove_if(cliext::binder2nd<cliext::not_equal_to<wchar_t> >(   
        cliext::not_equal_to<wchar_t>(), L'b'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b b b c  
a b b b c  
b b b  
``` 

## <a name="rend"></a> List::rend (STL/CLR)
Ters çevrilen denetlenen dizinin sonuna belirler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
reverse_iterator rend();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi hemen ötesine işaret eden bir başlangıç değerinin denetlenen dizideki ters yineleyici döndürür. Bu nedenle, atayan `end` ters dizisi. Gösteren bir yineleyici almak için kullandığınız `current` denetlenen dizinin uzunluğu değişirse sonuna ters sırada görülen denetlenen dizideki ancak durumunu değiştirebilirsiniz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_rend.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
 a b c  
*-- --rend() = b  
*--rend() = a  
 y x c  
```  

## <a name="resize"></a> List::resize (STL/CLR)
Öğe sayısını değiştirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *new_size*  
 Denetlenen dizinin yeni boyutu.  
  
 *VAL*  
 Doldurma öğesinin değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Her iki üye işlevleri emin [list::size (STL/CLR)](../dotnet/list-size-stl-clr.md) `()` henceforth döndürür *new_size*. Denetlenen dizi uzun yapmanız gerekiyorsa, ilk üye işlevi öğeleri değerle ekler `value_type()`ikinci üye işlevi öğeleri değerle ekler korurken *val*. Denetlenen dizi kısa yapmak için her iki üye işlevleri etkili bir şekilde son öğeyi silme [list::size (STL/CLR)](../dotnet/list-size-stl-clr.md) `() -` `new_size` kez. Denetlenen dizi boyutu olduğundan emin olmak için kullandığınız *new_size*, kesme ya da geçerli denetlenen dizideki doldurma.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_resize.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::list<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
size() = 0  
 0 0 0 0  
size() = 0  
 x x x x x  
```  

## <a name="reverse"></a> List::reverse (STL/CLR)
Denetlenen dizi tersine çevirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void reverse();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi, denetlenen dizideki tüm öğelerin sırasını tersine çevirir. Bir öğe listesi yansıtacak şekilde kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_reverse.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// reverse and redisplay   
    c1.reverse();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
c b a  
```  

## <a name="reverse_iterator"></a> List::reverse_iterator (STL/CLR)
Denetlenen dizi için bir ters yineleyici türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef T3 reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bilinmeyen türde bir nesne tanımlayan bir tür `T3` denetlenen dizi için bir ters yineleyici olarak verebilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    rit = c1.rbegin();   
    *rit = L'x';   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
c b a  
x b a  
```  
  
## <a name="size"></a> List::size (STL/CLR)
Öğe sayısını sayar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
size_type size();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi, denetlenen dizinin uzunluğunu döndürür. Şu anda denetlenen dizideki öğelerin sayısını belirlemek için kullanın. Tümü, önem verdiğiniz ise dizisi bakın, sıfır olmayan boyutu olup [list::empty (STL/CLR)](../dotnet/list-empty-stl-clr.md)`()`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_size.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
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

## <a name="size_type"></a> List::size_type (STL/CLR)
İki öğe arasındaki işaretli mesafenin türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir negatif olmayan öğe sayısını tanımlayan bir tür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_size_type.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::list<wchar_t>::size_type diff = 0;   
    for (cliext::list<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
```  
  
```Output  
 a b c  
end()-begin() = 3  
```

## <a name="sort"></a> List::sort (STL/CLR)
Denetlenen diziyi sıralar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void sort();  
template<typename Pred2>  
    void sort(Pred2 pred);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Pred*  
 Karşılaştırıcı öğesi çiftleri için.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi, böylece göre sıralanmış, denetlenen dizideki öğelerin yeniden düzenler `operator<` --öğeleri azaltamazsınız değerinde sırası boyunca ilerledikçe. Sırası artan düzende sıralamak için bu üye işlevini kullanın.  
  
 Sıra göre sıralanmış dışında ikinci üye işlevi, ilk olarak davranır `pred`  --  `pred(X, Y)` herhangi bir öğe için yanlış `X` , öğesi izleyen `Y` sonuç sırada. Koşul işlevi veya temsilci belirttiğiniz sırayla dizisi sıralamak için kullanın.  
  
 Hem tutarlı bir sıralama işlevleri gerçekleştiren--hiçbir çifti özgün denetlenen dizideki öğelerin elde edilen denetlenen dizide ters çevrilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_sort.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort descending and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort ascending and redisplay   
    c1.sort();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
c b a  
a b c  
``` 

## <a name="splice"></a> List::splice (STL/CLR)
Düğümler arasındaki bağlantılar restitch.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void splice(iterator where, list<Value>% right);  
void splice(iterator where, list<Value>% right,  
    iterator first);  
void splice(iterator where, list<Value>% right,  
    iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *ilk*  
 Splice aralığını başlangıcı.  
  
 *Son*  
 Splice aralığın bitiş olayı.  
  
 *sağ*  
 Gelen splice için kapsayıcı.  
  
 *Burada*  
 Önce splice kapsayıcısında yer.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi tarafından denetlenen dizinin ekler *doğru* denetlenen sıradaki öğenin işaret ettiği önce *nerede*. Ayrıca tüm öğeleri kaldırır *doğru*. (`%right` değil olmalıdır `this`.) Tüm bir listeyi diğerinin içine splice için kullanın.  
  
 İkinci üye işlevi tarafından işaret edilen öğeyi kaldırır *ilk* tarafından denetlenen dizideki *doğru* ve denetlenen sıradaki öğenin işaret ettiği önce ekler *burada* . (Varsa `where` `==` `first` `||` `where` `== ++first`, herhangi bir değişiklik meydana gelir.) Başka bir listenin tek bir öğe splice için kullanın.  
  
 Üçüncü üye işlevi tarafından belirlenen alt aralığı ekler [`first`, `last`) tarafından denetlenen dizinin gelen *doğru* tarafından denetlenen sıradaki öğenin önce *burada*. Bu ayrıca özgün alt aralığı tarafından denetlenen dizinin kaldırır *doğru*. (Eğer `right` `==` `this`, aralığı [`first`, `last`) işaret ettiği öğe içermemelidir *nerede*.) Splice sıfır veya daha fazla öğe bir listeden bir alt dizi diğeriyle birleştirmek için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp
// cliext_list_splice.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// splice to a new list   
    cliext::list<wchar_t> c2;   
    c2.splice(c2.begin(), c1);   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return one element   
    c1.splice(c1.end(), c2, c2.begin());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return remaining elements   
    c1.splice(c1.begin(), c2, c2.begin(), c2.end());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
    return (0);   
    }  
```  
  
```Output  
 a b c  
c1.size() = 0  
 a b c  
 a  
 b c  
 b c a  
c2.size() = 0  
```    

## <a name="swap"></a> List::Swap (STL/CLR)
İki kapsayıcının içeriğinin yerini değiştirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void swap(list<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *sağ*  
 Kapsayıcı içeriğini değiştirmek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetlenen diziyi üye işlevi değiştirir `*this` ve *doğru*. Bunu Sabit sürede yapar ve hiçbir özel durum oluşturur. İki kapsayıcının içeriğinin değişimi için hızlı bir şekilde kullanırsınız.  
  
### <a name="example"></a>Örnek  
  
```cpp 
// cliext_list_swap.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::list<wchar_t> c2(5, L'x');   
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
x x x x x  
x x x x x  
a b c  
```   

## <a name="to_array"></a> List::to_array (STL/CLR)
Denetlenen dizideki, yeni bir diziye kopyalar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
cli::array<Value>^ to_array();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi, denetlenen bir dizi içeren bir dizi döndürür. Dizi formunda denetlenen dizinin bir kopyasını almak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_to_array.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push_back(L'd');   
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

## <a name="unique"></a> List::Unique (STL/CLR)
Belirtilen testi geçmesi bitişik öğeyi kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void unique();  
template<typename Pred2>  
    void unique(Pred2 pred);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Pred*  
 Karşılaştırıcı öğesi çiftleri için.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi kaldırır (siler) denetimli dizisinden karşılaştıran her öğe varsa, bir önceki öğeye--eşit öğesi `X` öğesi önündeki `Y` ve `X == Y`, üye işlevi kaldırır `Y`. Her alt dizi bitişik öğelerin tümü değil tek kopyası kaldırmak için bu karşılaştırma eşit kullanırsınız. Unutmayın denetlenen dizideki sıralandığına, gibi çağırarak gibi [list::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)`()`, üye işlevi öğeleri yalnızca benzersiz değerler ile bırakır. (Bu nedenle adı).  
  
 Her öğeyi kaldırır dışında ikinci üye işlevi, ilk olarak davranır `Y` bir öğe aşağıdaki `X` hangi `pred(X, Y)`. Her alt diziyi bir koşul işlevi veya belirttiğiniz temsilci karşılayan bitişik öğelerin tümü değil tek kopyası kaldırmak için kullanın. Unutmayın denetlenen dizideki sıralandığına, gibi çağırarak gibi `sort(pred)`, üye işlevi herhangi bir öğe ile eşdeğer sıralamaya sahip olmayan öğeleri bırakır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_unique.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique   
    cliext::list<wchar_t> c2(c1);   
    c2.unique();   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique(not_equal_to)   
    c2 = c1;   
    c2.unique(cliext::not_equal_to<wchar_t>());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a a b c  
a b c  
a a  
```  

## <a name="value_type"></a> List::value_type (STL/CLR)
Öğenin türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
typedef Value value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eşanlamlı türüdür *değer*.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_value_type.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using value_type   
    for (cliext::list<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   // store element in value_type object   
        cliext::list<wchar_t>::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
```  
  
```Output  
a b c  
``` 

## <a name="op_neq"></a> işleç! = (list) (STL/CLR)
Eşit değildir karşılaştırma listeleyin.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename Value>  
    bool operator!=(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Sol*  
 Karşılaştırılacak sol kapsayıcısı.  
  
 *sağ*  
 Karşılaştırılacak doğru kapsayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevini döndürür `!(left == right)`. Test etmek için kullandığınız olmadığını *sol* aynı sıralı değil *doğru* listelerini karşılaştırılan öğe öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_operator_ne.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
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

## <a name="op_lt"></a> İşleç&lt; (liste) (STL/CLR)
Liste değerinden karşılaştırma.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename Value>  
    bool operator<(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Sol*  
 Karşılaştırılacak sol kapsayıcısı.  
  
 *sağ*  
 Karşılaştırılacak doğru kapsayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür true ise, en düşük konumu için `i` hangi `!(right[i] < left[i])` de true olduğu `left[i] < right[i]`. Aksi halde `left->size() < right->size()` test etmek için kullandığınız olmadığını *sol* önceyse *doğru* listelerini karşılaştırılan öğe öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_operator_lt.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
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

## <a name="op_lteq"></a> İşleç&lt;(liste) (STL/CLR) =
Küçüktür veya eşittir listesinde karşılaştırma.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename Value>  
    bool operator<=(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Sol*  
 Karşılaştırılacak sol kapsayıcısı.  
  
 *sağ*  
 Karşılaştırılacak doğru kapsayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevini döndürür `!(right < left)`. Test etmek için kullandığınız olmadığını *sol* sonra sıralı değil *doğru* listelerini karşılaştırılan öğe öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_operator_le.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
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

## <a name="op_eq"></a> işleç == (liste) (STL/CLR)
Eşit karşılaştırma listeleyin.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp 
template<typename Value>  
    bool operator==(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Sol*  
 Karşılaştırılacak sol kapsayıcısı.  
  
 *sağ*  
 Karşılaştırılacak doğru kapsayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevini dizileri denetlediği yalnızca, true değerini döndürür *sol* ve *doğru* aynı uzunluğa sahip ve her konum için `i`, `left[i] ==` `right[i]`. Test etmek için kullandığınız olmadığını *sol* aynı sıralı *doğru* listelerini karşılaştırılan öğe öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_operator_eq.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
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

## <a name="op_gt"></a> İşleç&gt; (liste) (STL/CLR)
Karşılaştırma büyük listeler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename Value>  
    bool operator>(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Sol*  
 Karşılaştırılacak sol kapsayıcısı.  
  
 *sağ*  
 Karşılaştırılacak doğru kapsayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevini döndürür `right` `<` `left`. Test etmek için kullandığınız olmadığını *sol* sonra sıralı *doğru* listelerini karşılaştırılan öğe öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_operator_gt.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
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

## <a name="op_gteq"></a> İşleç&gt;(liste) (STL/CLR) =
Liste büyüktür veya eşittir karşılaştırma.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename Value>  
    bool operator>=(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Sol*  
 Karşılaştırılacak sol kapsayıcısı.  
  
 *sağ*  
 Karşılaştırılacak doğru kapsayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevini döndürür `!(left` `<` `right)`. Test etmek için kullandığınız olmadığını *sol* önce sıralı değil *doğru* listelerini karşılaştırılan öğe öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_list_operator_ge.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
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