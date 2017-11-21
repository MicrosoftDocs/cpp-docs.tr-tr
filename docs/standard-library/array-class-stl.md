---
title: "array sınıfı (Standart C++ Kitaplığı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- array/std::array
- array/std::array::const_iterator
- array/std::array::const_pointer
- array/std::array::const_reference
- array/std::array::const_reverse_iterator
- array/std::array::difference_type
- array/std::array::iterator
- array/std::array::pointer
- array/std::array::reference
- array/std::array::reverse_iterator
- array/std::array::size_type
- array/std::array::value_type
- array/std::array::assign
- array/std::array::at
- array/std::array::back
- array/std::array::begin
- array/std::array::cbegin
- array/std::array::cend
- array/std::array::crbegin
- array/std::array::crend
- array/std::array::data
- array/std::array::empty
- array/std::array::end
- array/std::array::fill
- array/std::array::front
- array/std::array::max_size
- array/std::array::rbegin
- array/std::array::rend
- array/std::array::size
- array/std::array::swap
- array/std::array::operator=
- array/std::array::operator[]
dev_langs: C++
helpviewer_keywords:
- std::array [C++]
- std::array [C++], const_iterator
- std::array [C++], const_pointer
- std::array [C++], const_reference
- std::array [C++], const_reverse_iterator
- std::array [C++], difference_type
- std::array [C++], iterator
- std::array [C++], pointer
- std::array [C++], reference
- std::array [C++], reverse_iterator
- std::array [C++], size_type
- std::array [C++], value_type
- std::array [C++], assign
- std::array [C++], at
- std::array [C++], back
- std::array [C++], begin
- std::array [C++], cbegin
- std::array [C++], cend
- std::array [C++], crbegin
- std::array [C++], crend
- std::array [C++], data
- std::array [C++], empty
- std::array [C++], end
- std::array [C++], fill
- std::array [C++], front
- std::array [C++], max_size
- std::array [C++], rbegin
- std::array [C++], rend
- std::array [C++], size
- std::array [C++], swap
- ', '
- std::array [C++], const_iterator
- std::array [C++], const_pointer
- std::array [C++], const_reference
- std::array [C++], const_reverse_iterator
- std::array [C++], difference_type
- std::array [C++], iterator
- std::array [C++], pointer
- std::array [C++], reference
- std::array [C++], reverse_iterator
- std::array [C++], size_type
- std::array [C++], value_type
- std::array [C++], assign
- std::array [C++], at
- std::array [C++], back
- std::array [C++], begin
- std::array [C++], cbegin
- std::array [C++], cend
- std::array [C++], crbegin
- std::array [C++], crend
- std::array [C++], data
- std::array [C++], empty
- std::array [C++], end
- std::array [C++], fill
- std::array [C++], front
- std::array [C++], max_size
- std::array [C++], rbegin
- std::array [C++], rend
- std::array [C++], size
- std::array [C++], swap
ms.assetid: fdfd43a5-b2b5-4b9e-991f-93bf10fb4293
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ceec96efcfde06af2ad98178dff41f8569a81d85
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="array-class-c-standard-library"></a>array sınıfı (Standart C++ Kitaplığı)
Uzunluk dizisi denetleyen bir nesneyi tanımlayan `N` türü öğelerinin `Ty`. Sıralı bir dizisi olarak depolanan `Ty`, içerdiği `array<Ty, N>` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Ty, std::size_t N>  
class array;  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`Ty`|Öğenin türü.|  
|`N`|Öğe sayısı.|  
  
## <a name="members"></a>Üyeler  
  
