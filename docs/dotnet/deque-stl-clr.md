---
title: deque (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque
- cliext::deque::assign
- cliext::deque::at
- cliext::deque::back
- cliext::deque::back_item
- cliext::deque::begin
- cliext::deque::clear
- cliext::deque::const_iterator
- cliext::deque::const_reference
- cliext::deque::const_reverse_iterator
- cliext::deque::deque
- cliext::deque::difference_type
- cliext::deque::empty
- cliext::deque::end
- cliext::deque::erase
- cliext::deque::front
- cliext::deque::front_item
- cliext::deque::generic_container
- cliext::deque::generic_iterator
- cliext::deque::generic_reverse_iterator
- cliext::deque::generic_value
- cliext::deque::insert
- cliext::deque::iterator
- cliext::deque::operator!=
- cliext::deque::operator[]
- cliext::deque::pop_back
- cliext::deque::pop_front
- cliext::deque::push_back
- cliext::deque::push_front
- cliext::deque::rbegin
- cliext::deque::reference
- cliext::deque::rend
- cliext::deque::resize
- cliext::deque::reverse_iterator
- cliext::deque::size
- cliext::deque::size_type
- cliext::deque::swap
- cliext::deque::to_array
- cliext::deque::value_type
- cliext::deque::operator<
- cliext::deque::operator<=
- cliext::deque::operator=
- cliext::deque::operator==
- cliext::deque::operator>
- cliext::deque::operator>=
dev_langs:
- C++
helpviewer_keywords:
- deque class [STL/CLR]
- <deque> header [STL/CLR]
- <cliext/deque> header [STL/CLR]
- assign member [STL/CLR]
- assign member [STL/CLR]
- at member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- begin member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- deque member [STL/CLR]
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
- operator!= member [STL/CLR]
- operator member [] [STL/CLR]
- pop_back member [STL/CLR]
- pop_front member [STL/CLR]
- push_back member [STL/CLR]
- push_front member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- resize member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- value_type member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator= member [STL/CLR]
- operator== member [STL/CLR]
- operator> member [STL/CLR]
- operator>= member [STL/CLR]
ms.assetid: dd669da3-3c0e-45e9-8596-f6b483720941
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ec92f1fcda75c8d632ea2c5a8f66583d960c744a
ms.sourcegitcommit: 301bb19056e5bae84ff50f7d1df1e546efe225ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36305871"
---
# <a name="deque-stlclr"></a>sıradan ayır (STL/CLR)
Şablon sınıfı rastgele erişimi olan öğeleri değişen uzunluk dizisi denetleyen bir nesne tanımlar. Kapsayıcı kullandığınız `deque` bitişik bir blok depolama gibi görünüyor, ancak hangi büyütür veya kalan öğeler kopyalamak için gerek kalmadan her iki uçta küçültür bir dizi öğelerini yönetmek için. Bunu verimli bir şekilde böylece uygulayabileceğiniz bir `double-ended queue`. (Bu nedenle ad.)  
  
 Aşağıda, açıklamada `GValue` aynı `Value` ikinci ref türü olmadıkça olmasından; bu durumda `Value^`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    ref class deque  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IDeque<GValue>  
    { ..... };  
```  
  
### <a name="parameters"></a>Parametreler  
 GValue  
 Denetlenen sıradaki öğenin genel türü.  
  
 Değer  
 Denetlenen sıradaki öğenin türü.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/deque >  
  
 **Namespace:** cliext  

## <a name="members"></a>Üyeler  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|[deque::const_iterator (STL/CLR)](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|  
|[deque::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|  
|[deque::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Denetimli sırası için sabit bir ters yineleyici türü.|  
|[deque::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|  
|[deque::generic_container (STL/CLR)](#generic_container)|Genel arabirim kapsayıcının türü.|  
|[deque::generic_iterator (STL/CLR)](#generic_iterator)|Yineleyici kapsayıcısı için genel arabirimi türü.|  
|[deque::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Kapsayıcı için genel arabirimini ters yineleyici türü.|  
|[deque::generic_value (STL/CLR)](#generic_value)|Kapsayıcı için genel arabirimini öğenin türü.|  
|[deque::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|  
|[deque::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|  
|[deque::reverse_iterator (STL/CLR)](#reverse_iterator)|Denetimli sırası için ters yineleyici türü.|  
|[deque::size_type (STL/CLR)](#size_type)|İki öğe arasındaki işaretli mesafenin türü.|  
|[deque::value_type (STL/CLR)](#value_type)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[deque::assign (STL/CLR)](#assign)|Tüm öğeleri değiştirir.|  
|[deque::at (STL/CLR)](#at)|Belirtilen konumda bir öğe erişir.|  
|[deque::back (STL/CLR)](#back)|Son öğe erişir.|  
|[deque::begin (STL/CLR)](#begin)|Denetlenen dizinin başlangıcını belirtir.|  
|[deque::clear (STL/CLR)](#clear)|Tüm öğeleri kaldırır.|  
|[deque::deque (STL/CLR)](#deque)|Bir kapsayıcı nesnesi oluşturur.|  
|[deque::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|  
|[deque::end (STL/CLR)](#end)|Denetlenen dizinin bitişini belirtir.|  
|[deque::erase (STL/CLR)](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|  
|[deque::front (STL/CLR)](#front)|İlk öğe erişir.|  
|[deque::insert (STL/CLR)](#insert)|Öğeleri belirtilen bir konumda ekler.|  
|[deque::pop_back (STL/CLR)](#pop_back)|Son öğeyi kaldırır.|  
|[deque::pop_front (STL/CLR)](#pop_front)|İlk öğeyi kaldırır.|  
|[deque::push_back (STL/CLR)](#push_back)|Yeni bir son öğesi ekler.|  
|[deque::push_front (STL/CLR)](#push_front)|Yeni bir ilk öğesi ekler.|  
|[deque::rbegin (STL/CLR)](#rbegin)|Ters denetimli dizisi başlangıcını belirtir.|  
|[deque::rend (STL/CLR)](#rend)|Ters denetimli dizinin sonuna belirler.|  
|[deque::resize (STL/CLR)](#resize)|Öğe sayısını değiştirir.|  
|[deque::size (STL/CLR)](#size)|Öğe sayısını sayar.|  
|[deque::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|  
|[deque::to_array (STL/CLR)](#to_array)|Denetimli sırası yeni bir diziye kopyalar.|  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[deque::back_item (STL/CLR)](#back_item)|Son öğe erişir.|  
|[deque::front_item (STL/CLR)](#front_item)|İlk öğe erişir.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[deque::operator!= (STL/CLR)](#op_neq)|İki belirler `deque` nesneler eşit değildir.|  
|[deque::operator(STL/CLR)](#operator)|Belirtilen konumda bir öğe erişir.|  
|[operator< (deque) (STL/CLR)](#op_lt)|Belirler bir `deque` nesnesi, başka değerinden `deque` nesnesi.|  
|[operator<= (deque) (STL/CLR)](#op_lteq)|Belirler bir `deque` nesnesidir değerinden küçük veya eşit başka `deque` nesnesi.|  
|[operator= (deque) (STL/CLR)](#op_as)|Denetimli dizisi yerini alır.|  
|[operator== (deque) (STL/CLR)](#op_eq)|Belirler bir `deque` nesnesidir diğerine eşit `deque` nesnesi.|  
|[operator> (deque) (STL/CLR)](#op_gt)|Belirler bir `deque` nesnesidir diğerinden daha büyük `deque` nesnesi.|  
|[operator>= (deque) (STL/CLR)](#op_gteq)|Belirler bir `deque` nesnesidir büyük veya ona eşit diğerine `deque` nesnesi.|  
  
## <a name="interfaces"></a>Arabirimler  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Yinelenen bir nesne.|  
|<xref:System.Collections.IEnumerable>|Öğeleri dizisi.|  
|<xref:System.Collections.ICollection>|Öğeleri grubunu koruyun.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılan öğeleri dizisi.|  
|<xref:System.Collections.Generic.ICollection%601>|Yazılı öğeleri grubunu koruyun.|  
|<xref:System.Collections.Generic.IList%601>|Yazılı öğeleri sıralı grubunu koruyun.|  
|IDeque < değeri\>|Genel kapsayıcı korur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne ayırır ve saklı dizisi bloklarını tanımladığınız tanıtıcıları denetlediği dizisi için depolama boşaltır `Value` öğeleri. Dizi isteğe bağlı olarak artar. Büyüme eklenmesini ya da yeni bir öğe ekleme maliyetini sabit zamanıdır ve kalan öğe dağıtılmış bir şekilde gerçekleşir. Her iki ucunda bir öğe Ayrıca, sabit zaman ve rahatsız edici kalan öğeleri olmadan da kaldırabilirsiniz. Bu nedenle, bir deque Şablon sınıfı için temel alınan kapsayıcısı için iyi bir aday olduğunu [sıra (STL/CLR)](../dotnet/queue-stl-clr.md) veya Şablon sınıfı [yığın (STL/CLR)](../dotnet/stack-stl-clr.md).  
  
 A `deque` nesnesi ilk (ön) öğesi için sıfırdan sayım doğrudan sayısal konumuna verilen bir öğesine başvurabilir başka bir deyişle, rastgele erişim yineleyiciler destekler [deque::size (STL/CLR)](#size) `() - 1` için son (arka) öğesi. Ayrıca bir deque Şablon sınıfı için temel alınan kapsayıcısı için iyi bir aday olduğu anlamına gelir [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md).  
  
 Deque yineleyici onu atayan öğesi sapması yanı sıra, ilişkili deque nesnesi için bir tanıtıcı depolar. Yalnızca ilişkili kapsayıcı nesneleri ile yineleyiciler kullanabilirsiniz. Deque öğesinin sapması ise `not` mutlaka aynı konumu. Eklenen ilk öğe sapması sıfır, sapması 1 sonraki eklenmiş öğeye sahip, ancak sonraki prepended öğesi sapması -1 içeriyor.  
  
 Ekleme veya her iki uçta öğeleri silme `not` geçerli tüm sapması depolanan bir öğenin değerini alter. Ekleme veya bir iç öğesi, ancak silmeyi `can` yineleyici tarafından atanan değer de değiştirebilmeniz için belirli bir sapması depolanan öğesi değeri değiştirin. (Kapsayıcı delik INSERT önce oluşturmak veya bir silme sonra delik doldurmak için aşağı veya yukarı öğeleri kopyalamak gerekebilir.) Bununla birlikte, geçerli bir öğesi kendi sapmaya atayan sürece deque yineleyici geçerli kalır. Ayrıca, geçerli bir yineleyici dereferencable kalır--erişmek veya kendi sapmaya tarafından döndürülen yineleyici sapması eşit değil sürece bunu atayan--öğe değerini değiştirmek için kullanmak `end()`.  
  
 Silme veya bir öğe kaldırıldığında yıkıcı depolanan değeri için çağırır. Kapsayıcı yok etme tüm öğeleri siler. Bu nedenle, hiçbir öğe kapsayıcı outlive ref sınıfı öğe türü olan bir kapsayıcı sağlar. Ancak, bir kapsayıcı, tanıtıcısı algılamadığı unutmayın `not` öğeleri yok.  
 
## <a name="member-definitions"></a>Üye tanımları

## <a name="assign"></a> deque::Assign (STL/CLR)
Tüm öğeleri değiştirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `count`  
 Eklenecek öğe sayısı.  
  
 `first`  
 Eklenecek Aralık başlangıcı.  
  
 `last`  
 Eklenecek aralık sonu.  
  
 `right`  
 Eklenecek numaralandırması.  
  
 `val`  
 Eklenecek öğenin değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi denetimli dizisi ile yinelenmesinin değiştirir `count` değerinin öğeleri `val`. Kapsayıcı öğeler ile doldurmak için tüm aynı değere sahip kullanırsınız.  
  
 Varsa `InIt` bir tamsayı türünde ikinci üye işlevi aynı şekilde davranır `assign((size_type)first, (value_type)last)`. Aksi takdirde, denetlenen dizisi dizisiyle yerini [`first`, `last`). Denetimli bir kopyasını sıra yapmak için başka bir sıra kullanırsınız.  
  
 Numaralandırıcı tarafından belirtilen sıra ile denetlenen dizisi üçüncü üye işlevi değiştirir `right`. Denetimli sırası bir numaralandırıcı tarafından tanımlanan bir dizi bir kopya yapmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_assign.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::deque<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    c2.assign(c1.begin(), c1.end() - 1);   
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

## <a name="at"></a> deque::AT (STL/CLR)
Belirtilen konumda bir öğe erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
reference at(size_type pos);  
```  
  
#### <a name="parameters"></a>Parametreler  
 POS  
 Erişim öğesinin konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi konumunda denetimli dizisi öğesine bir başvuru döndürür `pos`. Okumak veya bir öğe, konumu yazmak için kullandığınız biliyor.  
  
### <a name="example"></a>Örnek  
  
```cpp
// cliext_deque_at.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using at   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1.at(1) = L'x';   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a x c  
```  
  
## <a name="back"></a> deque::Back (STL/CLR)
Son öğe erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
reference back();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini son öğe boş olmalıdır denetimli dizisi için bir başvuru döndürür. Mevcut bildiğinizde son öğesine erişmek için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_back.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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
  
## <a name="back_item"></a> deque::back_item (STL/CLR)
Son öğe erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
property value_type back_item;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliği, son öğe boş olmalıdır denetimli dizisi erişir. Okumak veya mevcut bildiğinizde son öğe yazmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_back_item.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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
  
## <a name="begin"></a> deque::Begin (STL/CLR)
Denetlenen dizinin başlangıcını belirtir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
iterator begin();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi ilk öğe denetimli dizisi ya da yalnızca boş bir dizi ötesinde atar rasgele erişim yineleyici döndürür. Atayan bir yineleyici almak için kullandığınız `current` denetimli dizisi ancak durumunu başında denetimli sırası uzunluğu değişirse değiştirebilirsiniz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_begin.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::deque<wchar_t>::iterator it = c1.begin();   
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

## <a name="clear"></a> deque::Clear (STL/CLR)
Tüm öğeleri kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void clear();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini etkili bir şekilde çağırır [deque::erase (STL/CLR)](#erase) `(` [deque::begin (STL/CLR)](#begin) `(),` [deque::end (STL/CLR)](#end) `())`. Denetimli sırası boş olduğundan emin olmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_clear.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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

## <a name="const_iterator"></a> deque::const_iterator (STL/CLR)
Denetlenen dizi için bir sabit yineleyici türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef T2 const_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilmeyen türünde bir nesne türünü açıklayan `T2` hizmet eden bir sabit rasgele erişim yineleyici denetlenen dizisi olarak.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_const_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::deque<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" {0}", *cit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="const_reference"></a> deque::const_reference (STL/CLR)
Bir öğe için sabit bir başvuru türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef value_type% const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğe için sabit bir başvuru türü açıklanmaktadır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_const_reference.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::deque<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        {   // get a const reference to an element   
        cliext::deque<wchar_t>::const_reference cref = *cit;   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="const_reverse_iterator"></a> deque::const_reverse_iterator (STL/CLR)
Denetimli sırası için sabit bir ters yineleyici türü...  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilmeyen türünde bir nesne türünü açıklayan `T4` hizmet eden sabit bir ters yineleyici denetlenen dizisi olarak.  
  
### <a name="example"></a>Örnek  
  
```cpp 
// cliext_deque_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::deque<wchar_t>::const_reverse_iterator crit = c1.rbegin();   
    cliext::deque<wchar_t>::const_reverse_iterator crend = c1.rend();   
    for (; crit != crend; ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  

## <a name="deque"></a> deque::deque (STL/CLR)
Bir kapsayıcı nesnesi oluşturur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
deque();  
deque(deque<Value>% right);  
deque(deque<Value>^ right);  
explicit deque(size_type count);  
deque(size_type count, value_type val);  
template<typename InIt>  
    deque(InIt first, InIt last);  
deque(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `count`  
 Eklenecek öğe sayısı.  
  
 `first`  
 Eklenecek Aralık başlangıcı.  
  
 `last`  
 Eklenecek aralık sonu.  
  
 `right`  
 Nesne veya eklemek için aralık.  
  
 `val`  
 Eklenecek öğenin değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucusu:  
  
 `deque();`  
  
 denetimli sıralı öğe ile başlatır. Boş bir başlangıç denetimli dizisini belirtmek için kullanın.  
  
 Oluşturucusu:  
  
 `deque(deque<Value>% right);`  
  
 denetimli dizisi dizisiyle başlatır [`right.begin()`, `right.end()`). Deque nesne tarafından denetlenen sırasının bir kopyasını bir ilk denetlenen sırası belirtmek için kullandığınız `right`. Yineleyiciler hakkında daha fazla bilgi için bkz: [deque::begin (STL/CLR)](#begin) ve [deque::end (STL/CLR)](#end).  
  
 Oluşturucusu:  
  
 `deque(deque<Value>^ right);`  
  
 denetimli dizisi dizisiyle başlatır [`right->begin()`, `right->end()`). Bir kopyasını, tanıtıcısı deque nesnesi tarafından denetlenen sırası olan ilk denetimli bir sıra belirtmek için kullandığınız `right`.  
  
 Oluşturucusu:  
  
 `explicit deque(size_type count);`  
  
 denetimli dizisiyle başlatır `count` öğeleriyle her değer `value_type()`. Kapsayıcı öğeler ile doldurmak için varsayılan değer tüm sahip kullanırsınız.  
  
 Oluşturucusu:  
  
 `deque(size_type count, value_type val);`  
  
 denetimli dizisiyle başlatır `count` öğeleriyle her değer `val`. Kapsayıcı öğeler ile doldurmak için tüm aynı değere sahip kullanırsınız.  
  
 Oluşturucusu:  
  
 `template<typename InIt>`  
  
 `deque(InIt first, InIt last);`  
  
 denetimli dizisi dizisiyle başlatır [`first`, `last`). Denetimli sırası başka bir dizi bir kopya yapmak için kullanın.  
  
 Oluşturucusu:  
  
 `deque(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 Numaralandırıcı tarafından belirtilen sıra ile denetlenen dizisi başlatır `right`. Denetimli sırası bir numaralandırıcı tarafından açıklanan başka bir dizi bir kopya yapmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_construct.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container   
    cliext::deque<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::deque<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::deque<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::deque<wchar_t>::iterator it = c3.end();   
    cliext::deque<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::deque<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::deque<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::deque<wchar_t> c8(%c3);   
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

## <a name="difference_type"></a> deque::difference_type (STL/CLR)
İki öğe arasındaki imzalı uzaklığı türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Türünü imzalı öğe sayısını tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp 
// cliext_deque_difference_type.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::deque<wchar_t>::difference_type diff = 0;   
    for (cliext::deque<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it) ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
  
// compute negative difference   
    diff = 0;   
    for (cliext::deque<wchar_t>::iterator it = c1.end();   
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
  
## <a name="empty"></a> deque::Empty (STL/CLR)
Bir öğe olup olmadığını sınar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool empty();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi boş denetimli dizisi için true değerini döndürür. Eşdeğer olan [deque::size (STL/CLR)](#size)`() == 0`. Deque boş olup olmadığını sınamak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_empty.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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

## <a name="end"></a> deque::End (STL/CLR)
Denetlenen dizinin bitişini belirtir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
iterator end();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi yalnızca denetimli dizisi ötesinde işaret rasgele erişim yineleyici döndürür. Atayan bir yineleyici almak için kullandığınız `current` denetimli dizisi ancak durumunu sonuna denetimli sırası uzunluğu değişirse değiştirebilirsiniz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_end.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    cliext::deque<wchar_t>::iterator it = c1.end();   
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

## <a name="erase"></a> deque::ERASE (STL/CLR)
Belirtilen konumlardaki öğeleri kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `first`  
 Silme aralığını başlangıcı.  
  
 `last`  
 Silinecek aralığı sonu.  
  
 `where`  
 Silinecek öğe.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi gösterdiği denetimli sırasının öğeyi kaldırır `where`. Tek bir öğe kaldırmak için kullanın.  
  
 İkinci üye işlevi denetlenen sıradaki aralığında kaldırır [`first`, `last`). Sıfır veya daha fazla bitişik öğeleri kaldırmak için kullanın.  
  
 Her iki üye işlevleri kaldırıldı, herhangi bir öğenin dışında kalan ilk öğe atayan bir yineleyici dönün veya [deque::end (STL/CLR)](#end) `()` böyle bir öğe varsa.  
  
 Öğeleri silme, öğesi kopyaları kuvvetini sonuna bitişinde yakın arasındaki öğelerin sayısı doğrusal sayısıdır. (Bir veya daha fazla öğe sırası her iki ucundaki silme hiçbir öğe kopya oluşur.)  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_erase.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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
    cliext::deque<wchar_t>::iterator it = c1.end();   
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

## <a name="front"></a> deque::Front (STL/CLR)
İlk öğe erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
reference front();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi boş olması gerekir denetlenen dizisinin ilk öğesi için bir başvuru döndürür. Okumak veya mevcut bildiğinizde ilk öğe yazmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_front.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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

## <a name="front_item"></a> deque::front_item (STL/CLR)
İlk öğe erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
property value_type front_item;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliği boş olması gerekir denetlenen dizisinin ilk öğesi erişir. Okumak veya mevcut bildiğinizde ilk öğe yazmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_front_item.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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

## <a name="generic_container"></a> deque::generic_container (STL/CLR)
Genel arabirim kapsayıcının türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef Microsoft::VisualC::StlClr::  
    IDeque<generic_value>  
    generic_container;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu şablon kapsayıcı sınıfı için genel arabirimi türünü tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_generic_container.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;   
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

## <a name="generic_iterator"></a> deque::generic_iterator (STL/CLR)
Yineleyici kullanmak için genel arabirimi kapsayıcının türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ContainerRandomAccessIterator<generic_value> generic_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Genel arabirim ile bu şablon kapsayıcı sınıfı için kullanılabilen genel bir yineleyici türünü tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_generic_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::deque<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::deque<wchar_t>::generic_value gcval = *gcit;   
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

## <a name="generic_reverse_iterator"></a> deque::generic_reverse_iterator (STL/CLR)
Kullanmak için ters yineleyici kapsayıcısı için genel arabirimi türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ReverseRandomAccessIterator<generic_value> generic_reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Genel arabirim ile bu şablon kapsayıcı sınıfı için kullanılabilen genel bir ters yineleyici türünü tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_generic_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::deque<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();   
    cliext::deque<wchar_t>::generic_value gcval = *gcit;   
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

## <a name="generic_value"></a> deque::generic_value (STL/CLR)
Kapsayıcı için genel arabirimi ile kullanmak için öğenin türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef GValue generic_value;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Türünde bir nesne türünü açıklayan `GValue` kullanmak için saklı öğesi değeri bu şablonu kapsayıcı sınıfı için genel arabirimi açıklar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_generic_value.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::deque<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::deque<wchar_t>::generic_value gcval = *gcit;   
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

## <a name="insert"></a> deque::insert (STL/CLR)
Öğeleri belirtilen bir konumda ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `count`  
 Eklenecek öğe sayısı.  
  
 `first`  
 Eklenecek Aralık başlangıcı.  
  
 `last`  
 Eklenecek aralık sonu.  
  
 `right`  
 Eklenecek numaralandırması.  
  
 `val`  
 Eklenecek öğenin değeri.  
  
 `where`  
 Önce eklemek için kapsayıcı WHERE.  
  
### <a name="remarks"></a>Açıklamalar  
 Her üyesinin gösterdiği öğesinden önce ekler işlevleri `where` denetimli sırayla bir dizi belirtilen tarafından kalan işlenen.  
  
 İlk üye işlevi değeri olan bir öğe ekler `val` ve yeni eklenen öğesi atayan bir yineleyici döndürür. Yineleyici tarafından atanan bir yerde önce tek bir öğe eklemek için kullanın.  
  
 İkinci üye işlevi bir yinelenmesinin ekler `count` değerinin öğeleri `val`. Tüm kopyalarını aynı değeri olan sıfır veya daha fazla bitişik öğe eklemek için kullanın.  
  
 Varsa `InIt` bir tamsayı türü üçüncü üye işlevi aynı şekilde davranır `insert(where, (size_type)first, (value_type)last)`. Aksi takdirde dizisi ekler [`first`, `last`). Başka bir sırasından kopyalanan sıfır veya daha fazla bitişik öğe eklemek için kullanın.  
  
 Dördüncü üye fonksiyonu tarafından belirlenen dizisi ekler `right`. Bir numaralandırıcı tarafından tanımlanan bir dizi eklemek için kullanın.  
  
 Tek bir öğe ekleme yaparken öğesi kopya ekleme noktasını bitişinde yakın arasındaki öğelerin sayısı doğrusal sayısıdır. (Bir veya daha fazla öğe sırası ya da sonunda eklerken, hiçbir öğe kopya gerçekleşir.) Varsa `InIt` giriş yineleyici olan üçüncü üye işlevi dizideki her öğe için tek bir ekleme etkili bir şekilde gerçekleştirir. Aksi takdirde eklerken `N` öğeleri öğesi kopya sayısı doğrusal olarak `N` ekleme noktasını bitişinde yakın arasındaki öğelerin sayısı artı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_insert.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using iterator   
    cliext::deque<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::deque<wchar_t> c2;   
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

## <a name="iterator"></a> deque::iterator (STL/CLR)
Denetlenen dizi için bir yineleyici türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef T1 iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilmeyen türünde bir nesne türünü açıklayan `T1` hizmet eden denetimli sırası için rasgele erişim yineleyici olarak.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::deque<wchar_t>::iterator it = c1.begin();   
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

## <a name="op_neq"></a> deque::operator! = (STL/CLR)
Deque eşit değildir karşılaştırma.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    bool operator!=(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `left`  
 Karşılaştırılacak sol kapsayıcı.  
  
 `right`  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `!(left == right)`. Test etmek için kullandığınız olup olmadığını `left` aynı sıralı değil `right` iki deques öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_operator_ne.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
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

## <a name="operator"></a> deque::operator(stl/CLR)
Belirtilen konumda bir öğe erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
reference operator[](size_type pos);  
```  
  
#### <a name="parameters"></a>Parametreler  
 POS  
 Erişim öğesinin konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci konumunda öğesine bir referene döndürür `pos`. Konum bildiğiniz bir öğe erişmek için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_operator_sub.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using subscripting   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
  
// change an entry and redisplay   
    c1[1] = L'x';   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1[i]);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a x c  
```  

## <a name="pop_back"></a> deque::pop_back (STL/CLR)
Son öğeyi kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void pop_back();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi boş olmalıdır denetimli dizisi son öğeyi kaldırır. Deque arkadaki bir öğe tarafından kısaltmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_pop_back.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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

## <a name="pop_front"></a> deque::pop_front (STL/CLR)
İlk öğeyi kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void pop_front();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi boş olması gerekir denetlenen dizisinin ilk öğesi kaldırır. Deque ön bir öğe tarafından kısaltmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_pop_front.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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
  
## <a name="push_back"></a> deque::push_back (STL/CLR)
Yeni bir son öğesi ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void push_back(value_type val);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini değeri olan bir öğe ekler `val` denetimli dizisi sonunda. Deque için başka bir öğe eklemek için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_push_back.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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

## <a name="push_front"></a> deque::push_front (STL/CLR)
Yeni bir ilk öğesi ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void push_front(value_type val);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini değeri olan bir öğe ekler `val` denetimli dizisi başındaki. Deque için başka bir öğe başına kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_push_front.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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

## <a name="rbegin"></a> deque::rbegin (STL/CLR)
Ters denetimli dizisi başlangıcını belirtir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
reverse_iterator rbegin();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli dizisi ya da boş bir dizi başına ötesinde yalnızca son öğesi atar ters bir yineleyici döndürür. Bu nedenle, atar `beginning` ters dizisi. Atayan bir yineleyici almak için kullandığınız `current` ters sırada görülen denetimli dizisi ancak durumunu başında denetimli sırası uzunluğu değişirse değiştirebilirsiniz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_rbegin.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    cliext::deque<wchar_t>::reverse_iterator rit = c1.rbegin();   
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

## <a name="reference"></a> deque::Reference (STL/CLR)
Bir öğe için bir başvuru türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğe için bir başvuru türü açıklanmaktadır.  
  
### <a name="example"></a>Örnek  
  
```cpp 
// cliext_deque_reference.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::deque<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::deque<wchar_t>::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
  
// modify contents " a b c"   
    for (it = c1.begin(); it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::deque<wchar_t>::reference ref = *it;   
  
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

## <a name="rend"></a> deque::rend (STL/CLR)
Ters denetimli dizinin sonuna belirler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
reverse_iterator rend();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini ters yineleyici başına yalnızca ötesinde işaret denetimli dizisi döndürür. Bu nedenle, atar `end` ters dizisi. Atayan bir yineleyici almak için kullandığınız `current` ters sırada görülen denetimli dizisi ancak durumunu sonuna denetimli sırası uzunluğu değişirse değiştirebilirsiniz.  
  
### <a name="example"></a>Örnek  
  
```cpp 
// cliext_deque_rend.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::deque<wchar_t>::reverse_iterator rit = c1.rend();   
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

## <a name="resize"></a> deque::resize (STL/CLR)
Öğe sayısını değiştirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### <a name="parameters"></a>Parametreler  
 new_size  
 Denetimli sırası yeni büyüklüğü.  
  
 VAL  
 Doldurma öğesinin değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Her iki üye işlevleri emin [deque::size (STL/CLR)](#size) `()` henceforth döndürür `new_size`. Uzun denetimli dizisi yapmanız gerekiyorsa, ilk üye işlevi değer ile öğeleri ekler `value_type()`değere sahip öğeleri ikinci üye işlevi ekler yaparken `val`. Daha kısa denetimli sıra yapmak için her iki üye işlevleri etkili bir şekilde son öğe silme [deque::size (STL/CLR)](#size) `() -` `new_size` kez. Denetimli sırası boyutu olduğundan emin olmak için kullandığınız `new_size`, kırpma ya da geçerli denetimli dizisi doldurma tarafından.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_resize.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::deque<wchar_t> c1;   
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

## <a name="reverse_iterator"></a> deque::reverse_iterator (STL/CLR)
Denetimli sırası için ters yineleyici türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef T3 reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilmeyen türünde bir nesne türünü açıklayan `T3` hizmet eden bir ters yineleyici denetimli sırası için farklı.  
  
### <a name="example"></a>Örnek  
  
```cpp 
// cliext_deque_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::deque<wchar_t>::reverse_iterator rit = c1.rbegin();   
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
 
## <a name="size"></a> deque::size (STL/CLR)
Öğe sayısını sayar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
size_type size();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sırası uzunluğunu döndürür. Şu anda denetlenen sıradaki öğelerinin sayısını belirlemek için kullanın. Tüm önem verdiğiniz ise dizisi bkz sıfır olmayan boyutu olup [deque::empty (STL/CLR)](#empty)`()`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_size.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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

## <a name="size_type"></a> deque::size_type (STL/CLR)
İki öğe arasındaki imzalı uzaklığı türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Türünü negatif olmayan öğe sayısını tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_size_type.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::deque<wchar_t>::size_type diff = c1.end() - c1.begin();   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
```  

## <a name="swap"></a> deque::Swap (STL/CLR)
İki kapsayıcının içeriğinin yerini değiştirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void swap(deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 sağ  
 İçeriği ile değiştirilecek kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sıraları arasında değiştirir `*this` ve `right`. Bunu Sabit sürede yapar ve hiçbir özel durum oluşturur. Bunu iki kapsayıcı içeriğini exchange hızlı bir şekilde kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_swap.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::deque<wchar_t> c2(5, L'x');   
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

## <a name="to_array"></a> deque::to_array (STL/CLR)
Denetimli sırası yeni bir diziye kopyalar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
cli::array<Value>^ to_array();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi denetimli sırası içeren bir dizi döndürür. Dizi formunda denetimli sırasının bir kopyasını almak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_to_array.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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
  
## <a name="value_type"></a> deque::value_type (STL/CLR)
Öğenin türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef Value value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Value`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_value_type.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using value_type   
    for (cliext::deque<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   // store element in value_type object   
        cliext::deque<wchar_t>::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="op_lt"></a> İşleç&lt; (deque) (STL/CLR)
Deque karşılaştırma küçüktür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    bool operator<(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleci işlevi döndürür true ise, en düşük konumunun `i` kendisi için `!(right[i] < left[i])` Ayrıca, true olan `left[i] < right[i]`. Aksi takdirde, döndürür `left->size() < right->size()` test etmek için kullandığınız olup olmadığını `left` önce sıralı `right` iki deques öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_operator_lt.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
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

## <a name="op_lteq"></a> İşleç&lt;= (deque) (STL/CLR)
Deque daha az veya bu değere eşit karşılaştırma.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    bool operator<=(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `!(right < left)`. Test etmek için kullandığınız olup olmadığını `left` sonra sıralı değil `right` iki deques öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_operator_le.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
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

## <a name="op_as"></a> işleç = (deque) (STL/CLR)
Denetimli dizisi yerini alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
deque<Value>% operator=(deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 sağ  
 Kopyalamak için kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci kopyaları `right` nesnesine sonra döndürür `*this`. Denetimli sırayla kopyası ile denetlenen sırasını değiştirmek için kullanın `right`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_operator_as.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
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
  
## <a name="op_eq"></a> operator == (deque) (STL/CLR)
Deque eşit karşılaştırması.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    bool operator==(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi sıraları denetlediği yalnızca, true değerini döndürür `left` ve `right` aynı uzunlukta olması ve her konum için `i`, `left[i] ==` `right[i]`. Test etmek için kullandığınız olup olmadığını `left` aynı sıralı `right` iki deques öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_operator_eq.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
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

## <a name="op_gt"></a> İşleç&gt; (deque) (STL/CLR)
Deque karşılaştırma büyük.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    bool operator>(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `right` `<` `left`. Test etmek için kullandığınız olup olmadığını `left` sonra sıralanmış `right` iki deques öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_operator_gt.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
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

## <a name="op_gteq"></a> İşleç&gt;= (deque) (STL/CLR)
Deque büyük veya ona eşit karşılaştırması.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    bool operator>=(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `!(left` `<` `right)`. Test etmek için kullandığınız olup olmadığını `left` önce sıralı değil `right` iki deques öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_deque_operator_ge.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
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
 