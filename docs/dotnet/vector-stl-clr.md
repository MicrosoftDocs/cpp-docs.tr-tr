---
title: vektör (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector
- cliext::operator!=
- cliext::operator<
- cliext::operator<=
- cliext::operator==
- cliext::operator>
- cliext::operator>=
- cliext::vector::assign
- cliext::vector::at
- cliext::vector::back
- cliext::vector::back_item
- cliext::vector::begin
- cliext::vector::capacity
- cliext::vector::clear
- cliext::vector::const_iterator
- cliext::vector::const_reference
- cliext::vector::const_reverse_iterator
- cliext::vector::difference_type
- cliext::vector::empty
- cliext::vector::end
- cliext::vector::erase
- cliext::vector::front
- cliext::vector::front_item
- cliext::vector::generic_container
- cliext::vector::generic_iterator
- cliext::vector::generic_reverse_iterator
- cliext::vector::generic_value
- cliext::vector::insert
- cliext::vector::iterator
- cliext::vector::operator=
- cliext::vector::operator
- cliext::vector::pop_back
- cliext::vector::push_back
- cliext::vector::rbegin
- cliext::vector::reference
- cliext::vector::rend
- cliext::vector::reserve
- cliext::vector::resize
- cliext::vector::reverse_iterator
- cliext::vector::size
- cliext::vector::size_type
- cliext::vector::swap
- cliext::vector::to_array
- cliext::vector::value_type
- cliext::vector::vector
dev_langs:
- C++
helpviewer_keywords:
- vector class [STL/CLR]
- <cliext/vector> header [STL/CLR]
- <vector> header [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> (vector) member [STL/CLR]
- operator>= member [STL/CLR]
- assign member [STL/CLR]
- at member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- begin member [STL/CLR]
- capacity member [STL/CLR]
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
- operator= member [STL/CLR]
- operator member [STL/CLR]
- pop_back member [STL/CLR]
- push_back member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- reserve member [STL/CLR]
- resize member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- value_type member [STL/CLR]
- vector member [STL/CLR]
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5d5b3e94b0b594174538aebe6542b04df7214f1b
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079818"
---
# <a name="vector-stlclr"></a>vektör (STL/CLR)
Şablon sınıfı rastgele erişimi olan öğeleri değişen uzunluk dizisi denetleyen bir nesne tanımlar. Kapsayıcı kullandığınız `vector` öğeleri dizisi bitişik bir blok depolama olarak yönetmek için. Blok büyür isteğe bağlı olarak bir dizi olarak uygulanır.  
  
 Aşağıda, açıklamada `GValue` aynı `Value` ikinci ref türü olmadıkça olmasından; bu durumda `Value^`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    ref class vector  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IVector<GValue>  
    { ..... };  
```  
  
### <a name="parameters"></a>Parametreler  
 Değer  
 Denetlenen sıradaki öğenin türü.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/vektör >  
  
 **Namespace:** cliext  

## <a name="declarations"></a>Bildirimler  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|[vector::const_iterator (STL/CLR)](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|  
|[vector::const_reference (STL/CLR)](#const_reference)|Bir öğe için sabit bir başvuru türü.|  
|[vector::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|Denetimli sırası için sabit bir ters yineleyici türü.|  
|[vector::difference_type (STL/CLR)](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|  
|[vector::generic_container (STL/CLR)](#generic_container)|Genel arabirim kapsayıcının türü.|  
|[vector::generic_iterator (STL/CLR)](#generic_iterator)|Yineleyici kapsayıcısı için genel arabirimi türü.|  
|[vector::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|Kapsayıcı için genel arabirimini ters yineleyici türü.|  
|[vector::generic_value (STL/CLR)](#generic_value)|Kapsayıcı için genel arabirimini öğenin türü.|  
|[vector::iterator (STL/CLR)](#iterator)|Denetlenen dizi için bir yineleyici türü.|  
|[vector::reference (STL/CLR)](#reference)|Bir öğe için bir başvuru türü.|  
|[vector::reverse_iterator (STL/CLR)](#reverse_iterator)|Denetimli sırası için ters yineleyici türü.|  
|[vector::size_type (STL/CLR)](#size_type)|İki öğe arasındaki işaretli mesafenin türü.|  
|[vector::value_type (STL/CLR)](#value_type)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[vector::assign (STL/CLR)](#assign)|Tüm öğeleri değiştirir.|  
|[vector::at (STL/CLR)](#at)|Belirtilen konumda bir öğe erişir.|  
|[vector::back (STL/CLR)](#back)|Son öğe erişir.|  
|[vector::begin (STL/CLR)](#begin)|Denetlenen dizinin başlangıcını belirtir.|  
|[vector::capacity (STL/CLR)](#capacity)|Kapsayıcı için ayrılan depolama alanı boyutunu raporlar.|  
|[vector::clear (STL/CLR)](#clear)|Tüm öğeleri kaldırır.|  
|[vector::empty (STL/CLR)](#empty)|Bir öğe olup olmadığını sınar.|  
|[vector::end (STL/CLR)](#end)|Denetlenen dizinin bitişini belirtir.|  
|[vector::erase (STL/CLR)](#erase)|Belirtilen konumlardaki öğeleri kaldırır.|  
|[vector::front (STL/CLR)](#front)|İlk öğe erişir.|  
|[vector::insert (STL/CLR)](#insert)|Öğeleri belirtilen bir konumda ekler.|  
|[vector::pop_back (STL/CLR)](#pop_back)|Son öğeyi kaldırır.|  
|[vector::push_back (STL/CLR)](#push_back)|Yeni bir son öğesi ekler.|  
|[vector::rbegin (STL/CLR)](#rbegin)|Ters denetimli dizisi başlangıcını belirtir.|  
|[vector::rend (STL/CLR)](#rend)|Ters denetimli dizinin sonuna belirler.|  
|[vector::reserve (STL/CLR)](#reserve)|Kapsayıcı için en düşük büyüme kapasitesi sağlar.|  
|[vector::resize (STL/CLR)](#resize)|Öğe sayısını değiştirir.|  
|[vector::size (STL/CLR)](#size)|Öğe sayısını sayar.|  
|[vector::swap (STL/CLR)](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|  
|[vector::to_array (STL/CLR)](#to_array)|Denetimli sırası yeni bir diziye kopyalar.|  
|[vector::vector (STL/CLR)](#vector)|Bir kapsayıcı nesnesi oluşturur.|  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[vector::back_item (STL/CLR)](#back_item)|Son öğe erişir.|  
|[vector::front_item (STL/CLR)](#front_item)|İlk öğe erişir.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[vector::operator= (STL/CLR)](#op_as)|Denetimli dizisi yerini alır.|  
|[vector::operator(STL/CLR)](#op)|Belirtilen konumda bir öğe erişir.|  
|[operator!= (vector) (STL/CLR)](#op_neq)|Belirler bir `vector` nesne diğerine eşit değil `vector` nesnesi.|  
|[operator< (vector) (STL/CLR)](#op_lt)|Belirler bir `vector` nesnesi, başka değerinden `vector` nesnesi.|  
|[operator<= (vector) (STL/CLR)](#op_lteq)|Belirler bir `vector` nesnesidir değerinden küçük veya eşit başka `vector` nesnesi.|  
|[operator== (vector) (STL/CLR)](#op_eq)|Belirler bir `vector` nesnesidir diğerine eşit `vector` nesnesi.|  
|[operator> (vector) (STL/CLR)](#op_gt)|Belirler bir `vector` nesnesidir diğerinden daha büyük `vector` nesnesi.|  
|[operator>= (vector) (STL/CLR)](#op_gteq)|Belirler bir `vector` nesnesidir büyük veya ona eşit diğerine `vector` nesnesi.|  
  
## <a name="interfaces"></a>Arabirimler  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Yinelenen bir nesne.|  
|<xref:System.Collections.IEnumerable>|Öğeleri dizisi.|  
|<xref:System.Collections.ICollection>|Öğeleri grubunu koruyun.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılan öğeleri dizisi.|  
|<xref:System.Collections.Generic.ICollection%601>|Yazılı öğeleri grubunu koruyun.|  
|<xref:System.Collections.Generic.IList%601>|Yazılı öğeleri sıralı grubunu koruyun.|  
|IVector < değeri\>|Genel kapsayıcı korur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne ayırır ve depolanan bir dizi denetlediği dizisi için depolama boşaltır `Value` isteğe bağlı olarak büyür öğeleri. Büyüme yeni bir öğe ekleme maliyetini amortized sabit zaman olduğunu şekilde gerçekleşir. Diğer bir deyişle, sonunda öğe eklemek maliyeti, ortalama olarak büyük denetimli dizisi alır uzunluğu olarak artırmaz. Bu nedenle, bir vektör Şablon sınıfı için temel alınan kapsayıcısı için iyi bir aday olduğunu [yığın (STL/CLR)](../dotnet/stack-stl-clr.md).  
  
 A `vector` ilk (ön) öğesinin sıfırdan sayım doğrudan sayısal konumuna verilen bir öğesine başvurabilir anlamına gelir destekler rasgele erişim yineleyiciler `size() - 1` son (arka) öğesi için. Ayrıca bir vektör Şablon sınıfı için temel alınan kapsayıcısı için iyi bir aday olduğu anlamına gelir [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md).  
  
 Vektör yineleyici onu atayan öğesi sapması yanı sıra, ilişkili vektör nesnesi için bir tanıtıcı depolar. Yalnızca ilişkili kapsayıcı nesneleri ile yineleyiciler kullanabilirsiniz. Vector öğesinin sapması konumuna ile aynıdır.  
  
 Ekleme veya öğeleri silme yineleyici tarafından atanan değer de değiştirebilmeniz için belirli bir konumda depolanan öğe değeri değiştirebilirsiniz. (Kapsayıcı delik INSERT önce oluşturmak veya bir silme sonra delik doldurmak için aşağı veya yukarı öğeleri kopyalamak gerekebilir.) Bununla birlikte, kendi sapmaya aralığında olduğu sürece vektör yineleyici geçerli kaldığı `[0, size()]`. Ayrıca, geçerli bir yineleyici dereferencable kalır--erişmek veya kendi sapmaya eşit değil sürece bunu atayan--öğe değerini değiştirmek için kullanmak `size()`.  
  
 Silme veya bir öğe kaldırıldığında yıkıcı depolanan değeri için çağırır. Kapsayıcı yok etme tüm öğeleri siler. Bu nedenle, hiçbir öğe kapsayıcı outlive ref sınıfı öğe türü olan bir kapsayıcı sağlar. Ancak, bir kapsayıcı, tanıtıcısı öğeleri silmiyor unutmayın.  
  
## <a name="members"></a>Üyeler

## <a name="assign"></a> Vector::Assign (STL/CLR)
Tüm öğeleri değiştirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 count  
 Eklenecek öğe sayısı.  
  
 ilk  
 Eklenecek Aralık başlangıcı.  
  
 Son  
 Eklenecek aralık sonu.  
  
 sağ  
 Eklenecek numaralandırması.  
  
 VAL  
 Eklenecek öğenin değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi denetimli dizisi ile yinelenmesinin değiştirir `count` değerinin öğeleri `val`. Kapsayıcı öğeler ile doldurmak için tüm aynı değere sahip kullanırsınız.  
  
 Varsa `InIt` bir tamsayı türünde ikinci üye işlevi aynı şekilde davranır `assign((size_type)first, (value_type)last)`. Aksi takdirde, denetlenen dizisi dizisiyle yerini [`first`, `last`). Denetimli bir kopyasını sıra yapmak için başka bir sıra kullanırsınız.  
  
 Numaralandırıcı tarafından belirtilen sıra ile denetlenen dizisi üçüncü üye işlevi değiştirir `right`. Denetimli sırası bir numaralandırıcı tarafından tanımlanan bir dizi bir kopya yapmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_assign.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::vector<wchar_t> c2;   
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

## <a name="at"></a> Vector::AT (STL/CLR)
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
// cliext_vector_at.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
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

## <a name="back"></a> Vector::Back (STL/CLR)
Son öğe erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
reference back();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini son öğe boş olmalıdır denetimli dizisi için bir başvuru döndürür. Mevcut bildiğinizde son öğesine erişmek için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_back.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
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

## <a name="back_item"></a> Vector::back_item (STL/CLR)
Son öğe erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
property value_type back_item;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliği, son öğe boş olmalıdır denetimli dizisi erişir. Okumak veya mevcut bildiğinizde son öğe yazmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_back_item.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
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

## <a name="begin"></a> Vector::Begin (STL/CLR)
Denetlenen dizinin başlangıcını belirtir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
iterator begin();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi ilk öğe denetimli dizisi ya da yalnızca boş bir dizi ötesinde atar rasgele erişim yineleyici döndürür. Atayan bir yineleyici almak için kullandığınız `current` denetimli dizisi ancak durumunu başında denetimli sırası uzunluğu değişirse değiştirebilirsiniz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_begin.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::vector<wchar_t>::iterator it = c1.begin();   
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

## <a name="capacity"></a> Vector::Capacity (STL/CLR)
Kapsayıcı için ayrılan depolama alanı boyutunu raporlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
size_type capacity();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi şu anda denetlenen sırası, en az kadar büyük bir değer tutmak için ayrılan depolama alanı döndürür [vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)`()`. Denetimli dizisi için depolama tahsis gerekir önce ne kadar kapsayıcı büyüyebilir belirlemek için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_capacity.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// increase capacity   
    cliext::vector<wchar_t>::size_type cap = c1.capacity();   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        cap, c1.size() <= cap);   
    c1.reserve(cap + 5);   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        c1.capacity(), cap + 5 <= c1.capacity());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
capacity() = 4, ok = True  
capacity() = 9, ok = True  
```  

## <a name="clear"></a> Vector::Clear (STL/CLR)
Tüm öğeleri kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void clear();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini etkili bir şekilde çağırır [vector::erase (STL/CLR)](../dotnet/vector-erase-stl-clr.md) `(` [vector::begin (STL/CLR)](../dotnet/vector-begin-stl-clr.md) `(),` [vector::end (STL/CLR)](../dotnet/vector-end-stl-clr.md) `())`. Denetimli sırası boş olduğundan emin olmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```  
// cliext_vector_clear.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
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

## <a name="const_iterator"></a> Vector::const_iterator (STL/CLR)
Denetlenen dizi için bir sabit yineleyici türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef T2 const_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilmeyen türünde bir nesne türünü açıklayan `T2` hizmet eden bir sabit rasgele erişim yineleyici denetlenen dizisi olarak.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_const_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::vector<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        System::Console::Write(" {0}", *cit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="const_reference"></a> Vector::const_reference (STL/CLR)
Bir öğe için sabit bir başvuru türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef value_type% const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğe için sabit bir başvuru türü açıklanmaktadır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_const_reference.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::vector<wchar_t>::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        {   // get a const reference to an element   
        cliext::vector<wchar_t>::const_reference cref = *cit;   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="const_reverse_iterator"></a> Vector::const_reverse_iterator (STL/CLR)
Denetimli sırası için sabit bir ters yineleyici türü...  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilmeyen türünde bir nesne türünü açıklayan `T4` hizmet eden sabit bir ters yineleyici denetlenen dizisi olarak.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::vector<wchar_t>::const_reverse_iterator crit = c1.rbegin();   
    cliext::vector<wchar_t>::const_reverse_iterator crend = c1.rend();   
    for (; crit != crend; ++crit)   
        System::Console::Write(" {0}", *crit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  

## <a name="difference_type"></a> Vector::difference_type (STL/CLR)
İki öğe arasındaki imzalı uzaklığı türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Türünü imzalı öğe sayısını tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_difference_type.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::vector<wchar_t>::difference_type diff = 0;   
    for (cliext::vector<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it) ++diff;   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
  
// compute negative difference   
    diff = 0;   
    for (cliext::vector<wchar_t>::iterator it = c1.end();   
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

## <a name="empty"></a> Vector::Empty (STL/CLR)
Bir öğe olup olmadığını sınar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool empty();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi boş denetimli dizisi için true değerini döndürür. Eşdeğer olan [vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)`() == 0`. Vektör boş olup olmadığını sınamak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_empty.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
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

## <a name="end"></a> Vector::End (STL/CLR)
Denetlenen dizinin bitişini belirtir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
iterator end();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi yalnızca denetimli dizisi ötesinde işaret rasgele erişim yineleyici döndürür. Atayan bir yineleyici almak için kullandığınız `current` denetimli dizisi ancak durumunu sonuna denetimli sırası uzunluğu değişirse değiştirebilirsiniz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_end.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    cliext::vector<wchar_t>::iterator it = c1.end();   
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

## <a name="erase"></a> Vector::ERASE (STL/CLR)
Belirtilen konumlardaki öğeleri kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>Parametreler  
 ilk  
 Silme aralığını başlangıcı.  
  
 Son  
 Silinecek aralığı sonu.  
  
 Burada  
 Silinecek öğe.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi gösterdiği denetimli sırasının öğeyi kaldırır `where`. Tek bir öğe kaldırmak için kullanın.  
  
 İkinci üye işlevi denetlenen sıradaki aralığında kaldırır [`first`, `last`). Sıfır veya daha fazla bitişik öğeleri kaldırmak için kullanın.  
  
 Her iki üye işlevleri kaldırıldı, herhangi bir öğenin dışında kalan ilk öğe atayan bir yineleyici dönün veya [vector::end (STL/CLR)](../dotnet/vector-end-stl-clr.md) `()` böyle bir öğe varsa.  
  
 Öğeleri silme, öğesi kopyaları kuvvetini sonuna bitişinde yakın arasındaki öğelerin sayısı doğrusal sayısıdır. (Bir veya daha fazla öğe sırası her iki ucundaki silme hiçbir öğe kopya oluşur.)  
  
### <a name="example"></a>Örnek  
  
```cpp 
// cliext_vector_erase.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
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
    cliext::vector<wchar_t>::iterator it = c1.end();   
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

## <a name="front"></a> Vector::Front (STL/CLR)
İlk öğe erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
reference front();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi boş olması gerekir denetlenen dizisinin ilk öğesi için bir başvuru döndürür. Okumak veya mevcut bildiğinizde ilk öğe yazmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_front.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
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

# <a name="front_item"></a> Vector::front_item (STL/CLR)
İlk öğe erişir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
property value_type front_item;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Özelliği boş olması gerekir denetlenen dizisinin ilk öğesi erişir. Okumak veya mevcut bildiğinizde ilk öğe yazmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_front_item.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
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

# <a name="generic_container"></a> Vector::generic_container (STL/CLR)
Genel arabirim kapsayıcının türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef Microsoft::VisualC::StlClr::  
    IVector<generic_value>  
    generic_container;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu şablon kapsayıcı sınıfı için genel arabirimi türünü tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_generic_container.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;   
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

## <a name="generic_iterator"></a> Vector::generic_iterator (STL/CLR)
Yineleyici kullanmak için genel arabirimi kapsayıcının türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ContainerRandomAccessIterator<generic_value>  
    generic_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Genel arabirim ile bu şablon kapsayıcı sınıfı için kullanılabilen genel bir yineleyici türünü tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_generic_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::vector<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::vector<wchar_t>::generic_value gcval = *gcit;   
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

# <a name="generic_reverse_iterator"></a> Vector::generic_reverse_iterator (STL/CLR)
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
// cliext_vector_generic_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::vector<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();   
    cliext::vector<wchar_t>::generic_value gcval = *gcit;   
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

## <a name="generic_value"></a> Vector::generic_value (STL/CLR)
Kapsayıcı için genel arabirimi ile kullanmak için öğenin türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef GValue generic_value;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Türünde bir nesne türünü açıklayan `GValue` kullanmak için saklı öğesi değeri bu şablonu kapsayıcı sınıfı için genel arabirimi açıklar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_generic_value.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::vector<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::vector<wchar_t>::generic_value gcval = *gcit;   
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

## <a name="insert"></a> Vector::insert (STL/CLR)
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
 count  
 Eklenecek öğe sayısı.  
  
 ilk  
 Eklenecek Aralık başlangıcı.  
  
 Son  
 Eklenecek aralık sonu.  
  
 sağ  
 Eklenecek numaralandırması.  
  
 VAL  
 Eklenecek öğenin değeri.  
  
 Burada  
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
// cliext_vector_insert.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using iterator   
    cliext::vector<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::vector<wchar_t> c2;   
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
  
## <a name="iterator"></a> Vector::iterator (STL/CLR)
Denetlenen dizi için bir yineleyici türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef T1 iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilmeyen türünde bir nesne türünü açıklayan `T1` hizmet eden denetimli sırası için rasgele erişim yineleyici olarak.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    cliext::vector<wchar_t>::iterator it = c1.begin();   
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

## <a name="op_as"></a> Vector::operator = (STL/CLR)
Denetimli dizisi yerini alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
vector<Value>% operator=(vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 sağ  
 Kopyalamak için kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci kopyaları `right` nesnesine sonra döndürür `*this`. Denetimli sırayla kopyası ile denetlenen sırasını değiştirmek için kullanın `right`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_operator_as.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
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

## <a name="op"></a> Vector::operator(stl/CLR)
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
// cliext_vector_operator_sub.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
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

## <a name="pop_back"></a> Vector::pop_back (STL/CLR)
Son öğeyi kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void pop_back();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi boş olmalıdır denetimli dizisi son öğeyi kaldırır. Vektör arkadaki bir öğe tarafından kısaltmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_pop_back.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
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

## <a name="push_back"></a> Vector::push_back (STL/CLR)
Yeni bir son öğesi ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void push_back(value_type val);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini değeri olan bir öğe ekler `val` denetimli dizisi sonunda. Vektör başka bir öğe eklemek için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_push_back.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
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
  
## <a name="rbegin"></a> Vector::rbegin (STL/CLR)
Ters denetimli dizisi başlangıcını belirtir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
reverse_iterator rbegin();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli dizisi ya da boş bir dizi başına ötesinde yalnızca son öğesi atar ters bir yineleyici döndürür. Bu nedenle, atar `beginning` ters dizisi. Atayan bir yineleyici almak için kullandığınız `current` ters sırada görülen denetimli dizisi ancak durumunu başında denetimli sırası uzunluğu değişirse değiştirebilirsiniz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_rbegin.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rbegin();   
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

## <a name="reference"></a> Vector::Reference (STL/CLR)
Bir öğe için bir başvuru türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğe için bir başvuru türü açıklanmaktadır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_reference.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    cliext::vector<wchar_t>::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::vector<wchar_t>::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
  
// modify contents " a b c"   
    for (it = c1.begin(); it != c1.end(); ++it)   
        {   // get a reference to an element   
        cliext::vector<wchar_t>::reference ref = *it;   
  
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

## <a name="rend"></a> Vector::rend (STL/CLR)
Ters denetimli dizinin sonuna belirler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
reverse_iterator rend();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini ters yineleyici başına yalnızca ötesinde işaret denetimli dizisi döndürür. Bu nedenle, atar `end` ters dizisi. Atayan bir yineleyici almak için kullandığınız `current` ters sırada görülen denetimli dizisi ancak durumunu sonuna denetimli sırası uzunluğu değişirse değiştirebilirsiniz.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_rend.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rend();   
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

## <a name="reserve"></a> Vector::reserve (STL/CLR)
Kapsayıcı için en düşük büyüme kapasitesi sağlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void reserve(size_type count);  
```  
  
#### <a name="parameters"></a>Parametreler  
 count  
 Kapsayıcı yeni en az kapasitesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi sağlar `capacity()` henceforth en az döndürür `count`. Belirtilen boyuta büyümüştür kadar kapsayıcı denetimli dizisi için depolama tahsis değil emin olmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_reserve.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// increase capacity   
    cliext::vector<wchar_t>::size_type cap = c1.capacity();   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        cap, c1.size() <= cap);   
    c1.reserve(cap + 5);   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        c1.capacity(), cap + 5 <= c1.capacity());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
capacity() = 4, ok = True  
capacity() = 9, ok = True  
```  

## <a name="resize"></a> Vector::resize (STL/CLR)
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
 Her iki üye işlevleri emin [vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md) `()` henceforth döndürür `new_size`. Uzun denetimli dizisi yapmanız gerekiyorsa, ilk üye işlevi değer ile öğeleri ekler `value_type()`değere sahip öğeleri ikinci üye işlevi ekler yaparken `val`. Daha kısa denetimli sıra yapmak için her iki üye işlevleri etkili bir şekilde son öğe silme [vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md) `() -` `new_size` kez. Denetimli sırası boyutu olduğundan emin olmak için kullandığınız `new_size`, kırpma ya da geçerli denetimli dizisi doldurma tarafından.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_resize.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::vector<wchar_t> c1;   
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

## <a name="reverse_iterator"></a> Vector::reverse_iterator (STL/CLR)
Denetimli sırası için ters yineleyici türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef T3 reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilmeyen türünde bir nesne türünü açıklayan `T3` hizmet eden bir ters yineleyici denetimli sırası için farklı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rbegin();   
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

## <a name="size"></a> Vector::size (STL/CLR)
Öğe sayısını sayar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
size_type size();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sırası uzunluğunu döndürür. Şu anda denetlenen sıradaki öğelerinin sayısını belirlemek için kullanın. Tüm önem verdiğiniz ise dizisi bkz sıfır olmayan boyutu olup [vector::empty (STL/CLR)](../dotnet/vector-empty-stl-clr.md)`()`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_size.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
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

## <a name="size_type"></a> Vector::size_type (STL/CLR)
İki öğe arasındaki işaretli mesafenin türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Türünü negatif olmayan öğe sayısını tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_size_type.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    cliext::vector<wchar_t>::size_type diff = c1.end() - c1.begin();   
    System::Console::WriteLine("end()-begin() = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
end()-begin() = 3  
```  
  
## <a name="swap"></a> Vector::Swap (STL/CLR)
İki kapsayıcının içeriğinin yerini değiştirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void swap(vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 sağ  
 İçeriği ile değiştirilecek kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sıraları arasında değiştirir `*this` ve `right`. Bunu Sabit sürede yapar ve hiçbir özel durum oluşturur. Bunu iki kapsayıcı içeriğini exchange hızlı bir şekilde kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_swap.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::vector<wchar_t> c2(5, L'x');   
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

## <a name="to_array"></a> Vector::to_array (STL/CLR)
Denetimli sırası yeni bir diziye kopyalar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
cli::array<Value>^ to_array();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi denetimli sırası içeren bir dizi döndürür. Dizi formunda denetimli sırasının bir kopyasını almak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_to_array.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
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

## <a name="value_type"></a> Vector::value_type (STL/CLR)
Öğenin türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef Value value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Value`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_value_type.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using value_type   
    for (cliext::vector<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   // store element in value_type object   
        cliext::vector<wchar_t>::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  

## <a name="vector"></a> Vector::Vector (STL/CLR)
Bir kapsayıcı nesnesi oluşturur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
vector();  
vector(vector<Value>% right);  
vector(vector<Value>^ right);  
explicit vector(size_type count);  
vector(size_type count, value_type val);  
template<typename InIt>  
    vector(InIt first, InIt last);  
vector(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 count  
 Eklenecek öğe sayısı.  
  
 ilk  
 Eklenecek Aralık başlangıcı.  
  
 Son  
 Eklenecek aralık sonu.  
  
 sağ  
 Nesne veya eklemek için aralık.  
  
 VAL  
 Eklenecek öğenin değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucusu:  
  
 `vector();`  
  
 denetimli sıralı öğe ile başlatır. Boş bir başlangıç denetimli dizisini belirtmek için kullanın.  
  
 Oluşturucusu:  
  
 `vector(vector<Value>% right);`  
  
 denetimli dizisi dizisiyle başlatır [`right.begin()`, `right.end()`). Vektör nesnesi tarafından denetlenen sırasının bir kopyasını bir ilk denetlenen sırası belirtmek için kullandığınız `right`.  
  
 Oluşturucusu:  
  
 `vector(vector<Value>^ right);`  
  
 denetimli dizisi dizisiyle başlatır [`right->begin()`, `right->end()`). Bir kopyasını, tanıtıcısı vektör nesnesi tarafından denetlenen sırası olan ilk denetimli bir sıra belirtmek için kullandığınız `right`.  
  
 Oluşturucusu:  
  
 `explicit vector(size_type count);`  
  
 denetimli dizisiyle başlatır `count` öğeleriyle her değer `value_type()`. Kapsayıcı öğeler ile doldurmak için varsayılan değer tüm sahip kullanırsınız.  
  
 Oluşturucusu:  
  
 `vector(size_type count, value_type val);`  
  
 denetimli dizisiyle başlatır `count` öğeleriyle her değer `val`. Kapsayıcı öğeler ile doldurmak için tüm aynı değere sahip kullanırsınız.  
  
 Oluşturucusu:  
  
 `template<typename InIt>`  
  
 `vector(InIt first, InIt last);`  
  
 denetimli dizisi dizisiyle başlatır [`first`, `last`). Denetimli sırası başka bir dizi bir kopya yapmak için kullanın.  
  
 Oluşturucusu:  
  
 `vector(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 Numaralandırıcı tarafından belirtilen sıra ile denetlenen dizisi başlatır `right`. Denetimli sırası bir numaralandırıcı tarafından açıklanan başka bir dizi bir kopya yapmak için kullanın.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_construct.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container   
    cliext::vector<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::vector<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::vector<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::vector<wchar_t>::iterator it = c3.end();   
    cliext::vector<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::vector<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::vector<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::vector<wchar_t> c8(%c3);   
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

## <a name="op_neq"></a> operator! = (vektör) (STL/CLR)
Eşit değildir karşılaştırma vektör.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename Value>  
    bool operator!=(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `!(left == right)`. Test etmek için kullandığınız olup olmadığını `left` aynı sıralı değil `right` iki vektörü öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_operator_ne.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
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

## <a name="op_lt"></a> İşleç&lt; (vektör) (STL/CLR)
Vektör karşılaştırma küçüktür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    bool operator<(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleci işlevi döndürür true ise, en düşük konumunun `i` kendisi için `!(right[i] < left[i])` Ayrıca, true olan `left[i] < right[i]`. Aksi takdirde, döndürür `left->size() < right->size()` test etmek için kullandığınız olup olmadığını `left` önce sıralanır `right` iki vektörü öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_operator_lt.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
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

## <a name="op_lteq"></a> İşleç&lt;= (vektör) (STL/CLR)
Küçük veya buna eşit vektör karşılaştırma.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    bool operator<=(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `!(right < left)`. Test etmek için kullandığınız olup olmadığını `left` sonra sıralı değil `right` iki vektörü öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_operator_le.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
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

## <a name="op_eq"></a> operator == (vektör) (STL/CLR)
Vektör eşit karşılaştırması.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    bool operator==(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi sıraları denetlediği yalnızca, true değerini döndürür `left` ve `right` aynı uzunlukta olması ve her konum için `i`, `left[i] ==` `right[i]`. Test etmek için kullandığınız olup olmadığını `left` aynı sıralı `right` iki vektörü öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_operator_eq.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
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

## <a name="op_gt"></a> İşleç&gt; (vektör) (STL/CLR)
Vektör karşılaştırma büyük.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    bool operator>(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `right` `<` `left`. Test etmek için kullandığınız olup olmadığını `left` sonra sıralanmış `right` iki vektörü öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_operator_gt.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
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

## <a name="op_gteq"></a> İşleç&gt;= (vektör) (STL/CLR)
Vektör daha büyük veya eşit karşılaştırma.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    bool operator>=(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol kapsayıcı.  
  
 sağ  
 Karşılaştırılacak sağ kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `!(left < right)`. Test etmek için kullandığınız olup olmadığını `left` önce sıralı değil `right` iki vektörü öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_vector_operator_ge.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
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