|||  
|-|-|  
|Tür Tanımlaması|Açıklama|  
|[const_iterator](#const_iterator)|Denetlenen dizi için bir sabit yineleyici türü.|  
|[const_pointer](#const_pointer)|Bir öğe için sabit bir işaretçi türü.|  
|[const_reference](#const_reference)|Bir öğe için sabit bir başvuru türü.|  
|[const_reverse_iterator](#const_reverse_iterator)|Denetimli sırası için sabit bir ters yineleyici türü.|  
|[difference_type](#difference_type)|İki öğe arasındaki işaretli mesafenin türü.|  
|[Yineleyici](#iterator)|Denetlenen dizi için bir yineleyici türü.|  
|[İşaretçi](#pointer)|Bir öğe için bir işaretçi türü.|  
|[başvuru](#reference)|Bir öğe için bir başvuru türü.|  
|[reverse_iterator](#reverse_iterator)|Denetimli sırası için ters yineleyici türü.|  
|[size_type](#size_type)|İki öğe arasındaki işaretsiz bir mesafenin türü.|  
|[value_type](#value_type)|Öğenin türü.|  
  
|||  
|-|-|  
|Üye İşlevi|Açıklama|  
|[dizi](#array)|Bir dizi nesnesi oluşturur.|  
|[Ata](#assign)|Tüm öğeleri değiştirir.|  
|[konumundaki](#at)|Belirtilen konumda bir öğe erişir.|  
|[Geri](#back)|Son öğe erişir.|  
|[başlayın](#begin)|Denetlenen dizinin başlangıcını belirtir.|  
|[cbegin](#cbegin)|Rasgele erişim const yineleyici dizinin ilk öğesi döndürür.|  
|[cend](#cend)|Rasgele erişim const yineleyici dizinin yalnızca ötesinde işaret döndürür.|  
|[crbegin](#crbegin)|Const yineleyici ters dizinin ilk öğesi döndürür.|  
|[crend](#crend)|Const yineleyici ters dizinin sonuna döndürür.|  
|[veri](#data)|İlk öğe adresini alır.|  
|[boş](#empty)|Öğeleri olup testleri sunar.|  
|[Bitiş](#end)|Denetlenen dizinin bitişini belirtir.|  
|[doldurma](#fill)|Tüm öğeleri belirtilen bir değeri ile değiştirir.|  
|[Ön](#front)|İlk öğe erişir.|  
|[max_size](#max_size)|Öğe sayısını sayar.|  
|[rbegin](#rbegin)|Ters denetimli dizisi başlangıcını belirtir.|  
|[rend](#rend)|Ters denetimli dizinin sonuna belirler.|  
|[boyutu](#size)|Öğe sayısını sayar.|  
|[değiştirme](#swap)|İki kapsayıcının içeriğinin yerini değiştirir.|  
  
|||  
|-|-|  
|İşleç|Açıklama|  
|[Array::operator =](#op_eq)|Denetimli dizisi yerini alır.|  
|[Array::operator]](#op_at)|Belirtilen konumda bir öğe erişir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan bir oluşturucu türünde `array()` ve varsayılan atama işleci `operator=`ve gereksinimlerini karşılayan bir `aggregate`. Bu nedenle, nesne türü `array<Ty, N>` birleşik bir başlatıcı kullanarak başlatılabilir. Örneğin,  
  
```  
array<int, 4> ai = { 1, 2, 3 };  
```  
  
 nesnesi oluşturur `ai` dört tamsayı değerleri, değerler 1, 2 ve 3 ' ü ilk üç öğelerine sırasıyla başlatır ve 0 dördüncü öğesine başlatır tutar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<dizi >  
  
 **Namespace:** std  
  
##  <a name="array"></a>Array::Array  
 Bir dizi nesnesi oluşturur.  
  
```  
array();

array(const array& right);
```  
  
### <a name="parameters"></a>Parametreler  
*sağ*  
 Nesne veya eklemek için aralık.  
  
### <a name="remarks"></a>Açıklamalar  
Varsayılan Oluşturucu `array()` denetimli başlatılmadı dizisi (veya varsayılan başlatıldı) bırakır. Başlatılmamış denetimli dizisi belirtmek için kullanın.  
  
Kopya Oluşturucu `array(const array& right)` dizisi ile denetlenen dizisi başlatır [*sağ*`.begin()`, *sağ*`.end()`). Dizi nesnesi tarafından denetlenen sırasının bir kopyasını bir ilk denetlenen sırası belirtmek için kullandığınız *sağ*.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_array.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1(c0);   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
```  
  
##  <a name="assign"></a>Array::Assign  
Değiştirilmiştir C ++ 11,'te eski [dolgu](#fill). Tüm öğeleri değiştirir.  
  
```  
void assign(const Ty& val);
```  
  
### <a name="parameters"></a>Parametreler  
 `val`  
 Atanacak değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye fonksiyonu tarafından denetlenen dizisi değiştirir `*this` bir yinelenmesinin ile `N` değerinin öğeleri `val`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_assign.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1;   
    c1.assign(4);   
  
// display contents " 4 4 4 4"   
    for (Myarray::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4 4 4 4  
```  
  
##  <a name="at"></a>Array::AT  
 Belirtilen konumda bir öğe erişir.  
  
```  
reference at(size_type off);

constexpr const_reference at(size_type off) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `off`  
 Erişim öğesinin konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevleri konumunda denetimli dizisi öğesi başvuru döndürmek `off`. Bu konumu geçersiz, işlevi sınıfın bir nesnesi döndürürse `out_of_range`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_at.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display odd elements " 1 3"   
    std::cout << " " << c0.at(1);   
    std::cout << " " << c0.at(3);   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
##  <a name="back"></a>Array::Back  
 Son öğe erişir.  
  
```  
reference back();

constexpr const_reference back() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevleri son öğe boş olmalıdır denetimli dizisi için bir başvuru döndürür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_back.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display last element " 3"   
    std::cout << " " << c0.back();   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
3  
```  
  
##  <a name="begin"></a>Array::Begin  
 Denetlenen dizinin başlangıcını belirtir.  
  
```  
iterator begin() noexcept;  
const_iterator begin() const noexcept;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevleri rasgele erişim yineleyici bu noktalarda ilk öğe dizisi (veya yalnızca boş bir dizi ötesinde) döndürür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_begin.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::iterator it2 = c0.begin();   
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="cbegin"></a>Array::cbegin  
 Döndürür bir `const` aralığın ilk öğe adresleri yineleyici.  
  
```  
const_iterator cbegin() const noexcept;  
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
  
##  <a name="cend"></a>Array::cend  
 Döndürür bir `const` konumun yalnızca bir aralıkta son öğenin ötesinde adresleri yineleyici.  
  
```  
const_iterator cend() const noexcept;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aralığın hemen sonunu gösteren bir rastgele erişim yineleyicisi.  
  
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
  
##  <a name="const_iterator"></a>Array::const_iterator  
 Denetlenen dizi için bir sabit yineleyici türü.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimli sırası için sabit bir rastgele erişim yineleyici olarak hizmet verebilir bir nesne türünü tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_const_iterator.cpp  
// compile with: /EHsc /W4  
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> MyArray;   
  
int main()   
{   
    MyArray c0 = {0, 1, 2, 3};   
  
    // display contents " 0 1 2 3"   
    std::cout << "it1:";  
    for ( MyArray::const_iterator it1 = c0.begin();   
          it1 != c0.end();   
          ++it1 ) {  
       std::cout << " " << *it1;   
    }  
    std::cout << std::endl;   
  
    // display first element " 0"   
    MyArray::const_iterator it2 = c0.begin();   
    std::cout << "it2:";  
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
}  
  
```  
  
```Output  
it1: 0 1 2 3                                  
  
it2: 0  
  
```  
  
##  <a name="const_pointer"></a>Array::const_pointer  
 Bir öğe için sabit bir işaretçi türü.  
  
```  
typedef const Ty *const_pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sıradaki için sabit bir işaretçi olarak hizmet verebilir bir nesne türünü tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_const_pointer.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::const_pointer ptr = &*c0.begin();   
    std::cout << " " << *ptr;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="const_reference"></a>Array::const_reference  
 Bir öğe için sabit bir başvuru türü.  
  
```  
typedef const Ty& const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Öğenin denetimli dizisi sabit bir başvuru olarak hizmet verebilir bir nesne türünü tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_const_reference.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::const_reference ref = *c0.begin();   
    std::cout << " " << ref;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="const_reverse_iterator"></a>Array::const_reverse_iterator  
 Denetimli sırası için sabit bir ters yineleyici türü.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimli sırası için sabit bir ters yineleyici olarak hizmet verebilir bir nesne türünü tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_const_reverse_iterator.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display last element " 3"   
    Myarray::const_reverse_iterator it2 = c0.rbegin();   
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
3  
```  
  
##  <a name="crbegin"></a>Array::crbegin  
 Const yineleyici ters dizinin ilk öğesi döndürür.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir const ters bir dizi ilk öğe adresleme veya ne unreversed dizideki son öğe olsaydı adresleme rasgele erişim yineleyici ters çevrilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri ile `crbegin`, dizi nesnesi değiştirilemez.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// array_crbegin.cpp  
// compile with: /EHsc  
#include <array>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   array<int, 2> v1 = {1, 2};  
   array<int, 2>::iterator v1_Iter;  
   array<int, 2>::const_reverse_iterator v1_rIter;  
  
   v1_Iter = v1.begin( );  
   cout << "The first element of array is "  
        << *v1_Iter << "." << endl;  
  
   v1_rIter = v1.crbegin( );  
   cout << "The first element of the reversed array is "  
        << *v1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element of array is 1.  
The first element of the reversed array is 2.  
```  
  
##  <a name="crend"></a>Array::crend  
 Ters bir dizi son öğesi başarılı konumu adresleri const bir yineleyici döndürür.  
  
```  
const_reverse_iterator crend() const noexcept;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir const ters bir dizi (ilk öğe unreversed dizisinde öncesinde konum) son öğesi başarılı konumu adresleri rasgele erişim yineleyici ters çevrilir.  
  
### <a name="remarks"></a>Açıklamalar  
 `crend`Ters dizisiyle kullanılan gibi [array::cend](#cend) bir dizi ile kullanılır.  
  
 Dönüş değeri ile `crend` (uygun indirildiği), dizi nesnesi değiştirilemez.  
  
 `crend`Ters yineleyici kendi dizinin sonuna olup ulaştı için test etmek için kullanılabilir.  
  
 Tarafından döndürülen değer `crend` değil başvuru yapıldı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// array_crend.cpp  
// compile with: /EHsc  
#include <array>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   array<int, 2> v1 = {1, 2};  
   array<int, 2>::const_reverse_iterator v1_rIter;  
  
   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )  
      cout << *v1_rIter << endl;  
}  
```  
  
```Output  
2  
1  
```  
  
##  <a name="data"></a>Array::Data  
 İlk öğe adresini alır.  
  
```  
Ty *data();

const Ty *data() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevleri denetimli sırayla ilk öğe adresini döndürür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_data.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::pointer ptr = c0.data();   
    std::cout << " " << *ptr;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="difference_type"></a>Array::difference_type  
 İki öğe arasındaki işaretli mesafenin türü.  
  
```  
typedef std::ptrdiff_t difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İmzalı tamsayı türünü herhangi iki öğe denetlenen sıradaki adreslerini arasındaki farkı temsil eden bir nesne tanımlar. Türü için eş anlamlı olduğundan `std::ptrdiff_t`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_difference_type.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display distance first-last " -4"   
    Myarray::difference_type diff = c0.begin() - c0.end();   
    std::cout << " " << diff;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
-4  
```  
  
##  <a name="empty"></a>Array::empty  
 Bir öğe olup olmadığını sınar.  
  
```  
constexpr bool empty() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini ise true değerini döndürür `N == 0`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_empty.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display whether c0 is empty " false"   
    std::cout << std::boolalpha << " " << c0.empty();   
    std::cout << std::endl;   
  
    std::array<int, 0> c1;   
  
// display whether c1 is empty " true"   
    std::cout << std::boolalpha << " " << c1.empty();   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
false  
true  
```  
  
##  <a name="end"></a>Array::End  
 Denetlenen dizinin bitişini belirtir.  
  
```  
reference end();

const_reference end() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevleri rasgele erişim yineleyici dizisi yalnızca ötesinde işaret döndür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_end.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display last element " 3"   
    Myarray::iterator it2 = c0.end();   
    std::cout << " " << *--it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
3  
```  
  
##  <a name="fill"></a>Array::Fill  
 Bir dizi siler ve belirtilen öğelerini boş diziye kopyalar.  
  
```  
void fill(const Type& val);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|`val`|Diziye eklenen öğesinin değeri.|  
  
### <a name="remarks"></a>Açıklamalar  
 `fill`Dizideki her öğe, belirtilen değerle değiştirir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// array_fill.cpp  
// compile with: /EHsc  
#include <array>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   array<int, 2> v1 = {1, 2};  
   array<int, 2>::iterator iter;  
  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
   v1.fill(3);  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
}  
```  
  
##  <a name="front"></a>Array::Front  
 İlk öğe erişir.  
  
```  
reference front();

constexpr const_reference front() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevleri boş olması gerekir denetlenen dizisinin ilk öğesi bir başvuru döndürür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_front.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    std::cout << " " << c0.front();   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="iterator"></a>Array::iterator  
 Denetlenen dizi için bir yineleyici türü.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimli sırası için rasgele erişim yineleyici olarak hizmet verebilir bir nesne türünü tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_iterator.cpp   
// compile with: /EHsc /W4  
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> MyArray;   
  
int main()   
{   
    MyArray c0 = {0, 1, 2, 3};   
  
    // display contents " 0 1 2 3"   
    std::cout << "it1:";  
    for ( MyArray::iterator it1 = c0.begin();   
          it1 != c0.end();   
          ++it1 ) {  
       std::cout << " " << *it1;   
    }  
    std::cout << std::endl;   
  
    // display first element " 0"   
    MyArray::iterator it2 = c0.begin();   
    std::cout << "it2:";  
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
}  
  
```  
  
```Output  
it1: 0 1 2 3                                  
  
it2: 0  
  
```  
  
##  <a name="max_size"></a>Array::max_size  
 Öğe sayısını sayar.  
  
```  
constexpr size_type max_size() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür `N`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_max_size.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display (maximum) size " 4"   
    std::cout << " " << c0.max_size();   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4  
```  
  
##  <a name="op_at"></a>Array::operator]  
 Belirtilen konumda bir öğe erişir.  
  
```  
reference operator[](size_type off);

constexpr const_reference operator[](size_type off) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `off`  
 Erişim öğesinin konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevleri konumunda denetimli dizisi öğesi başvuru döndürmek `off`. Bu konum geçersizse, tanımlanmamış bir davranıştır.  
  
Ayrıca olmayan üyesi olduğu [almak](array-functions.md#get) işlevi bir öğesine bir başvuru almak için kullanılabilen bir `array`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_operator_sub.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display odd elements " 1 3"   
    std::cout << " " << c0[1];   
    std::cout << " " << c0[3];   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
1 3  
```  
  
##  <a name="op_eq"></a>Array::operator =  
 Denetimli dizisi yerini alır.  
  
```  
array <Value>%  operator=(array <Value>% right);
```  
  
### <a name="parameters"></a>Parametreler  
 sağ  
 Kopyalamak için kapsayıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci her öğeye atar `right` için karşılık gelen öğe denetimli dizisi sonra döndürür `*this`. Denetimli sırayla kopyası ile denetlenen sırasını değiştirmek için kullanın `right`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_operator_as.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1;   
    c1 = c0;   
  
// display copied contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
```  
  
##  <a name="pointer"></a>Array::pointer  
 Bir öğe için bir işaretçi türü.  
  
```  
typedef Ty *pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sıradaki gösteren bir işaretçi olarak hizmet verebilir bir nesne türünü tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_pointer.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::pointer ptr = &*c0.begin();   
    std::cout << " " << *ptr;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="rbegin"></a>Array::rbegin  
 Ters denetimli dizisi başlangıcını belirtir.  
  
```  
reverse_iterator rbegin()noexcept;  
const_reverse_iterator rbegin() const noexcept;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevleri yalnızca denetimli dizisi ötesinde işaret ters yineleyici döndür. Bu nedenle, geriye doğru dizisi başlangıcını belirtir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_rbegin.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display last element " 3"   
    Myarray::const_reverse_iterator it2 = c0.rbegin();   
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
3  
```  
  
##  <a name="reference"></a>Array::Reference  
 Bir öğe için bir başvuru türü.  
  
```  
typedef Ty& reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Öğenin denetimli sırasının bir başvuru olarak hizmet verebilir bir nesne türünü tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_reference.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::reference ref = *c0.begin();   
    std::cout << " " << ref;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="rend"></a>Array::rend  
 Ters denetimli dizinin sonuna belirler.  
  
```  
reverse_iterator rend()noexcept;  
const_reverse_iterator rend() const noexcept;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevleri ters yineleyici bu noktalarda ilk öğe dizisi (veya yalnızca boş bir dizi ötesinde) return). Bu nedenle, geriye doğru bitişinde belirler.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_rend.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display first element " 0"   
    Myarray::const_reverse_iterator it2 = c0.rend();   
    std::cout << " " << *--it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0  
```  
  
##  <a name="reverse_iterator"></a>Array::reverse_iterator  
 Denetimli sırası için ters yineleyici türü.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimli sırası için ters yineleyici olarak hizmet verebilir bir nesne türünü tanımlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_reverse_iterator.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display last element " 3"   
    Myarray::reverse_iterator it2 = c0.rbegin();   
    std::cout << " " << *it2;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
3  
```  
  
##  <a name="size"></a>Array::size  
 Öğe sayısını sayar.  
  
```  
constexpr size_type size() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür `N`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_size.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display size " 4"   
    std::cout << " " << c0.size();   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4  
```  
  
##  <a name="size_type"></a>Array::size_type  
 İki öğe arasındaki imzasız bir uzaklığı türü.  
  
```  
typedef std::size_t size_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İşaretsiz tamsayı türünü herhangi denetimli sırası uzunluğu temsil eden bir nesne tanımlar. Türü için eş anlamlı olduğundan `std::size_t`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_size_type.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display distance last-first " 4"   
    Myarray::size_type diff = c0.end() - c0.begin();   
    std::cout << " " << diff;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4  
```  
  
##  <a name="swap"></a>Array::Swap  
Başka bir diziye sahip bu dizinin içeriğini değiştirir.  
  
```  
void swap(array& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 İçeriği ile değiştirilecek dizisi.  
  
### <a name="remarks"></a>Açıklamalar  
Üye işlevini denetimli sıraları arasında değiştirir `*this` ve `right`. Bir dizi öğesi atamaları gerçekleştirir ve oluşturucuyu çağırır orantılı `N`.  

Ayrıca olmayan üyesi olduğu [takas](array-functions.md#swap) işlevi takas iki kullanılabilir `array` örnekleri.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_swap.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1 = {4, 5, 6, 7};   
    c0.swap(c1);   
  
// display swapped contents " 4 5 6 7"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    swap(c0, c1);   
  
// display swapped contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4 5 6 7  
0 1 2 3  
```  
  
##  <a name="value_type"></a>Array::value_type  
 Öğenin türü.  
  
```  
typedef Ty value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür `Ty`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__array__array_value_type.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        {   
        Myarray::value_type val = *it;   
        std::cout << " " << val;   
        }   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<dizi >](../standard-library/array.md)

