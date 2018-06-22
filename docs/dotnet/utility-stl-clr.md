---
title: yardımcı program (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/utility>
- cliext::pair
- cliext::pair::pair
- cliext::pair::first
- cliext::pair::first_type
- cliext::pair::second
- cliext::pair::second_type
- cliext::pair::swap
- cliext::make_pair
- cliext::pair::operator=
- cliext::pair::operator==
- cliext::pair::operator>=
- cliext::pair::operator>
- cliext::pair::operator!=
- cliext::pair::operator<=
- cliext::pair::operator<
dev_langs:
- C++
helpviewer_keywords:
- <utility> header [STL/CLR]
- utility header [STL/CLR]
- <cliext/utility> header [STL/CLR]
- first member [STL/CLR]
- first_type member [STL/CLR]
- second member [STL/CLR]
- second_type member [STL/CLR]
- swap member [STL/CLR]
- make_pair function [STL/CLR]
- pair class [STL/CLR]
- pair member [STL/CLR]
- operator== member [STL/CLR]
- operator= member [STL/CLR]
- operator>= member [STL/CLR]
- operator> member [STL/CLR]
- operator!= member [STL/CLR]
- operator<= member [STL/CLR]
- operator< member [STL/CLR]
ms.assetid: fb48cb75-d5ef-47ce-b526-bf60dc86c552
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fcc97e5037898b3a9c39a6c72ed21b2c19a4c777
ms.sourcegitcommit: 301bb19056e5bae84ff50f7d1df1e546efe225ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36306027"
---
# <a name="utility-stlclr"></a>yardımcı program (STL/CLR)
STL/CLR üstbilgisini `<cliext/utility>` Şablon sınıfı tanımlamak için `pair` ve çeşitli destekleyici şablon işlevleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <utility>  
```

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/yardımcı programı >  
  
 **Namespace:** cliext  
  
## <a name="declarations"></a>Bildirimler  
  
|örneği|Açıklama|  
|-----------|-----------------|  
|[pair (STL/CLR)](#pair)|Çiftlerini sarılır.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[operator== (pair) (STL/CLR)](#op_eq)|Çifti karşılaştırma eşit.|  
|[operator!= (pair) (STL/CLR)](#op_neq)|Eşit değildir karşılaştırma eşleştirin.|  
|[operator< (pair) (STL/CLR)](#op_lt)|Çifti karşılaştırma küçüktür.|  
|[İşleç\<(eşleştirmesi) (STL/CLR)](#op_lteq)|Küçük veya buna eşit eşleştirin karşılaştırma.|  
|[operator> (pair) (STL/CLR)](#op_gt)|Çifti karşılaştırma büyük.|  
|[operator>= (pair) (STL/CLR)](#op_gteq)|Çifti daha büyük veya eşit karşılaştırma.|  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|[make_pair (STL/CLR)](#make_pair)|Bir çift değer çiftinden olun.|  

## <a name="members"></a>Üyeler

##<a name="pair"></a> çift (STL/CLR)
Şablon sınıfı bir değer çifti saran bir nesne tanımlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value1,  
    typename Value2>  
    ref class pair;  
```  
  
#### <a name="parameters"></a>Parametreler  
 Değer1  
 İlk sarılan değer türü.  
  
 Value2  
 İkinci sarılan değer türü.  
  
## <a name="members"></a>Üyeler  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|[pair::first_type (STL/CLR)](#first_type)|İlk sarılan değer türü.|  
|[pair::second_type (STL/CLR)](#second_type)|İkinci sarılan değer türü.|  
  
|Üye nesnesi|Açıklama|  
|-------------------|-----------------|  
|[pair::first (STL/CLR)](#first)|İlk depolanan değer.|  
|[pair::second (STL/CLR)](#second)|İkinci depolanan değer.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[pair::pair (STL/CLR)](#pair_pair)|Çifti nesnesi oluşturur.|  
|[pair::swap (STL/CLR)](#swap)|İki çift içeriğini değiştirir.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[pair::operator= (STL/CLR)](#op_as)|Depolanan değer çifti yerini alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesnesi bir değer çifti depolar. Bu şablon sınıfı iki değer tek bir nesnede birleştirmek için kullanın. Ayrıca, nesne `cliext::pair` (aşağıda açıklanmıştır) yönetilmeyen çifti depolamak için türlerini kullanın; depoları türleri yalnızca yönetilen `std::pair`bildirilen `<utility>`.  


## <a name="first"></a> pair::First (STL/CLR)
İlk sarılan değer.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
Value1 first;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne ilk Sarmalanan değerini depolar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_pair_first.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
```  

## <a name="first_type"></a> pair::first_type (STL/CLR)
İlk sarılan değer türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef Value1 first_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Value1`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_pair_first_type.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
```  

## <a name="op_as"></a> pair::operator (STL/CLR) =
Depolanan değer çifti yerini alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 sağ  
 Kopyalamak için çifti.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci kopyaları `right` nesnesine sonra döndürür `*this`. Depolanan değer çifti değerlerinin saklı çiftinin bir kopya ile değiştirmek için kullandığınız `right`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_pair_operator_as.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
// assign to a new pair   
    cliext::pair<wchar_t, int> c2;   
    c2 = c1;   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 3]  
```  

## <a name="pair_pair"></a> pair::pair (STL/CLR)
Çifti nesnesi oluşturur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
pair();  
pair(pair<Coll>% right);  
pair(pair<Coll>^ right);  
pair(Value1 val1, Value2 val2);  
```  
  
#### <a name="parameters"></a>Parametreler  
 sağ  
 Depolamak için çifti.  
  
 val1  
 Depolamak için ilk değer.  
  
 değer2  
 Depolamak için ikinci değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucusu:  
  
 `pair();`  
  
 saklı çifti oluşturulan varsayılan değerlerle başlatır.  
  
 Oluşturucusu:  
  
 `pair(pair<Value1, Value2>% right);`  
  
 saklı çifti ile başlatır `right.` [pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md) ve `right.` [pair::second (STL/CLR)](../dotnet/pair-second-stl-clr.md).  
  
 `pair(pair<Value1, Value2>^ right);`  
  
 saklı çifti ile başlatır `right->` [pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md) ve `right>` [pair::second (STL/CLR)](../dotnet/pair-second-stl-clr.md).  
  
 Oluşturucusu:  
  
 `pair(Value1 val1, Value2 val2);`  
  
 ile saklı çifti ile başlatır `val1` ve `val2`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_pair_construct.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
// construct an empty container   
    cliext::pair<wchar_t, int> c1;   
    System::Console::WriteLine("[{0}, {1}]",   
        c1.first == L'\0' ? "\\0" : "??", c1.second);   
  
// construct with a pair of values   
    cliext::pair<wchar_t, int> c2(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
// construct by copying another pair   
    cliext::pair<wchar_t, int> c3(c2);   
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);   
  
// construct by copying a pair handle   
    cliext::pair<wchar_t, int> c4(%c3);   
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);   
  
    return (0);   
    }  
  
```  
  
```Output  
[\0, 0]  
[x, 3]  
[x, 3]  
[x, 3]  
```  

## <a name="second"></a> pair::Second (STL/CLR)
İkinci değer sarılır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
Value2 second;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne ikinci Sarmalanan değerini depolar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_pair_second.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
```  

## <a name="second_type"></a> pair::second_type (STL/CLR)
İkinci sarılan değer türü.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
typedef Value2 second_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Value2`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_pair_second_type.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
```    

## <a name="swap"></a> pair::Swap (STL/CLR)
İki çift içeriğini değiştirir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void swap(pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 sağ  
 İçeriği ile değiştirilecek çifti.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini depolanan değer çifti arasında değiştirir `*this` ve `right`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_pair_swap.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::deque<wchar_t> d2(5, L'x');   
    Mycoll c2(%d2);   
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

## <a name="make_pair"></a> make_pair (STL/CLR)
Olun bir `pair` gelen bir değer çifti.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value1,  
    typename Value2>  
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Value1`  
 İlk sarılan değer türü.  
  
 `Value2`  
 İkinci sarılan değer türü.  
  
 `first`  
 Sarmalamak için ilk değer.  
  
 `second`  
 Sarmalamak için ikinci değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon işlevi döndürür `pair<Value1, Value2>(first, second)`. Oluşturmak için kullandığınız bir `pair<Value1, Value2>` bir değer çifti nesnesi.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_make_pair.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    c1 = cliext::make_pair(L'y', 4);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[y, 4]  
```  

## <a name="op_neq"></a> operator! = (çifti) (STL/CLR)
Eşit değildir karşılaştırma eşleştirin.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator!=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol çifti.  
  
 sağ  
 Karşılaştırılacak sağ çifti.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `!(left == right)`. Test etmek için kullandığınız olup olmadığını `left` aynı sıralı değil `right` iki çift öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp
// cliext_pair_operator_ne.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] != [x 3] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[x 3] != [x 4] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] != [x 3] is False  
[x 3] != [x 4] is True  
```  
  
## <a name="op_lt"></a> İşleç&lt; (çifti) (STL/CLR)
Çifti karşılaştırma küçüktür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator<(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol çifti.  
  
 sağ  
 Karşılaştırılacak sağ çifti.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `left.first <` `right.first || !(right.first <` `left.first &&` `left.second <` `right.second`. Test etmek için kullandığınız olup olmadığını `left` sıralanır önce `right` iki çift öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_pair_operator_lt.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] < [x 3] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[x 3] < [x 4] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] < [x 3] is False  
[x 3] < [x 4] is True  
```  

## <a name="op_lteq"></a> İşleç&lt;(eşleştirmesi) (STL/CLR)
Küçük veya buna eşit eşleştirin karşılaştırma.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator<=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol çifti.  
  
 sağ  
 Karşılaştırılacak sağ çifti.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `!(right < left)`. Test etmek için kullandığınız olup olmadığını `left` sonra sıralı değil `right` iki çift öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_pair_operator_le.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] <= [x 3] is {0}",   
        c1 <= c1);   
    System::Console::WriteLine("[x 4] <= [x 3] is {0}",   
        c2 <= c1);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] <= [x 3] is True  
[x 4] <= [x 3] is False  
```  
  
## <a name="op_eq"></a> operator == (çifti) (STL/CLR)
Çifti karşılaştırma eşit.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator==(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol çifti.  
  
 sağ  
 Karşılaştırılacak sağ çifti.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `left.first ==` `right.first &&` `left.second ==` `right.second`. Test etmek için kullandığınız olup olmadığını `left` aynı sıralı `right` iki çift öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_pair_operator_eq.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] == [x 3] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[x 3] == [x 4] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] == [x 3] is True  
[x 3] == [x 4] is False  
```  

## <a name="op_gt"></a> İşleç&gt; (çifti) (STL/CLR)
Çifti karşılaştırma büyük.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator>(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol çifti.  
  
 sağ  
 Karşılaştırılacak sağ çifti.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `right` `<` `left`. Test etmek için kullandığınız olup olmadığını `left` sonra sıralanmış `right` iki çift öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_pair_operator_gt.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] > [x 3] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[x 4] > [x 3] is {0}",   
        c2 > c1);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] > [x 3] is False  
[x 4] > [x 3] is True  
```  

## <a name="op_gteq"></a> İşleç&gt;(eşleştirmesi) (STL/CLR)
Çifti daha büyük veya eşit karşılaştırma.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator>=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parametreler  
 left  
 Karşılaştırılacak sol çifti.  
  
 sağ  
 Karşılaştırılacak sağ çifti.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç işlevi döndürür `!(left < right)`. Test etmek için kullandığınız olup olmadığını `left` önce sıralı değil `right` iki çift öğe tarafından karşılaştırılan öğe olduğunda.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// cliext_pair_operator_ge.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] >= [x 3] is {0}",   
        c1 >= c1);   
    System::Console::WriteLine("[x 3] >= [x 4] is {0}",   
        c1 >= c2);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] >= [x 3] is True  
[x 3] >= [x 4] is False  
```  
