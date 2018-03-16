---
title: "basic_string sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xstring/std::basic_string
- xstring/std::basic_string::allocator_type
- xstring/std::basic_string::const_iterator
- xstring/std::basic_string::const_pointer
- xstring/std::basic_string::const_reference
- xstring/std::basic_string::const_reverse_iterator
- xstring/std::basic_string::difference_type
- xstring/std::basic_string::iterator
- xstring/std::basic_string::npos
- xstring/std::basic_string::pointer
- xstring/std::basic_string::reference
- xstring/std::basic_string::reverse_iterator
- xstring/std::basic_string::size_type
- xstring/std::basic_string::traits_type
- xstring/std::basic_string::value_type
- xstring/std::basic_string::append
- xstring/std::basic_string::assign
- xstring/std::basic_string::at
- xstring/std::basic_string::back
- xstring/std::basic_string::begin
- xstring/std::basic_string::c_str
- xstring/std::basic_string::capacity
- xstring/std::basic_string::cbegin
- xstring/std::basic_string::cend
- xstring/std::basic_string::clear
- xstring/std::basic_string::compare
- xstring/std::basic_string::copy
- xstring/std::basic_string::crbegin
- xstring/std::basic_string::crend
- xstring/std::basic_string::_Copy_s
- xstring/std::basic_string::data
- xstring/std::basic_string::empty
- xstring/std::basic_string::end
- xstring/std::basic_string::erase
- xstring/std::basic_string::find
- xstring/std::basic_string::find_first_not_of
- xstring/std::basic_string::find_first_of
- xstring/std::basic_string::find_last_not_of
- xstring/std::basic_string::find_last_of
- xstring/std::basic_string::front
- xstring/std::basic_string::get_allocator
- xstring/std::basic_string::insert
- xstring/std::basic_string::length
- xstring/std::basic_string::max_size
- xstring/std::basic_string::pop_back
- xstring/std::basic_string::push_back
- xstring/std::basic_string::rbegin
- xstring/std::basic_string::rend
- xstring/std::basic_string::replace
- xstring/std::basic_string::reserve
- xstring/std::basic_string::resize
- xstring/std::basic_string::rfind
- xstring/std::basic_string::shrink_to_fit
- xstring/std::basic_string::size
- xstring/std::basic_string::substr
- xstring/std::basic_string::swap
dev_langs:
- C++
helpviewer_keywords:
- std::basic_string [C++]
- std::basic_string [C++], allocator_type
- std::basic_string [C++], const_iterator
- std::basic_string [C++], const_pointer
- std::basic_string [C++], const_reference
- std::basic_string [C++], const_reverse_iterator
- std::basic_string [C++], difference_type
- std::basic_string [C++], iterator
- std::basic_string [C++], npos
- std::basic_string [C++], pointer
- std::basic_string [C++], reference
- std::basic_string [C++], reverse_iterator
- std::basic_string [C++], size_type
- std::basic_string [C++], traits_type
- std::basic_string [C++], value_type
- std::basic_string [C++], append
- std::basic_string [C++], assign
- std::basic_string [C++], at
- std::basic_string [C++], back
- std::basic_string [C++], begin
- std::basic_string [C++], c_str
- std::basic_string [C++], capacity
- std::basic_string [C++], cbegin
- std::basic_string [C++], cend
- std::basic_string [C++], clear
- std::basic_string [C++], compare
- std::basic_string [C++], copy
- std::basic_string [C++], crbegin
- std::basic_string [C++], crend
- std::basic_string [C++], _Copy_s
- std::basic_string [C++], data
- std::basic_string [C++], empty
- std::basic_string [C++], end
- std::basic_string [C++], erase
- std::basic_string [C++], find
- std::basic_string [C++], find_first_not_of
- std::basic_string [C++], find_first_of
- std::basic_string [C++], find_last_not_of
- std::basic_string [C++], find_last_of
- std::basic_string [C++], front
- std::basic_string [C++], get_allocator
- std::basic_string [C++], insert
- std::basic_string [C++], length
- std::basic_string [C++], max_size
- std::basic_string [C++], pop_back
- std::basic_string [C++], push_back
- std::basic_string [C++], rbegin
- std::basic_string [C++], rend
- std::basic_string [C++], replace
- std::basic_string [C++], reserve
- std::basic_string [C++], resize
- std::basic_string [C++], rfind
- std::basic_string [C++], shrink_to_fit
- std::basic_string [C++], size
- std::basic_string [C++], substr
- std::basic_string [C++], swap
ms.assetid: a9c3e0a2-39bf-4c8a-b093-9abe30839591
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 895b0921785e29a49bd367c2676995ba9af8e309
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2018
---
# <a name="basicstring-class"></a>basic_string Sınıfı
Şablon sınıfın bir nesnesi tarafından denetlenen sıraları `basic_string` standart C++ string sınıfı ve bu genellikle için dize olarak adlandırılır, ancak bunlar C++ Standart Kitaplığı kullanılan null ile sonlandırılmış C tarzı dizeler ile karıştırılmamalıdır. Standart C++ dize karşılaştırma ve birleştirme işlemlerinin, yineleyiciler, C++ Standart Kitaplığı algoritmaları ve kopyalama gibi normal türü olarak dizelerinin kullanılmasını sağlayan bir kapsayıcıdır ve bellek yönetilen sınıf ayırıcısı ile atama. Standart C++ dize null ile sonlandırılmış C stili dizeye dönüştürmek istiyorsanız, kullanmak [basic_string::c_str](#c_str) üyesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>  
class basic_string;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `CharType`  
 Dizede depolanması için tek bir karakter veri türü. Bu şablon sınıfıyla tür tanımları özelleştirmeleri C++ Standart Kitaplığı sağlar [dize](../standard-library/string-typedefs.md#string) türündeki öğeler için `char`, [wstring](../standard-library/string-typedefs.md#wstring), için `wchar_t`, [u16string](../standard-library/string-typedefs.md#u16string) için `char16_t`, ve [u32string](../standard-library/string-typedefs.md#u32string) için `char32_t`.  
  
 `Traits`  
 Çeşitli önemli özelliklerini **CharType** basic_string uzmanlık öğelerinde sınıfı tarafından açıklanan **nitelikler**. Varsayılan değer `char_traits` <  `CharType`>.  
  
 `Allocator`  
 Dizesinin ayırma ve bellek ayırmayı kaldırma hakkında ayrıntılar yalıtan saklı ayırıcısı nesneyi temsil eden tür. Varsayılan değer **ayırıcısı**< `CharType`>.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[basic_string](#basic_string)|Boş veya özel karakterler veya diğer bir deyişle bir kopyası tüm veya bir bölümünü başka bir dize nesnesi tarafından başlatılmış veya C dize bir dize oluşturur.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|Temsil eden bir tür `allocator` bir dize nesnesi için sınıf.|  
|[const_iterator](#const_iterator)|Rasgele erişim yineleyici sağlayan bir tür erişim ve okuma bir `const` dize öğesi.|  
|[const_pointer](#const_pointer)|Bir işaretçi sağlayan bir türü bir `const` dize öğesi.|  
|[const_reference](#const_reference)|Bir başvuru sağlayan bir türü bir `const` okumak ve gerçekleştirmek için bir dize depolanan öğesi `const` işlemleri.|  
|[const_reverse_iterator](#const_reverse_iterator)|Herhangi bir rastgele erişim yineleyici bu can sağlayan bir türü okuma `const` dizesindeki öğesi.|  
|[difference_type](#difference_type)|Aynı dize içinde öğelerin başvurmak iki yineleyiciler arasındaki farkı sağlayan türü.|  
|[iterator](#iterator)|Rasgele erişim yineleyici sağlayan bir tür okuma veya bir dizede herhangi bir öğeyi değiştirin.|  
|[npos](#npos)|"Bulunamadı" ya da gösterir -1 veya "tüm geriye kalan karakterler" başlatılan bir işaretsiz tamsayı değer başarısız olduğunda bir arama işlevi.|  
|[pointer](#pointer)|Bir işaretçi bir dize veya karakter dizisi karakter öğesinde sağlayan türü.|  
|[reference](#reference)|Bir dizede depolanan bir öğe için bir başvuru sağlar türü.|  
|[reverse_iterator](#reverse_iterator)|Rasgele erişim yineleyici sağlayan bir tür okumak veya ters dizesindeki bir öğeyi değiştirin.|  
|[size_type](#size_type)|İmzasız tamsayı türü bir dize öğelerin sayısı.|  
|[traits_type](#traits_type)|Bir dizede depolanan öğelerin türü karakter özellikleri için.|  
|[value_type](#value_type)|Karakter dizesi içinde depolanan türünü temsil eden tür.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[append](#append)|Karakterleri bir dize sonuna ekler.|  
|[Ata](#assign)|Yeni karakter değeri bir dize içeriğini atar.|  
|[konumundaki](#at)|Belirtilen bir konumdaki öğeye başvuru dizeyi döndürür.|  
|[Geri](#back)||  
|[Başlangıç](#begin)|Dize ilk öğe adresleme yineleyici döndürür.|  
|[c_str](#c_str)|C türü, null ile sonlandırılmış, dize olarak bir dize içeriklerini dönüştürür.|  
|[capacity](#capacity)|Bir dizede dizesinin bellek ayırma artırmadan depolanabilir öğelerin en büyük sayıyı döndürür.|  
|[cbegin](#cbegin)|Dize ilk öğe adresleme const yineleyici döndürür.|  
|[cend](#cend)|Konumun bir dize son öğesi başarılı adresleri const bir yineleyici döndürür.|  
|[Temizle](#clear)|Bir dizenin tüm öğeleri siler.|  
|[Karşılaştırma](#compare)|İki dizeyi eşitse veya bir diğerinden lexicographically daha az olup olmadığını belirlemek için belirtilen bir dizeyi bir dizeyle karşılaştırır.|  
|[Kopyalama](#copy)|En fazla belirtilen sayıda karakteri bir kaynak dizesi dizinlenmiş bir konumda bir hedef karakter diziye kopyalar. Kullanım dışı. Kullanım [basic_string::_Copy_s](#copy_s) yerine.|  
|[crbegin](#crbegin)|Ters dize ilk öğe adresleri const bir yineleyici döndürür.|  
|[crend](#crend)|Ters dize son öğesi başarılı konumu adresleri const bir yineleyici döndürür.|  
|[_Copy_s](#copy_s)|En fazla belirtilen sayıda karakteri bir kaynak dizesi dizinlenmiş bir konumda bir hedef karakter diziye kopyalar.|  
|[Veri](#data)|Bir dize içeriğini karakterden oluşan bir diziye dönüştürür.|  
|[empty](#empty)|Karakter dizesini içeren olup olmadığını sınar.|  
|[Bitiş](#end)|Konumun bir dize son öğesi başarılı adresleri yineleyici döndürür.|  
|[silme](#erase)|Bir dizede belirtilen konumdan bir öğe veya öğe aralığını kaldırır.|  
|[find](#find)|Bir dizeyi belirtilen bir karakter dizisi eşleşen bir alt dizenin ilk a geçişi için ileriye doğru bir yönde arar.|  
|[find_first_not_of](#find_first_not_of)|Belirtilen dizenin herhangi bir öğe değil ilk karakter arasında bir dize arar.|  
|[find_first_of](#find_first_of)|Belirtilen dizenin herhangi bir öğe ile eşleşen ilk karakter arasında bir dize arar.|  
|[find_last_not_of](#find_last_not_of)|Belirtilen dizenin herhangi bir öğe değil son karakter arasında bir dize arar.|  
|[find_last_of](#find_last_of)|Belirtilen bir dizeyi bir öğenin son karakter arasında bir dize arar.|  
|[Ön](#front)|İlk öğe başvuru bir dize döndürür.|  
|[get_allocator](#get_allocator)|Bir kopyasını döndürür `allocator` dizesi oluşturmak için kullanılan nesne.|  
|[insert](#insert)|Bir öğenin veya öğe sayısı veya bir dizi öğeleri belirtilen bir konumda dize ekler.|  
|[uzunluğu](#length)|Öğelerin geçerli bir dize döndürür.|  
|[max_size](#max_size)|En fazla bir dize içermesi karakter sayısını döndürür.|  
|[pop_back](#pop_back)|Dizenin son öğe siler.|  
|[push_back](#push_back)|Bir öğeyi dize sonuna ekler.|  
|[rbegin](#rbegin)|Yineleyici ilk öğe ters bir dize döndürür.|  
|[rend](#rend)|Yineleyici yalnızca son öğenin ötesinde işaret içinde ters bir dize döndürür.|  
|[Değiştir](#replace)|Belirtilen veya diğer aralıkları veya dizeler veya C dizeleri kopyalanan karakter ile belirtilen konumda bir dizedeki öğeleri değiştirir.|  
|[reserve](#reserve)|Dize kapasitesini sayıyı en az olarak harika bir belirtilen sayı olarak ayarlar.|  
|[resize](#resize)|Bir dize ekleme veya silmeyi gerektiği gibi öğeleri için yeni bir boyutunu belirtir.|  
|[rfind](#rfind)|Bir dizeyi belirtilen bir karakter dizisi eşleşen bir alt dizenin ilk a geçişi için geriye dönük bir yönde arar.|  
|[shrink_to_fit](#shrink_to_fit)|Dizenin fazlalık kapasite atar.|  
|[Boyutu](#size)|Öğelerin geçerli bir dize döndürür.|  
|[substr](#substr)|Bir dizenin karakter sayısı en çok bazı belirtilen konuma dize baştan kopyalar.|  
|[Değiştirme](#swap)|İki dizeyi içeriğini exchange.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator+=](#op_add_eq)|Karakterleri dizeye ekler.|  
|[operator=](#op_eq)|Yeni karakter değeri bir dize içeriğini atar.|  
|[işleci&#91;&#93;](#op_at)|Belirtilen bir dizinden bir dizedeki karakter başvuru sağlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir işlev daha uzun bir sıra oluşturmak için sorular, [max_size](#max_size) öğeleri işlevi raporları uzunluğu hata türünde bir nesne atma tarafından [length_error](../standard-library/length-error-class.md).  
  
 Başvurular, işaretçiler ve denetlenen sıradaki tanımladığınız yineleyiciler dönüşebilir geçersiz herhangi denetimli dizisi olarak değiştiren bir işlev çağrısı olmayan bir ilk çağrıda sonra veya **const** üye işlevi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<dize >  
  
 **Namespace:** std  
  
##  <a name="allocator_type"></a>  basic_string::allocator_type  
 Allocator sınıfı bir dize nesnesi için temsil eden tür.  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **ayırıcısı**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_allocator_type.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   // The following lines declare objects  
   // that use the default allocator.  
   string s1;  
   basic_string <char>::allocator_type xchar = s1.get_allocator( );  
   // You can now call functions on the allocator class xchar used by s1  
}  
```  
  
##  <a name="append"></a>  basic_string::Append  
 Karakterleri bir dize sonuna ekler.  
  
```  
basic_string<CharType, Traits, Allocator>& append(
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& append(
    const value_type* ptr,  
    size_type count);

basic_string<CharType, Traits, Allocator>& append(
    const basic_string<CharType, Traits, Allocator>& str,  
    size_type _Off,  
    size_type count);

basic_string<CharType, Traits, Allocator>& append(
    const basic_string<CharType, Traits, Allocator>& str);

basic_string<CharType, Traits, Allocator>& append(
    size_type count,   
    value_type _Ch);

template <class InputIterator>  
basic_string<CharType, Traits, Allocator>& append(
    InputIterator first,   
    InputIterator last);

basic_string<CharType, Traits, Allocator>& append(
    const_pointer first,  
    const_pointer last);

basic_string<CharType, Traits, Allocator>& append(
    const_iterator first,  
    const_iterator last);
```  
  
### <a name="parameters"></a>Parametreler  
 `ptr`  
 C-eklenecek dize.  
  
 `str`  
 Karakterine eklenecek dize.  
  
 `_Off`  
 Eklenecek karakterleri sağladığını kaynak dizesi parçası dizini.  
  
 `count`  
 En fazla kaynak dizesi eklenecek karakter sayısı.  
  
 `_Ch`  
 Eklenecek karakter değeri.  
  
 `first`  
 Eklenecek aralık ilk öğe adresleme giriş yineleyici.  
  
 `last`  
 Bir giriş Yineleyici, const_pointer veya son öğesi dışındaki bir konum aralığında adresleme const_iterator eklenecek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üye işlevi tarafından geçirilen karakterlerle eklenen dize nesnesi referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 Karakter eklenmiş kullanarak bir dize [operator +=](#op_add_eq) veya üye işlevleri **sona** veya [push_back](#push_back). `operator+=` bağımsız değişken birden çok hatayla tek bağımsız değişkenli değerler ekler **sona** üye işlevini eklemek için belirtilmesi için bir dizeyi belirli bir kısmını sağlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_append.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // The first member function  
   // appending a C-string to a string  
   string str1a ( "Hello " );  
   cout << "The original string str1 is: " << str1a << endl;  
   const char *cstr1a = "Out There ";  
   cout << "The C-string cstr1a is: " << cstr1a << endl;  
   str1a.append ( cstr1a );  
   cout << "Appending the C-string cstr1a to string str1 gives: "   
        << str1a << "." << endl << endl;  
  
   // The second member function  
   // appending part of a C-string to a string  
   string str1b ( "Hello " );  
   cout << "The string str1b is: " << str1b << endl;  
   const char *cstr1b = "Out There ";  
   cout << "The C-string cstr1b is: " << cstr1b << endl;  
   str1b.append ( cstr1b , 3 );  
   cout << "Appending the 1st part of the C-string cstr1b "  
        << "to string str1 gives: " << str1b << "."   
        << endl << endl;  
  
   // The third member function  
   // appending part of one string to another  
   string str1c ( "Hello " ), str2c ( "Wide World " );  
   cout << "The string str2c is: " << str2c << endl;  
   str1c.append ( str2c , 5 , 5 );  
   cout << "The appended string str1 is: "   
        << str1c << "." << endl << endl;  
  
   // The fourth member function  
   // appending one string to another in two ways,  
   // comparing append and operator [ ]  
   string str1d ( "Hello " ), str2d ( "Wide " ), str3d ( "World " );  
   cout << "The  string str2d is: " << str2d << endl;  
   str1d.append ( str2d );  
   cout << "The appended string str1d is: "   
        << str1d << "." << endl;  
   str1d += str3d;  
   cout << "The doubly appended strig str1 is: "   
        << str1d << "." << endl << endl;  
  
   // The fifth member function  
   // appending characters to a string  
   string str1e ( "Hello " );  
   str1e.append ( 4 , '!' );  
   cout << "The string str1 appended with exclamations is: "   
        << str1e << endl << endl;  
  
   // The sixth member function  
   // appending a range of one string to another  
   string str1f ( "Hello " ), str2f ( "Wide World " );  
   cout << "The string str2f is: " << str2f << endl;  
   str1f.append ( str2f.begin ( ) + 5 , str2f.end ( ) - 1 );  
   cout << "The appended string str1 is: "   
        << str1f << "." << endl << endl;  
}  
```  
  
```Output  
The original string str1 is: Hello   
The C-string cstr1a is: Out There   
Appending the C-string cstr1a to string str1 gives: Hello Out There .  
  
The string str1b is: Hello   
The C-string cstr1b is: Out There   
Appending the 1st part of the C-string cstr1b to string str1 gives: Hello Out.  
  
The string str2c is: Wide World   
The appended string str1 is: Hello World.  
  
The  string str2d is: Wide   
The appended string str1d is: Hello Wide .  
The doubly appended strig str1 is: Hello Wide World .  
  
The string str1 appended with exclamations is: Hello !!!!  
  
The string str2f is: Wide World   
The appended string str1 is: Hello World.  
```  
  
##  <a name="assign"></a>  basic_string::Assign  
 Yeni karakter değeri bir dize içeriğini atar.  
  
```  
basic_string<CharType, Traits, Allocator>& assign(
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& assign(
    const value_type* ptr,  
    size_type count);

basic_string<CharType, Traits, Allocator>& assign(
    const basic_string<CharType, Traits, Allocator>& str,  
    size_type off,   
    size_type count);

basic_string<CharType, Traits, Allocator>& assign(
    const basic_string<CharType, Traits, Allocator>& str);

basic_string<CharType, Traits, Allocator>& assign(
    size_type count,   
    value_type _Ch);

template <class InIt>  
basic_string<CharType, Traits, Allocator>& assign(
    InputIterator first,   
    InputIterator last);

basic_string<CharType, Traits, Allocator>& assign(
    const_pointer first,  
    const_pointer last);

basic_string<CharType, Traits, Allocator>& assign(
    const_iterator first,  
    const_iterator last);
```  
  
### <a name="parameters"></a>Parametreler  
 `ptr`  
 Hedef dizeye atamayı C dize karakterlerini gösteren bir işaretçi.  
  
 `count`  
 En fazla kaynak dizesi eklenecek karakter sayısı.  
  
 `str`  
 Hedef dizeye atamayı karakterine olan kaynak dizesi.  
  
 `_Ch`  
 Atanacak karakter değeri.  
  
 `first`  
 Bir giriş Yineleyici, const_pointer veya kaynak dizesi aralığındaki ilk karakter adresleme const_iterator hedef aralığın atanacak.  
  
 `last`  
 Bir giriş Yineleyici, const_pointer veya son karakter aralığı dışındaki bir kaynak dizesi adresleme const_iterator hedef aralığın atanacak.  
  
 `off`  
 Atanacak yeni karakterler başlayacağı konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üye işlevi tarafından atanan yeni karakter dizesi nesneye başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizeleri yeni karakter değerleri atanabilir. Yeni değer bir dize ve C dize veya tek bir karakter olabilir. [İşleci =](#op_eq) yeni değer olabiliyorsa, tek bir parametre tarafından açıklanan; Aksi takdirde kullanılabilir üye fonksiyonu **atamak**, hangi dizesinin parçası olduğunu belirtmek amacıyla birden çok parametre olan kullanılabilir bir hedef dizeye atanamıyor.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_assign.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // The first member function assigning the  
   // characters of a C-string to a string  
   string str1a;  
   const char *cstr1a = "Out There";  
   cout << "The C-string cstr1a is: " << cstr1a <<  "." << endl;  
   str1a.assign ( cstr1a );  
   cout << "Assigning the C-string cstr1a to string str1 gives: "   
        << str1a << "." << endl << endl;  
  
   // The second member function assigning a specific  
   // number of the of characters a C-string to a string  
   string  str1b;  
   const char *cstr1b = "Out There";  
   cout << "The C-string cstr1b is: " << cstr1b << endl;  
   str1b.assign ( cstr1b , 3 );  
   cout << "Assigning the 1st part of the C-string cstr1b "  
        << "to string str1 gives: " << str1b << "."   
        << endl << endl;  
  
   // The third member function assigning a specific number  
   // of the characters from one string to another string   
   string str1c ( "Hello " ), str2c ( "Wide World " );  
   cout << "The string str2c is: " << str2c << endl;  
   str1c.assign ( str2c , 5 , 5 );  
   cout << "The newly assigned string str1 is: "   
        << str1c << "." << endl << endl;  
  
   // The fourth member function assigning the characters  
   // from one string to another string in two equivalent  
   // ways, comparing the assign and operator =  
   string str1d ( "Hello" ), str2d ( "Wide" ), str3d ( "World" );  
   cout << "The original string str1 is: " << str1d << "." << endl;  
   cout << "The string str2d is: " << str2d << endl;  
   str1d.assign ( str2d );  
   cout << "The string str1 newly assigned with string str2d is: "   
        << str1d << "." << endl;  
   cout << "The string str3d is: " << str3d << "." << endl;  
   str1d = str3d;  
   cout << "The string str1 reassigned with string str3d is: "   
        << str1d << "." << endl << endl;  
  
   // The fifth member function assigning a specific   
   // number of characters of a certain value to a string  
   string str1e ( "Hello " );  
   str1e.assign ( 4 , '!' );  
   cout << "The string str1 assigned with eclamations is: "   
        << str1e << endl << endl;  
  
   // The sixth member function assigning the value from  
   // the range of one string to another string  
   string str1f ( "Hello " ), str2f ( "Wide World " );  
   cout << "The string str2f is: " << str2f << endl;  
   str1f.assign ( str2f.begin ( ) + 5 , str2f.end ( ) - 1 );  
   cout << "The string str1 assigned a range of string str2f is: "   
        << str1f << "." << endl << endl;  
}  
```  
  
```Output  
The C-string cstr1a is: Out There.  
Assigning the C-string cstr1a to string str1 gives: Out There.  
  
The C-string cstr1b is: Out There  
Assigning the 1st part of the C-string cstr1b to string str1 gives: Out.  
  
The string str2c is: Wide World   
The newly assigned string str1 is: World.  
  
The original string str1 is: Hello.  
The string str2d is: Wide  
The string str1 newly assigned with string str2d is: Wide.  
The string str3d is: World.  
The string str1 reassigned with string str3d is: World.  
  
The string str1 assigned with eclamations is: !!!!  
  
The string str2f is: Wide World   
The string str1 assigned a range of string str2f is: World.  
```  
  
##  <a name="at"></a>  basic_string::at  
 Belirtilen bir dizinden bir dizedeki karakter başvuru sağlar.  
  
```  
const_reference at(size_type _Off) const;

 
reference at(size_type _Off);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Off`  
 Başvurulacak öğesinin konumu dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karakter dizesi parametresi dizini tarafından belirtilen konumdaki bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dizin sıfır dizenin ilk öğeye sahip olan ve aşağıdaki öğeleri art arda pozitif tamsayılar tarafından dizinlenen böylece bir dize uzunluğu *n* sahip bir *n*th öğesi dizine numarasınagöre*n -* 1.  
  
 Üye [işleci&#91; &#93; ](#op_at) üye işlevi hızlıdır **adresindeki** okuma ve yazma erişimi dizesinin öğelerine sağlamak için.  
  
 Üye `operator[]` parametre olarak geçirilen dizini geçerli olup, ancak üye fonksiyonu denetlemez **adresindeki** yapar ve bu nedenle kullanılmalıdır geçerlilik belirli değilse. Sıfır bir dizin daha az olan geçersiz bir dizin ya da sıfırdan büyük veya eşit üye işlevine geçirilen dize boyutu **adresindeki** oluşturur bir [out_of_range sınıfı](../standard-library/out-of-range-class.md) özel durum. Geçersiz dizin geçirilen `operator[]` sonuçlarında tanımsız davranışı, ancak dizini dize uzunluğu eşit const dizeleri için geçerli bir dizin ve işleci bu dizini geçirildiğinde null-karakteri döndürür.  
  
 Başvuru döndürülen geçersiz dize adetle sınırla veya ilgili olmayan değişiklikleri **const** dizeleri.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_at.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   string str1 ( "Hello world" ), str2 ( "Goodbye world" );  
   const string  cstr1 ( "Hello there" ), cstr2 ( "Goodbye now" );  
   cout << "The original string str1 is: " << str1 << endl;  
   cout << "The original string str2 is: " << str2 << endl;  
  
   // Element access to the non const strings  
   basic_string <char>::reference refStr1 = str1 [6];  
   basic_string <char>::reference refStr2 = str2.at ( 3 );  
  
   cout << "The character with an index of 6 in string str1 is: "  
        << refStr1 << "." << endl;  
   cout << "The character with an index of 3 in string str2 is: "  
        << refStr2 << "." << endl;  
  
   // Element access to the const strings  
   basic_string <char>::const_reference crefStr1 = cstr1 [ cstr1.length ( ) ];  
   basic_string <char>::const_reference crefStr2 = cstr2.at ( 8 );  
  
   if ( crefStr1 == '\0' )  
      cout << "The null character is returned as a valid reference."  
           << endl;  
   else  
      cout << "The null character is not returned." << endl;  
   cout << "The character with index 8 in the const string cstr2 is: "  
        << crefStr2 << "." << endl;  
}  
```  
  
##  <a name="back"></a>  basic_string::Back  
 Son öğeye başvuru dizeyi döndürür.  
  
```  
const_reference back() const;

 
reference back();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Son öğe boş olmalıdır dizesinin bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="basic_string"></a>  basic_string::basic_string  
 Bir belirli karakterler tarafından başlatılan boş olduğundan veya tüm kopyasını ya da başka bir dize nesnesi parçası veya C stili (boşluksuz) dize oluşturur.  
  
```  
basic_string();

explicit basic_string(
    const allocator_type& _Al);

basic_string(
    const basic_string& right);

basic_string(
    basic_string&& right);

basic_string(
    const basic_string& right,   
    size_type _Roff,  
    size_type count = npos);

basic_string(
    const basic_string& right,   
    size_type _Roff,  
    size_type count,   
    const allocator_type& _Al);

basic_string(
    const value_type* ptr,   
    size_type count);

basic_string(
    const value_type* ptr,   
    size_type count,  
    const allocator_type& _Al);

basic_string(
    const value_type* ptr);

basic_string(
    const value_type* ptr,  
    const allocator_type& _Al);

basic_string(
    size_type count,   
    value_type _Ch);

basic_string(
    size_type count,   
    value_type _Ch,  
    const allocator_type& _Al);

template <class InputIterator>  
basic_string(
 InputIterator first,   
    InputIterator last);

template <class InputIterator>  
basic_string(
 InputIterator first,   
    InputIterator last,   
    const allocator_type& _Al);

basic_string(
    const_pointer first,  
    const_pointer last);

basic_string(
    const_iterator first,  
    const_iterator last);
```  
  
### <a name="parameters"></a>Parametreler  
 `ptr`  
 C-karakterine başlatmak için kullanılacak dize `string` oluşturulamıyor. Bu değer null işaretçi olamaz.  
  
 `_Al`  
 Depolama allocator sınıfı için yapılandırılan bir dize nesnesi.  
  
 `count`  
 Başlatılması için karakter sayısı.  
  
 `right`  
 Yapılandırılan bir dizesini başlatır dize.  
  
 `_Roff`  
 İlk karakter değerleri için yapılandırılan bir dize başlatmak için kullanılan bir dizeye karakter dizini.  
  
 `_Ch`  
 Yapılandırılan bir dizeye kopyalanacak karakter değeri.  
  
 `first`  
 Bir giriş Yineleyici, const_pointer veya kaynak aralığındaki ilk öğe adresleme const_iterator eklenecek.  
  
 `last`  
 Bir giriş Yineleyici, const_pointer veya kaynak aralığı son öğenin ötesinde bir konumda adresleme const_iterator eklenecek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Oluşturucular tarafından oluşturulan dize nesnesi referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm oluşturucular depolamak bir [basic_string::allocator_type](#allocator_type) ve denetlenen sırası başlatılamıyor. Bağımsız değişken ayırıcısı nesnesidir `al`, varsa. Kopya Oluşturucu için olmasından `right.` [basic_string::get_allocator](#get_allocator)`()`. Aksi takdirde, değer `Alloc()`.  
  
 Denetimli dizisi kalan işlenen tarafından belirtilen işleneni sırası kopyasına başlatılır. Bir oluşturucu işleneni dizisi olmadan boş bir ilk denetlenen sırasını belirtir. Varsa `InputIterator` işlenen dizisi _F bir şablon kurucusunda bir tamsayı türü `irst,  last` aynı şekilde davranır `(size_type) first, (value_type) last`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_ctor.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // The first member function initializing with a C-string  
   const char *cstr1a = "Hello Out There.";  
   basic_string <char> str1a ( cstr1a , 5);  
   cout << "The string initialized by C-string cstr1a is: "  
        << str1a << "." << endl;  
  
   // The second member function initializing with a string  
   string  str2a ( "How Do You Do" );  
   basic_string <char> str2b ( str2a , 7 , 7 );  
   cout << "The string initialized by part of the string cstr2a is: "  
        << str2b << "." << endl;  
  
   // The third member function initializing a string  
   // with a number of characters of a specific value  
   basic_string <char> str3a ( 5, '9' );  
   cout << "The string initialized by five number 9s is: "  
        << str3a << endl;  
  
   // The fourth member function creates an empty string  
   // and string with a specified allocator  
   basic_string <char> str4a;  
   string str4b;  
   basic_string <char> str4c ( str4b.get_allocator( ) );  
   if (str4c.empty ( ) )  
      cout << "The string str4c is empty." << endl;  
   else  
      cout << "The string str4c is not empty." << endl;  
  
   // The fifth member function initializes a string from  
   // another range of characters  
   string str5a ( "Hello World" );  
   basic_string <char> str5b ( str5a.begin ( ) + 5 , str5a.end ( ) );  
   cout << "The string initialized by another range is: "  
        << str5b << "." << endl;  
}  
```  
  
##  <a name="begin"></a>  basic_string::Begin  
 Dize ilk öğe adresleme yineleyici döndürür.  
  
```  
const_iterator begin() const;

 
iterator begin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk öğe dizisi veya yalnızca boş bir dizi ötesinde adresleri rasgele erişim yineleyici.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_begin.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( ) {  
   using namespace std;  
   string str1 ( "No way out." ), str2;  
   basic_string <char>::iterator strp_Iter, str1_Iter, str2_Iter;  
   basic_string <char>::const_iterator str1_cIter;  
  
   str1_Iter = str1.begin ( );  
   cout << "The first character of the string str1 is: "   
        << *str1_Iter << endl;  
   cout << "The full original string str1 is: " << str1 << endl;  
  
   // The dereferenced iterator can be used to modify a character  
 *str1_Iter = 'G';  
   cout << "The first character of the modified str1 is now: "   
        << *str1_Iter << endl;  
   cout << "The full modified string str1 is now: " << str1 << endl;  
  
   // The following line would be an error because iterator is const  
   // *str1_cIter = 'g';  
  
   // For an empty string, begin is equivalent to end  
   if (  str2.begin ( ) == str2.end ( ) )  
      cout << "The string str2 is empty." << endl;  
   else  
      cout << "The string str2 is not empty." << endl;  
}  
```  
  
##  <a name="c_str"></a>  basic_string::c_str  
 Bir C-stil olarak bir dize içeriklerini dönüştürür null ile sonlandırılmış dize.  
  
```  
const value_type *c_str() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çağıran dize C tarzı sürümü için bir işaretçi.  Basic_string sınıfı nesnesindeki yıkıcı dahil olmak üzere bir const olmayan işlevi çağırdıktan sonra özelliği işaretçi değeri geçerli değil.  
  
### <a name="remarks"></a>Açıklamalar  
 C++ Şablon sınıfı basic_string ait dize türünde nesneleri\<char > olan mutlaka null sonlandırıldı. Null karakteri '\0' C dizesindeki bir özel karakter olarak dize sonu işaretlemek için kullanılır, ancak dize türünde bir nesne özel bir anlamı yoktur ve gibi başka bir karakter dizesi parçası olabilir. Const otomatik bir dönüştürme **char\***  sınıfı türündeki nesneler için C tarzı dizelerden otomatik dönüştürmeleri için sağlamaz dizeler, ancak dize **basic_string\< char >**.  
  
 Bu dize işaretçisine geçersiz kılmak veya dize sınırlı bir ömrü vardır ve sınıf dizesi tarafından sahip olunan silinmiş döndürülen C stili dize değiştirilmemelidir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_c_str.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   string  str1 ( "Hello world" );  
   cout << "The original string object str1 is: "   
        << str1 << endl;  
   cout << "The length of the string object str1 = "   
        << str1.length ( ) << endl << endl;  
  
   // Converting a string to an array of characters  
   const char *ptr1 = 0;  
   ptr1= str1.data ( );  
   cout << "The modified string object ptr1 is: " << ptr1   
        << endl;  
   cout << "The length of character array str1 = "   
        << strlen ( ptr1) << endl << endl;  
  
   // Converting a string to a C-style string  
   const char *c_str1 = str1.c_str ( );  
   cout << "The C-style string c_str1 is: " << c_str1   
        << endl;  
   cout << "The length of C-style string str1 = "   
        << strlen ( c_str1) << endl << endl;  
}  
```  
  
```Output  
The original string object str1 is: Hello world  
The length of the string object str1 = 11  
  
The modified string object ptr1 is: Hello world  
The length of character array str1 = 11  
  
The C-style string c_str1 is: Hello world  
The length of C-style string str1 = 11  
```  
  
##  <a name="capacity"></a>  basic_string::Capacity  
 Bir dizede dizesinin bellek ayırma artırmadan depolanabilir öğelerin en büyük sayıyı döndürür.  
  
```  
size_type capacity() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda bellek dize tutmak için ayrılmış depolama boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi şu anda denetlenen sırası, en az kadar büyük bir değer tutmak için ayrılan depolama alanı döndürür [boyutu](#size).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_capacity.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   string  str1 ("Hello world");  
   cout << "The original string str1 is: " << str1 << endl;  
  
   // The size and length member functions differ in name only  
   basic_string <char>::size_type sizeStr1, lenStr1;  
   sizeStr1 = str1.size ( );  
   lenStr1 = str1.length ( );  
  
   basic_string <char>::size_type capStr1, max_sizeStr1;  
   capStr1 = str1.capacity ( );  
   max_sizeStr1 = str1.max_size ( );  
  
   // Compare size, length, capacity & max_size of a string  
   cout << "The current size of original string str1 is: "   
        << sizeStr1 << "." << endl;  
   cout << "The current length of original string str1 is: "   
        << lenStr1 << "." << endl;  
   cout << "The capacity of original string str1 is: "  
        << capStr1 << "." << endl;  
   cout << "The max_size of original string str1 is: "   
        << max_sizeStr1 << "." << endl << endl;  
  
   str1.erase ( 6, 5 );  
   cout << "The modified string str1 is: " << str1 << endl;  
  
   sizeStr1 = str1.size (  );  
   lenStr1 = str1.length (  );  
   capStr1 = str1.capacity (  );  
   max_sizeStr1 = str1.max_size (  );  
  
   // Compare size, length, capacity & max_size of a string  
   // after erasing part of the original string  
   cout << "The current size of modified string str1 is: "   
        << sizeStr1 << "." << endl;  
   cout << "The current length of modified string str1 is: "   
        << lenStr1 << "." << endl;  
   cout << "The capacity of modified string str1 is: "  
        << capStr1 << "." << endl;  
   cout << "The max_size of modified string str1 is: "   
        << max_sizeStr1 << "." << endl;  
}  
```  
  
##  <a name="cbegin"></a>  basic_string::cbegin  
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
  
##  <a name="cend"></a>  basic_string::cend  
 Döndürür bir `const` konumun yalnızca bir aralıkta son öğenin ötesinde adresleri yineleyici.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `const` yalnızca aralığın sonunu aşan işaret rasgele erişim yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 `cend` Yineleyici kendi aralığının sonunu geçti olup olmadığını test etmek için kullanılır.  
  
 Bu üye işlevi yerine kullanabileceğiniz `end()` üye işlevi dönüş değeri garanti `const_iterator`. Genellikle, ile birlikte kullanılır [otomatik](../cpp/auto-cpp.md) kesintisi anahtar sözcüğü, aşağıdaki örnekte gösterildiği gibi yazın. Örnekte, göz önünde bulundurun `Container` bir değiştirilebilir için (olmayan `const`) destekleyen herhangi bir türde kapsayıcı `end()` ve `cend()`.  
  
```cpp  
auto i1 = Container.end();
// i1 is Container<T>::iterator   
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator  
```  
  
 Tarafından döndürülen değer `cend` değil başvuru yapıldı.  
  
##  <a name="clear"></a>  basic_string::Clear  
 Bir dizenin tüm öğeleri siler.  
  
```  
void clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini çağırıldığı dize boş olacaktır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_clear.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   string  str1 ("Hello world"), str2;  
   basic_string <char>::iterator str_Iter;  
   cout << "The original string str1 is: ";  
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )  
      cout << *str_Iter;  
   cout << endl;  
  
   str1.clear ( );  
   cout << "The modified string str1 is: ";  
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )  
      cout << *str_Iter;  
   cout << endl;  
  
   //For an empty string, begin is equivalent to end  
   if ( str1.begin ( ) == str1.end ( ) )  
      cout << "Nothing printed above because "  
           << "the string str1 is empty." << endl;  
   else  
      cout << "The string str1 is not empty." << endl;  
}  
```  
  
```Output  
The original string str1 is: Hello world  
The modified string str1 is:   
Nothing printed above because the string str1 is empty.  
```  
  
##  <a name="compare"></a>  basic_string::compare  
 İki dizeyi eşitse veya bir diğerinden lexicographically daha az olup olmadığını belirlemek için belirtilen dize ile büyük küçük harfe duyarlı karşılaştırma gerçekleştirir.  
  
```  
int compare(
    const basic_string<CharType, Traits, Allocator>& str) const;

 
int compare(
    size_type _Pos1,   
    size_type _Num1,  
    const basic_string<CharType, Traits, Allocator>& str) const;

 
int compare(
    size_type _Pos1,  
    size_type _Num1,  
    const basic_string<CharType, Traits, Allocator>& str,   
    size_type _Off,   
    size_type count) const;

 
int compare(
    const value_type* ptr) const;

 
int compare(
    size_type _Pos1,  
    size_type _Num1,  
    const value_type* ptr) const;

 
int compare(
    size_type _Pos1,  
    size_type _Num1,  
    const value_type* ptr  
    size_type _Num2) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `str`  
 İşlenen dizeye karşılaştırılacak olan dize.  
  
 `_Pos1`  
 Hangi karşılaştırma başlar işleneni dize dizini.  
  
 `_Num1`  
 Karşılaştırılacak işleneni dizeden karakterleri maksimum sayısı.  
  
 `_Num2`  
 Karşılaştırılacak parametre dizeden karakterleri maksimum sayısı.  
  
 `_Off`  
 Hangi karşılaştırma başlar parametre dizesi dizini.  
  
 `count`  
 Karşılaştırılacak parametre dizeden karakterleri maksimum sayısı.  
  
 `ptr`  
 C-işlenen dizeye Karşılaştırılacak dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlenen dize parametre dizesini küçükse negatif bir değer; iki dizeyi eşitse sıfır; veya işlenen dize parametresi dize büyükse, pozitif bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 **Karşılaştırmak** üye işlevlerini karşılaştırmak tüm veya parametre ve işlenen dizelerde seçtiğinize bağlı olarak kullanılan bir parçası.  
  
 Gerçekleştirilen karşılaştırma büyük/küçük harfe duyarlıdır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_compare.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // The first member function compares  
   // an operand string to a parameter string  
   int comp1;  
   string s1o ( "CAB" );  
   string s1p ( "CAB" );  
   cout << "The operand string is: " << s1o << endl;  
   cout << "The parameter string is: " << s1p << endl;  
   comp1 = s1o.compare ( s1p );  
   if ( comp1 < 0 )  
      cout << "The operand string is less than "  
           << "the parameter string." << endl;  
   else if ( comp1 == 0 )  
      cout << "The operand string is equal to "  
           << "the parameter string." << endl;  
   else  
      cout << "The operand string is greater than "  
           << "the parameter string." << endl;  
   cout << endl;  
  
   // The second member function compares part of  
   // an operand string to a parameter string  
   int comp2a, comp2b;  
   string s2o ( "AACAB" );  
   string s2p ( "CAB" );  
   cout << "The operand string is: " << s2o << endl;  
   cout << "The parameter string is: " << s2p << endl;  
   comp2a = s2o.compare (  2 , 3 , s2p );  
   if ( comp2a < 0 )  
      cout << "The last three characters of "  
           << "the operand string\n are less than "  
           << "the parameter string." << endl;  
   else if ( comp2a == 0 )  
      cout << "The last three characters of "  
           << "the operand string\n are equal to "  
           << "the parameter string." << endl;  
   else  
      cout << "The last three characters of "  
           << "the operand string\n is greater than "  
           << "the parameter string." << endl;  
  
   comp2b = s2o.compare (  0 , 3 , s2p );  
   if ( comp2b < 0 )  
      cout << "The first three characters of "  
           << "the operand string\n are less than "  
           << "the parameter string." << endl;  
   else if ( comp2b == 0 )  
      cout << "The first three characters of "  
           << "the operand string\n are equal to "  
           << "the parameter string." << endl;  
   else  
      cout << "The first three characters of "  
           << "the operand string\n is greater than "  
           << "the parameter string." << endl;  
   cout << endl;  
  
   // The third member function compares part of  
   // an operand string to part of a parameter string  
   int comp3a;  
   string s3o ( "AACAB" );  
   string s3p ( "DCABD" );  
   cout << "The operand string is: " << s3o << endl;  
   cout << "The parameter string is: " << s3p << endl;  
   comp3a = s3o.compare (  2 , 3 , s3p , 1 , 3 );  
   if ( comp3a < 0 )  
      cout << "The three characters from position 2 of "  
           << "the operand string are less than\n "  
           << "the 3 characters parameter string "   
           << "from position 1." << endl;  
   else if ( comp3a == 0 )  
      cout << "The three characters from position 2 of "  
           << "the operand string are equal to\n "  
           << "the 3 characters parameter string "   
           << "from position 1." << endl;  
   else  
      cout << "The three characters from position 2 of "  
           << "the operand string is greater than\n "  
           << "the 3 characters parameter string "   
           << "from position 1." << endl;  
   cout << endl;  
  
   // The fourth member function compares  
   // an operand string to a parameter C-string  
   int comp4a;  
   string s4o ( "ABC" );  
   const char* cs4p = "DEF";  
   cout << "The operand string is: " << s4o << endl;  
   cout << "The parameter C-string is: " << cs4p << endl;  
   comp4a = s4o.compare ( cs4p );  
   if ( comp4a < 0 )  
      cout << "The operand string is less than "  
           << "the parameter C-string." << endl;  
   else if ( comp4a == 0 )  
      cout << "The operand string is equal to "  
           << "the parameter C-string." << endl;  
   else  
      cout << "The operand string is greater than "  
           << "the parameter C-string." << endl;  
   cout << endl;  
  
   // The fifth member function compares part of  
   // an operand string to a parameter C-string  
   int comp5a;  
   string s5o ( "AACAB" );  
   const char* cs5p = "CAB";  
   cout << "The operand string is: " << s5o << endl;  
   cout << "The parameter string is: " << cs5p << endl;  
   comp5a = s5o.compare (  2 , 3 , s2p );  
   if ( comp5a < 0 )  
      cout << "The last three characters of "  
           << "the operand string\n are less than "  
           << "the parameter C-string." << endl;  
   else if ( comp5a == 0 )  
      cout << "The last three characters of "  
           << "the operand string\n are equal to "  
           << "the parameter C-string." << endl;  
   else  
      cout << "The last three characters of "  
           << "the operand string\n is greater than "  
           << "the parameter C-string." << endl;  
   cout << endl;  
  
   // The sixth member function compares part of  
   // an operand string to part of an equal length of  
   // a parameter C-string  
   int comp6a;  
   string s6o ( "AACAB" );  
   const char* cs6p = "ACAB";  
   cout << "The operand string is: " << s6o << endl;  
   cout << "The parameter C-string is: " << cs6p << endl;  
   comp6a = s6o.compare (  1 , 3 , cs6p , 3 );  
   if ( comp6a < 0 )  
      cout << "The 3 characters from position 1 of "  
           << "the operand string are less than\n "  
           << "the first 3 characters of the parameter C-string."   
           << endl;  
   else if ( comp6a == 0 )  
      cout << "The 3 characters from position 2 of "  
           << "the operand string are equal to\n "  
           << "the first 3 characters of the parameter C-string."   
           <<  endl;  
   else  
      cout << "The 3 characters from position 2 of "  
           << "the operand string is greater than\n "  
           << "the first 3 characters of the parameter C-string."   
           << endl;  
   cout << endl;  
}  
```  
  
```Output  
The operand string is: CAB  
The parameter string is: CAB  
The operand string is equal to the parameter string.  
  
The operand string is: AACAB  
The parameter string is: CAB  
The last three characters of the operand string  
 are equal to the parameter string.  
The first three characters of the operand string  
 are less than the parameter string.  
  
The operand string is: AACAB  
The parameter string is: DCABD  
The three characters from position 2 of the operand string are equal to  
 the 3 characters parameter string from position 1.  
  
The operand string is: ABC  
The parameter C-string is: DEF  
The operand string is less than the parameter C-string.  
  
The operand string is: AACAB  
The parameter string is: CAB  
The last three characters of the operand string  
 are equal to the parameter C-string.  
  
The operand string is: AACAB  
The parameter C-string is: ACAB  
The 3 characters from position 2 of the operand string are equal to  
 the first 3 characters of the parameter C-string.  
```  
  
##  <a name="const_iterator"></a>  basic_string::const_iterator  
 Rasgele erişim yineleyici sağlayan bir tür erişim ve okuma bir **const** dizesindeki öğesi.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_iterator` bir karakterin değerini değiştirmek için kullanılamaz ve bir iletme yön dizesinde yinelemek için kullanılır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [başlamak](#begin) bildirme ve kullanma konusunda bir örnek için `const_iterator`.  
  
##  <a name="const_pointer"></a>  basic_string::const_pointer  
 Bir işaretçi sağlayan bir türü bir **const** dize öğesi.  
  
```  
typedef typename allocator_type::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türüdür **allocator_type::const_pointer**.  
  
 Türü için **dize**, eşdeğer olan `char`*.  
  
 Bunlar bildirirken const bildirilir işaretçileri başlatılması gerekir. Const işaretçileri her zaman aynı bellek konumuna işaret ve sabit veya nonconstant veri noktası.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_const_ptr.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   basic_string<char>::const_pointer pstr1a = "In Here";  
   const char *cstr1c = "Out There";  
  
   cout << "The string pstr1a is: " << pstr1a <<  "." << endl;  
   cout << "The C-string cstr1c is: " << cstr1c << "." << endl;  
}  
```  
  
```Output  
The string pstr1a is: In Here.  
The C-string cstr1c is: Out There.  
```  
  
##  <a name="const_reference"></a>  basic_string::const_reference  
 Bir başvuru sağlayan bir türü bir **const** okumak ve gerçekleştirmek için bir dize depolanan öğesi **const** işlemleri.  
  
```  
typedef typename allocator_type::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_reference` bir öğenin değerini değiştirmek için kullanılamaz.  
  
 Eşanlamlısı türüdür **allocator_type::const_reference**. Dize **türü**, const için eşdeğer olan **char &**.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [adresindeki](#at) bildirme ve kullanma konusunda bir örnek için `const_reference`.  
  
##  <a name="const_reverse_iterator"></a>  basic_string::const_reverse_iterator  
 Herhangi bir rastgele erişim yineleyici bu can sağlayan bir türü okuma **const** dizesindeki öğesi.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `const_reverse_iterator` bir karakterin değerini değiştiremez ve ters dizesinde yinelemek için kullanılır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [rbegin](#rbegin) bildirme ve kullanma konusunda bir örnek için `const_reverse_iterator`.  
  
##  <a name="copy"></a>  basic_string::Copy  
 En fazla belirtilen sayıda karakteri bir kaynak dizesi dizinlenmiş bir konumda bir hedef karakter diziye kopyalar.  
  
 Geçirilen değerlerin doğru olduğunu kontrol etmek için arayan alacağından bu büyük olasılıkla güvensiz bir yöntemdir. Kullanmayı [basic_string::_Copy_s](#copy_s) yerine.  
  
```  
size_type copy(
    value_type* ptr,   
    size_type count,  
    size_type _Off = 0) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `ptr`  
 Öğeleri kopyalanacak olan hedef karakter dizisi.  
  
 _ `Count`  
 En fazla kaynak dizesi kopyalanacak karakter sayısı.  
  
 `_Off`  
 Kopyalarıdır yapılması kaynak dizesi başlangıç konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gerçekte kopyalanan karakter sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir null karakter kopyalama sonuna eklenmez.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_copy.cpp  
// compile with: /EHsc /W3  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   string str1 ( "Hello World" );  
   basic_string <char>::iterator str_Iter;  
   char array1 [ 20 ] = { 0 };  
   char array2 [ 10 ] = { 0 };  
   basic_string <char>:: pointer array1Ptr = array1;  
   basic_string <char>:: value_type *array2Ptr = array2;  
  
   cout << "The original string str1 is: ";  
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )  
      cout << *str_Iter;  
   cout << endl;  
  
   basic_string <char>:: size_type nArray1;  
   // Note: string::copy is potentially unsafe, consider  
   // using string::_Copy_s instead.  
   nArray1 = str1.copy ( array1Ptr , 12 );  // C4996  
   cout << "The number of copied characters in array1 is: "  
        << nArray1 << endl;  
   cout << "The copied characters array1 is: " << array1 << endl;  
  
   basic_string <char>:: size_type nArray2;  
   // Note: string::copy is potentially unsafe, consider  
   // using string::_Copy_s instead.  
   nArray2 = str1.copy ( array2Ptr , 5 , 6  );  // C4996  
   cout << "The number of copied characters in array2 is: "  
           << nArray2 << endl;  
   cout << "The copied characters array2 is: " << array2Ptr << endl;  
}  
```  
  
```Output  
The original string str1 is: Hello World  
The number of copied characters in array1 is: 11  
The copied characters array1 is: Hello World  
The number of copied characters in array2 is: 5  
The copied characters array2 is: World  
```  
  
##  <a name="crbegin"></a>  basic_string::crbegin  
 Ters dize ilk öğe adresleri const bir yineleyici döndürür.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yalnızca dize sonunu aşan işaret ters yineleyici. Ters dizesinin başlangıç konumunu belirler.  
  
##  <a name="crend"></a>  basic_string::crend  
 Ters dize son öğesi başarılı konumu adresleri const bir yineleyici döndürür.  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir const ters bir dize (ilk öğe unreversed dizesinde öncesinde konum) son öğesi başarılı konumu adresleri yineleyici ters çevrilir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="copy_s"></a>  basic_string::_Copy_s  
 En fazla belirtilen sayıda karakteri bir kaynak dizesi dizinlenmiş bir konumda bir hedef karakter diziye kopyalar.  
  
```  
size_type _Copy_s(
    value_type* dest,  
    size_type dest_size,  
    size_type count,  
    size_type _Off = 0) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `dest`  
 Öğeleri kopyalanacak olan hedef karakter dizisi.  
  
 `dest_size`  
 Boyutunu `dest`.  
  
 _ `Count`  
 En fazla kaynak dizesi kopyalanacak karakter sayısı.  
  
 `_Off`  
 Kopyalarıdır yapılması kaynak dizesi başlangıç konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gerçekte kopyalanan karakter sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir null karakter kopyalama sonuna eklenmez.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string__Copy_s.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
    using namespace std;  
    string str1("Hello World");  
    basic_string<char>::iterator str_Iter;  
    const int array1_size = 20;  
    char array1[array1_size] = { 0 };  
    const int array2_size = 10;  
    char array2[array2_size] = { 0 };  
    basic_string<char>:: pointer array1Ptr = array1;  
    basic_string<char>:: value_type *array2Ptr = array2;  
  
    cout << "The original string str1 is: ";  
    for (str_Iter = str1.begin(); str_Iter != str1.end(); str_Iter++)  
        cout << *str_Iter;  
    cout << endl;  
  
    basic_string<char>::size_type nArray1;  
    nArray1 = str1._Copy_s(array1Ptr, array1_size, 12);  
    cout << "The number of copied characters in array1 is: "  
         << nArray1 << endl;  
    cout << "The copied characters array1 is: " << array1 << endl;  
  
    basic_string<char>:: size_type nArray2;  
    nArray2 = str1._Copy_s(array2Ptr, array2_size, 5, 6);  
    cout << "The number of copied characters in array2 is: "  
         << nArray2 << endl;  
    cout << "The copied characters array2 is: " << array2Ptr << endl;  
}  
```  
  
```Output  
The original string str1 is: Hello World  
The number of copied characters in array1 is: 11  
The copied characters array1 is: Hello World  
The number of copied characters in array2 is: 5  
The copied characters array2 is: World  
```  
  
##  <a name="data"></a>  basic_string::Data  
 Bir dize içeriğini karakterden oluşan bir diziye dönüştürür.  
  
```  
const value_type *data() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizenin mı, yoksa boş bir dizi çözülemiyor bir null olmayan işaretçi içeriği içeren dizisinin ilk öğesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 C++ Şablon sınıfı basic_string ait dize türünde nesneleri \<char > olan mutlaka null sonlandırıldı. Dönüş türü için **veri** hiçbir null karakter eklenmiş çünkü geçerli C-dizesi, değil. Null karakteri '\0' C dizesindeki bir özel karakter olarak dize sonu işaretlemek için kullanılır, ancak dize türünde bir nesne özel bir anlamı yoktur ve gibi başka bir karakter dizesi nesnesinin bir parçası olabilir.  
  
 Const otomatik bir dönüştürme **char\***  sınıfı türündeki nesneler için C tarzı dizelerden otomatik dönüştürmeleri için sağlamaz dizeler, ancak dize **basic_string \< char >**.  
  
 Bu dize işaretçisine geçersiz kılmak veya dize sınırlı bir ömrü vardır ve sınıf dizesiyle ait olduğundan, silinmiş olduğundan döndürülen dize değiştirilmemelidir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_data.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   string str1 ( "Hello world" );  
   cout << "The original string object str1 is: "   
        << str1 << endl;  
   cout << "The length of the string object str1 = "   
        << str1.length ( ) << endl << endl;  
  
   // Converting a string to an array of characters  
   const char *ptr1 = 0;  
   ptr1= str1.data ( );  
   cout << "The modified string object ptr1 is: " << ptr1   
        << endl;  
   cout << "The length of character array str1 = "   
        << strlen ( ptr1) << endl << endl;  
  
   // Converting a string to a C-style string  
   const char *c_str1 = str1.c_str ( );  
   cout << "The C-style string c_str1 is: " << c_str1   
        << endl;  
   cout << "The length of C-style string str1 = "   
        << strlen ( c_str1) << endl << endl;  
}  
```  
  
```Output  
The original string object str1 is: Hello world  
The length of the string object str1 = 11  
  
The modified string object ptr1 is: Hello world  
The length of character array str1 = 11  
  
The C-style string c_str1 is: Hello world  
The length of C-style string str1 = 11  
```  
  
##  <a name="difference_type"></a>  basic_string::difference_type  
 Aynı dize içinde öğelerin başvurmak iki yineleyiciler arasındaki farkı sağlayan türü.  
  
```  
typedef typename allocator_type::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İmzalı tamsayı türünü herhangi iki öğe denetlenen sıradaki adreslerini arasındaki farkı temsil eden bir nesne tanımlar.  
  
 Türü için **dize**, eşdeğer olan **ptrdiff_t**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_diff_type.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   string str1 ( "quintillion" );  
   cout << "The original string str1 is: " << str1 << endl;  
   basic_string <char>::size_type indexChFi, indexChLi;  
  
   indexChFi = str1.find_first_of ( "i" );  
   indexChLi = str1.find_last_of ( "i" );  
   basic_string<char>::difference_type diffi = indexChLi - indexChFi;  
  
   cout << "The first character i is at position: "  
        << indexChFi << "." << endl;  
   cout << "The last character i is at position: "  
        << indexChLi << "." << endl;  
   cout << "The difference is: " << diffi << "." << endl;  
}  
```  
  
```Output  
The original string str1 is: quintillion  
The first character i is at position: 2.  
The last character i is at position: 8.  
The difference is: 6.  
```  
  
##  <a name="empty"></a>  basic_string::empty  
 Dize veya olmayan karakterler içeriyor olup olmadığını sınar.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** dize nesnesi hiçbir karakter; içeriyorsa **false** en az bir karakter varsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini eşdeğerdir [boyutu](#size) == 0.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_empty.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main() {  
   using namespace std;  
  
   bool b1, b2;  
  
   string str1 ("Hello world");  
   cout << "The original string object str1 is: " << str1 << endl;  
   b1 = str1.empty();  
   if (b1)  
      cout << "The string object str1 is empty." << endl;  
   else  
      cout << "The string object str1 is not empty." << endl;  
   cout << endl;  
  
   // An example of an empty string object  
   string str2;  
   b2 = str2.empty();  
   if (b2)  
      cout << "The string object str2 is empty." << endl;  
   else  
      cout << "The string object str2 is not empty." << endl;  
}  
```  
  
##  <a name="end"></a>  basic_string::End  
 Konumun bir dize son öğesi başarılı adresleri yineleyici döndürür.  
  
```  
const_iterator end() const;

 
iterator end();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Konumun bir dize son öğesi başarılı adresleri rasgele erişim yineleyici döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 **Son** çoğunlukla yineleyici alt dizenin sonuna ulaştı olup olmadığını test etmek için kullanılır. Tarafından döndürülen değer **son** değil başvuru yapıldı.  
  
 Varsa dönüş değerini **son** atanmış bir `const_iterator`, dize nesnesi değiştirilemez. Varsa dönüş değerini **son** atanmış bir **yineleyici**, dize nesnesi değiştirilebilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_end.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   string str1 ( "No way out." ), str2;  
   basic_string <char>::iterator str_Iter, str1_Iter, str2_Iter;  
   basic_string <char>::const_iterator str1_cIter;  
  
   str1_Iter = str1.end ( );  
   str1_Iter--;  
   str1_Iter--;  
   cout << "The last character-letter of the string str1 is: " << *str1_Iter << endl;  
   cout << "The full orginal string str1 is: " << str1 << endl;  
  
   // end used to test when an iterator has reached the end of its string  
   cout << "The string is now: ";  
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )  
      cout << *str_Iter;  
   cout << endl;  
  
   // The dereferenced iterator can be used to modify a character  
 *str1_Iter = 'T';  
   cout << "The last character-letter of the modified str1 is now: "  
        << *str1_Iter << endl;  
   cout << "The modified string str1 is now: " << str1 << endl;  
  
   // The following line would be an error because iterator is const  
   // *str1_cIter = 'T';  
  
   // For an empty string, end is equivalent to begin  
   if ( str2.begin( ) == str2.end ( ) )  
      cout << "The string str2 is empty." << endl;  
   else  
      cout << "The stringstr2  is not empty." << endl;  
}  
```  
  
```Output  
The last character-letter of the string str1 is: t  
The full orginal string str1 is: No way out.  
The string is now: No way out.  
The last character-letter of the modified str1 is now: T  
The modified string str1 is now: No way ouT.  
The string str2 is empty.  
```  
  
##  <a name="erase"></a>  basic_string::ERASE  
 Bir dizede belirtilen konumdan bir öğe veya öğe aralığını kaldırır.  
  
```  
iterator erase(
    iterator first,   
    iterator last);

iterator erase(
    iterator _It);

basic_string<CharType, Traits, Allocator>& erase(
    size_type _Pos = 0,  
    size_type count = npos);
```  
  
### <a name="parameters"></a>Parametreler  
 `first`  
 Silinecek şekilde ilk öğe konumu aralığında adresleme yineleyici.  
  
 `last`  
 Silinecek şekilde konumunu bir aşan son öğe aralığında adresleme yineleyici.  
  
 `_It`  
 Silinecek şekilde dizedeki öğenin adresleme yineleyici.  
  
 `_Pos`  
 Kaldırılacak dizedeki ilk karakter dizini.  
  
 `count`  
 Varsa dize başlayarak aralığında sayıda kaldırılacak öğe sayısını *_Pos*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk iki üye işlevleri için üye işlevi tarafından kaldırıldı son karakterinden sonraki ilk karakter adresleme yineleyici. Üçüncü üye fonksiyonu için öğeleri silindi dize nesnesine başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Üçüncü üye işlevinin döndürdüğü  **\*bu**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_erase.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // The 1st member function using a range demarcated  
   // by iterators  
   string str1 ( "Hello world" );  
   basic_string <char>::iterator str1_Iter;  
   cout << "The original string object str1 is: "   
        << str1 << "." << endl;  
   str1_Iter = str1.erase ( str1.begin ( ) + 3 , str1.end ( ) - 1 );  
   cout << "The first element after those removed is: "  
        << *str1_Iter << "." << endl;  
   cout << "The modified string object str1 is: " << str1   
           << "." << endl << endl;  
  
   // The 2nd member function erasing a char pointed to   
   // by an iterator  
   string str2 ( "Hello World" );  
   basic_string <char>::iterator str2_Iter;  
   cout << "The original string object str2 is: " << str2  
        << "." << endl;  
   str2_Iter = str2.erase ( str2.begin ( ) + 5 );  
   cout << "The first element after those removed is: "  
        << *str2_Iter << "." << endl;  
   cout << "The modified string object str2 is: " << str2   
        << "." << endl << endl;  
  
   // The 3rd member function erasing a number of chars   
   // after a char  
   string str3 ( "Hello computer" ), str3m;  
   basic_string <char>::iterator str3_Iter;  
   cout << "The original string object str3 is: "   
        << str3 << "." << endl;  
   str3m = str3.erase ( 6 , 8 );  
   cout << "The modified string object str3m is: "   
        << str3m << "." << endl;  
}  
```  
  
```Output  
The original string object str1 is: Hello world.  
The first element after those removed is: d.  
The modified string object str1 is: Held.  
  
The original string object str2 is: Hello World.  
The first element after those removed is: W.  
The modified string object str2 is: HelloWorld.  
  
The original string object str3 is: Hello computer.  
The modified string object str3m is: Hello .  
```  
  
##  <a name="find"></a>  basic_string::Find  
 Bir dizeyi belirtilen bir karakter dizisi eşleşen bir alt dizenin ilk a geçişi için ileriye doğru bir yönde arar.  
  
```  
size_type find(
    value_type _Ch,   
    size_type _Off = 0) const;

 
size_type find(
    const value_type* ptr,  
    size_type _Off = 0) const;

 
size_type find(
    const value_type* ptr,   
    size_type _Off,  
    size_type count) const;

 
size_type find(
    const basic_string<CharType, Traits, Allocator>& str,  
    size_type _Off = 0) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Ch`  
 Üye işlevini aranacak olduğu karakter değeri.  
  
 `_Off`  
 Başlamak için arama olduğu konumu dizini.  
  
 `ptr`  
 C-üye fonksiyonu aranacak olduğu dize.  
  
 `count`  
 Üye işlevi aranacak olduğu C-dizesindeki ilk karakter İleri sayım karakter sayısı.  
  
 `str`  
 Üye işlevini aranacak olduğu dizesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizenin ilk karakter dizinini başarılı olduğunda arama; Aksi takdirde `npos`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_find.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // The first member function  
   // searches for a single character in a string  
   string str1 ( "Hello Everyone" );  
   cout << "The original string str1 is: " << str1 << endl;  
   basic_string <char>::size_type indexCh1a, indexCh1b;  
  
   indexCh1a = str1.find ( "e" , 3 );  
   if (indexCh1a != string::npos )  
      cout << "The index of the 1st 'e' found after the 3rd"  
           << " position in str1 is: " << indexCh1a << endl;  
   else  
      cout << "The character 'e' was not found in str1 ." << endl;  
  
   indexCh1b = str1.find ( "x" );  
   if (indexCh1b != string::npos )  
      cout << "The index of the 'x' found in str1 is: "  
           << indexCh1b << endl << endl;  
   else  
      cout << "The Character 'x' was not found in str1."  
           << endl << endl;  
  
   // The second member function searches a string  
   // for a substring as specified by a C-string  
   string str2 ( "Let me make this perfectly clear." );  
   cout << "The original string str2 is: " << str2 << endl;  
   basic_string <char>::size_type indexCh2a, indexCh2b;  
  
   const char *cstr2 = "perfect";  
   indexCh2a = str2.find ( cstr2 , 5 );  
   if ( indexCh2a != string::npos )  
      cout << "The index of the 1st element of 'perfect' "  
           << "after\n the 5th position in str2 is: "  
           << indexCh2a << endl;  
   else  
      cout << "The substring 'perfect' was not found in str2 ."  
           << endl;  
  
   const char *cstr2b = "imperfectly";  
   indexCh2b = str2.find ( cstr2b , 0 );  
   if (indexCh2b != string::npos )  
      cout << "The index of the 1st element of 'imperfect' "  
           << "after\n the 5th position in str3 is: "  
           << indexCh2b << endl;  
   else  
      cout << "The substring 'imperfect' was not found in str2 ."  
           << endl << endl;  
  
   // The third member function searches a string  
   // for a substring as specified by a C-string  
   string str3 ( "This is a sample string for this program" );  
   cout << "The original string str3 is: " << str3 << endl;  
   basic_string <char>::size_type indexCh3a, indexCh3b;  
  
   const char *cstr3a = "sample";  
   indexCh3a = str3.find ( cstr3a );  
   if ( indexCh3a != string::npos )  
      cout << "The index of the 1st element of sample "  
           << "in str3 is: " << indexCh3a << endl;  
   else  
      cout << "The substring 'perfect' was not found in str3 ."  
           << endl;  
  
   const char *cstr3b = "for";  
   indexCh3b = str3.find ( cstr3b , indexCh3a + 1 , 2 );  
   if (indexCh3b != string::npos )  
      cout << "The index of the next occurrence of 'for' is in "  
           << "str3 begins at: " << indexCh3b << endl << endl;  
   else  
      cout << "There is no next occurrence of 'for' in str3 ."  
           << endl << endl;  
  
   // The fourth member function searches a string  
   // for a substring as specified by a string  
   string str4 ( "clearly this perfectly unclear." );  
   cout << "The original string str4 is: " << str4 << endl;  
   basic_string <char>::size_type indexCh4a, indexCh4b;  
  
   string str4a ( "clear" );  
   indexCh4a = str4.find ( str4a , 5 );  
   if ( indexCh4a != string::npos )  
      cout << "The index of the 1st element of 'clear' "  
           << "after\n the 5th position in str4 is: "  
           << indexCh4a << endl;  
   else  
      cout << "The substring 'clear' was not found in str4 ."  
           << endl;  
  
   string str4b ( "clear" );  
   indexCh4b = str4.find ( str4b );  
   if (indexCh4b != string::npos )  
      cout << "The index of the 1st element of 'clear' "  
           << "in str4 is: "  
           << indexCh4b << endl;  
   else  
      cout << "The substring 'clear' was not found in str4 ."  
           << endl << endl;  
}  
```  
  
```Output  
The original string str1 is: Hello Everyone  
The index of the 1st 'e' found after the 3rd position in str1 is: 8  
The Character 'x' was not found in str1.  
  
The original string str2 is: Let me make this perfectly clear.  
The index of the 1st element of 'perfect' after  
 the 5th position in str2 is: 17  
The substring 'imperfect' was not found in str2 .  
  
The original string str3 is: This is a sample string for this program  
The index of the 1st element of sample in str3 is: 10  
The index of the next occurrence of 'for' is in str3 begins at: 24  
  
The original string str4 is: clearly this perfectly unclear.  
The index of the 1st element of 'clear' after  
 the 5th position in str4 is: 25  
The index of the 1st element of 'clear' in str4 is: 0  
```  
  
##  <a name="find_first_not_of"></a>  basic_string::find_first_not_of  
 Belirtilen dizenin bir öğe değil ilk karakter arasında bir dize arar.  
  
```  
size_type find_first_not_of(
    value_type _Ch,   
    size_type _Off = 0) const;

 
size_type find_first_not_of(
    const value_type* ptr,  
    size_type _Off = 0) const;

 
size_type find_first_not_of(
    const value_type* ptr,   
    size_type _Off,  
    size_type count) const;

 
size_type find_first_not_of(
    const basic_string<CharType, Traits, Allocator>& str,  
    size_type _Off = 0) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Ch`  
 Üye işlevini aranacak olduğu karakter değeri.  
  
 `_Off`  
 Başlamak için arama olduğu konumu dizini.  
  
 `ptr`  
 C-üye fonksiyonu aranacak olduğu dize.  
  
 `count`  
 Üye işlevi aranacak olduğu C-dizesindeki ilk karakter İleri sayım karakter sayısı.  
  
 `str`  
 Üye işlevini aranacak olduğu dizesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizenin ilk karakter dizinini başarılı olduğunda arama; Aksi takdirde `npos`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_find_first_not_of.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // The first member function  
   // searches for a single character in a string  
   string str1 ( "xddd-1234-abcd" );  
   cout << "The original string str1 is: " << str1 << endl;  
   basic_string <char>::size_type indexCh1a, indexCh1b;  
   static const basic_string <char>::size_type npos = -1;  
  
   indexCh1a = str1.find_first_not_of ( "d" , 2 );  
   if ( indexCh1a != npos )  
      cout << "The index of the 1st 'd' found after the 3rd"  
           << " position in str1 is: " << indexCh1a << endl;  
   else  
      cout << "The character 'd' was not found in str1 ." << endl;  
  
   indexCh1b = str1.find_first_not_of  ( "x" );  
   if (indexCh1b != npos )  
      cout << "The index of the 'non x' found in str1 is: "   
           << indexCh1b << endl << endl;  
   else  
      cout << "The character 'non x' was not found in str1."  
           << endl << endl;  
  
   // The second member function searches a string  
   // for a substring as specified by a C-string  
   string str2 ( "BBB-1111" );  
   cout << "The original string str2 is: " << str2 << endl;  
   basic_string <char>::size_type indexCh2a, indexCh2b;  
  
   const char *cstr2 = "B1";  
   indexCh2a = str2.find_first_not_of ( cstr2 , 6 );  
   if ( indexCh2a != npos )  
      cout << "The index of the 1st occurrence of an "  
           << "element of 'B1' in str2 after\n the 6th "  
           << "position is: " << indexCh2a << endl;  
   else  
      cout << "Elements of the substring 'B1' were not"  
           << "\n found in str2 after the 6th position."  
           << endl;  
  
   const char *cstr2b = "B2";  
   indexCh2b = str2.find_first_not_of ( cstr2b );  
   if ( indexCh2b != npos )  
      cout << "The index of the 1st element of 'B2' "  
           << "after\n the 0th position in str2 is: "  
           << indexCh2b << endl << endl;  
   else  
      cout << "The substring 'B2' was not found in str2 ."   
           << endl << endl << endl;  
  
   // The third member function searches a string  
   // for a substring as specified by a C-string  
   string str3 ( "444-555-GGG" );  
   cout << "The original string str3 is: " << str3 << endl;  
   basic_string <char>::size_type indexCh3a, indexCh3b;  
  
   const char *cstr3a = "45G";  
   indexCh3a = str3.find_first_not_of ( cstr3a );  
   if ( indexCh3a != npos )  
      cout << "The index of the 1st occurrence of an "  
           << "element in str3\n other than one of the "  
           << "characters in '45G' is: " << indexCh3a   
           << endl;  
   else  
      cout << "Elements in str3 contain only characters "  
           << " in the string '45G'. "  
           << endl;  
  
   const char *cstr3b = "45G";  
   indexCh3b = str3.find_first_not_of ( cstr3b , indexCh3a + 1 , 2 );  
   if ( indexCh3b != npos )  
      cout << "The index of the second occurrence of an "  
           << "element of '45G' in str3\n after the 0th "  
           << "position is: " << indexCh3b << endl << endl;  
   else  
      cout << "Elements in str3 contain only characters "  
           << " in the string  '45G'. "  
           << endl  << endl;  
  
   // The fourth member function searches a string  
   // for a substring as specified by a string  
   string str4 ( "12-ab-12-ab" );  
   cout << "The original string str4 is: " << str4 << endl;  
   basic_string <char>::size_type indexCh4a, indexCh4b;  
  
   string str4a ( "ba3" );  
   indexCh4a = str4.find_first_not_of ( str4a , 5 );  
   if (indexCh4a != npos )  
      cout << "The index of the 1st non occurrence of an "  
           << "element of 'ba3' in str4 after\n the 5th "  
           << "position is: " << indexCh4a << endl;  
   else  
      cout << "Elements other than those in the substring"  
           << " 'ba3' were not found in the string str4."  
           << endl;  
  
   string str4b ( "12" );  
   indexCh4b = str4.find_first_not_of ( str4b  );  
   if (indexCh4b != npos )  
      cout << "The index of the 1st non occurrence of an "  
           << "element of '12' in str4 after\n the 0th "  
           << "position is: " << indexCh4b << endl;  
   else  
      cout << "Elements other than those in the substring"  
           << " '12' were not found in the string str4."  
           << endl;  
}  
```  
  
```Output  
The original string str1 is: xddd-1234-abcd  
The index of the 1st 'd' found after the 3rd position in str1 is: 4  
The index of the 'non x' found in str1 is: 1  
  
The original string str2 is: BBB-1111  
Elements of the substring 'B1' were not  
 found in str2 after the 6th position.  
The index of the 1st element of 'B2' after  
 the 0th position in str2 is: 3  
  
The original string str3 is: 444-555-GGG  
The index of the 1st occurrence of an element in str3  
 other than one of the characters in '45G' is: 3  
The index of the second occurrence of an element of '45G' in str3  
 after the 0th position is: 7  
  
The original string str4 is: 12-ab-12-ab  
The index of the 1st non occurrence of an element of 'ba3' in str4 after  
 the 5th position is: 5  
The index of the 1st non occurrence of an element of '12' in str4 after  
 the 0th position is: 2  
```  
  
##  <a name="find_first_of"></a>  basic_string::find_first_of  
 Belirtilen dizenin herhangi bir öğe ile eşleşen ilk karakter arasında bir dize arar.  
  
```  
size_type find_first_of(
    value_type _Ch,   
    size_type _Off = 0) const;

 
size_type find_first_of(
    const value_type* ptr,  
    size_type _Off = 0) const;

 
size_type find_first_of(
    const value_type* ptr,   
    size_type _Off,  
    size_type count) const;

 
size_type find_first_of(
    const basic_string<CharType, Traits, Allocator>& str,  
    size_type _Off = 0) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Ch`  
 Üye işlevini aranacak olduğu karakter değeri.  
  
 `_Off`  
 Başlamak için arama olduğu konumu dizini.  
  
 `ptr`  
 C-üye fonksiyonu aranacak olduğu dize.  
  
 `count`  
 Üye işlevi aranacak olduğu C-dizesindeki ilk karakter İleri sayım karakter sayısı.  
  
 `str`  
 Üye işlevini aranacak olduğu dizesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizenin ilk karakter dizinini başarılı olduğunda arama; Aksi takdirde `npos`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_find_first_of.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // The first member function  
   // searches for a single character in a string  
   string str1 ( "abcd-1234-abcd-1234" );  
   cout << "The original string str1 is: " << str1 << endl;  
   basic_string <char>::size_type indexCh1a, indexCh1b;  
   static const basic_string <char>::size_type npos = -1;  
  
   indexCh1a = str1.find_first_of ( "d" , 5 );  
   if ( indexCh1a != npos )  
      cout << "The index of the 1st 'd' found after the 5th"  
           << " position in str1 is: " << indexCh1a << endl;  
   else  
      cout << "The character 'd' was not found in str1 ." << endl;  
  
   indexCh1b = str1.find_first_of ( "x" );  
   if ( indexCh1b != npos )  
      cout << "The index of the 'x' found in str1 is: "   
           << indexCh1b << endl << endl;  
   else  
      cout << "The character 'x' was not found in str1."  
           << endl << endl;  
  
   // The second member function searches a string  
   // for any element of a substring as specified by a C-string  
   string str2 ( "ABCD-1234-ABCD-1234" );  
   cout << "The original string str2 is: " << str2 << endl;  
   basic_string <char>::size_type indexCh2a, indexCh2b;  
  
   const char *cstr2 = "B1";  
   indexCh2a = str2.find_first_of ( cstr2 , 6 );  
   if ( indexCh2a != npos )  
      cout << "The index of the 1st occurrence of an "  
           << "element of 'B1' in str2 after\n the 6th "  
           << "position is: " << indexCh2a << endl;  
   else  
      cout << "Elements of the substring 'B1' were not "  
           << "found in str2 after the 10th position."  
           << endl;  
  
   const char *cstr2b = "D2";  
   indexCh2b = str2.find_first_of ( cstr2b );  
   if ( indexCh2b != npos )  
      cout << "The index of the 1st element of 'D2' "  
           << "after\n the 0th position in str2 is: "  
           << indexCh2b << endl << endl;  
   else  
      cout << "The substring 'D2' was not found in str2 ."   
           << endl << endl << endl;  
  
   // The third member function searches a string  
   // for any element of a substring as specified by a C-string  
   string str3 ( "123-abc-123-abc-456-EFG-456-EFG" );  
   cout << "The original string str3 is: " << str3 << endl;  
   basic_string <char>::size_type indexCh3a, indexCh3b;  
  
   const char *cstr3a = "5G";  
   indexCh3a = str3.find_first_of ( cstr3a );  
   if ( indexCh3a != npos )  
      cout << "The index of the 1st occurrence of an "  
           << "element of '5G' in str3 after\n the 0th "  
           << "position is: " << indexCh3a << endl;  
   else  
      cout << "Elements of the substring '5G' were not "  
           << "found in str3\n after the 0th position."  
           << endl;  
  
   const char *cstr3b = "5GF";  
   indexCh3b = str3.find_first_of  ( cstr3b , indexCh3a + 1 , 2 );  
   if (indexCh3b != npos )  
      cout << "The index of the second occurrence of an "  
           << "element of '5G' in str3\n after the 0th "  
           << "position is: " << indexCh3b << endl << endl;  
   else  
      cout << "Elements of the substring '5G' were not "  
           << "found in str3\n after the first occurrrence."  
           << endl << endl;  
  
   // The fourth member function searches a string  
   // for any element of a substring as specified by a string  
   string str4 ( "12-ab-12-ab" );  
   cout << "The original string str4 is: " << str4 << endl;  
   basic_string <char>::size_type indexCh4a, indexCh4b;  
  
   string str4a ( "ba3" );  
   indexCh4a = str4.find_first_of ( str4a , 5 );  
   if ( indexCh4a != npos )  
      cout << "The index of the 1st occurrence of an "  
           << "element of 'ba3' in str4 after\n the 5th "  
           << "position is: " << indexCh4a << endl;  
   else  
      cout << "Elements of the substring 'ba3' were not "  
           << "found in str4\n after the 0th position."  
           << endl;  
  
   string str4b ( "a2" );  
   indexCh4b = str4.find_first_of ( str4b );  
   if ( indexCh4b != npos )  
      cout << "The index of the 1st occurrence of an "  
           << "element of 'a2' in str4 after\n the 0th "  
           << "position is: " << indexCh4b << endl;  
   else  
      cout << "Elements of the substring 'a2' were not "  
           << "found in str4\n after the 0th position."  
           << endl;  
}  
```  
  
```Output  
The original string str1 is: abcd-1234-abcd-1234  
The index of the 1st 'd' found after the 5th position in str1 is: 13  
The character 'x' was not found in str1.  
  
The original string str2 is: ABCD-1234-ABCD-1234  
The index of the 1st occurrence of an element of 'B1' in str2 after  
 the 6th position is: 11  
The index of the 1st element of 'D2' after  
 the 0th position in str2 is: 3  
  
The original string str3 is: 123-abc-123-abc-456-EFG-456-EFG  
The index of the 1st occurrence of an element of '5G' in str3 after  
 the 0th position is: 17  
The index of the second occurrence of an element of '5G' in str3  
 after the 0th position is: 22  
  
The original string str4 is: 12-ab-12-ab  
The index of the 1st occurrence of an element of 'ba3' in str4 after  
 the 5th position is: 9  
The index of the 1st occurrence of an element of 'a2' in str4 after  
 the 0th position is: 1  
```  
  
##  <a name="find_last_not_of"></a>  basic_string::find_last_not_of  
 Belirtilen dizenin herhangi bir öğe değil son karakter arasında bir dize arar.  
  
```  
size_type find_last_not_of(
    value_type _Ch,   
    size_type _Off = npos) const;

 
size_type find_last_not_of(
    const value_type* ptr,  
    size_type _Off = npos) const;

 
size_type find_last_not_of(
    const value_type* ptr,   
    size_type _Off,  
    size_type count) const;

 
size_type find_last_not_of(
    const basic_string<CharType, Traits, Allocator>& str,  
    size_type _Off = npos) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Ch`  
 Üye işlevini aranacak olduğu karakter değeri.  
  
 `_Off`  
 Bitirmek için arama olduğu konumu dizini.  
  
 `ptr`  
 C-üye fonksiyonu aranacak olduğu dize.  
  
 `count`  
 Üye işlevi aranacak olduğu C-dizesindeki ilk karakter İleri sayım karakter sayısı.  
  
 `str`  
 Üye işlevini aranacak olduğu dizesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizenin ilk karakter dizinini başarılı olduğunda arama; Aksi takdirde `npos`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_find_last_not_of.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // The first member function  
   // searches for a single character in a string  
   string str1 ( "dddd-1dd4-abdd" );  
   cout << "The original string str1 is: " << str1 << endl;  
   basic_string <char>::size_type indexCh1a, indexCh1b;  
   static const basic_string <char>::size_type npos = -1;  
  
   indexCh1a = str1.find_last_not_of ( "d" , 7 );  
   if ( indexCh1a != npos )  
      cout << "The index of the last non 'd'\n found before the "  
           << "7th position in str1 is: " << indexCh1a << endl;  
   else  
      cout << "The non 'd' character was not found ." << endl;  
  
   indexCh1b = str1.find_last_not_of  ( "d" );  
   if ( indexCh1b != npos )  
      cout << "The index of the non 'd' found in str1 is: "   
           << indexCh1b << endl << endl;  
   else  
      cout << "The Character 'non x' was not found in str1."  
           << endl << endl;  
  
   // The second member function searches a string  
   // for a substring as specified by a C-string  
   string str2 ( "BBB-1111" );  
   cout << "The original string str2 is: " << str2 << endl;  
   basic_string <char>::size_type indexCh2a, indexCh2b;  
  
   const char *cstr2 = "B1";  
   indexCh2a = str2.find_last_not_of  ( cstr2 , 6 );  
   if ( indexCh2a != npos )  
      cout << "The index of the last occurrence of a "  
           << "element\n not of 'B1' in str2 before the 6th "  
           << "position is: " << indexCh2a << endl;  
   else  
      cout << "Elements not of the substring 'B1' were not "  
           << "\n found in str2 before the 6th position."  
           << endl;  
  
   const char *cstr2b = "B-1";  
   indexCh2b = str2.find_last_not_of  ( cstr2b );  
   if ( indexCh2b != npos )  
      cout << "The index of the last element not "  
           << "in 'B-1'\n is: "  
           << indexCh2b << endl << endl;  
   else  
      cout << "The elements of the substring 'B-1' were "  
           << "not found in str2 ."   
           << endl << endl;  
  
   // The third member function searches a string  
   // for a substring as specified by a C-string  
   string str3 ( "444-555-GGG" );  
   cout << "The original string str3 is: " << str3 << endl;  
   basic_string <char>::size_type indexCh3a, indexCh3b;  
  
   const char *cstr3a = "45G";  
   indexCh3a = str3.find_last_not_of ( cstr3a );  
   if ( indexCh3a != npos )  
      cout << "The index of the last occurrence of an "  
           << "element in str3\n other than one of the "  
           << "characters in '45G' is: " << indexCh3a   
           << endl;  
   else  
      cout << "Elements in str3 contain only characters "  
           << " in the string  '45G'. "  
           << endl;  
  
   const char *cstr3b = "45G";  
   indexCh3b = str3.find_last_not_of ( cstr3b , 6 , indexCh3a - 1 );  
   if (indexCh3b != npos )  
      cout << "The index of the penultimate occurrence of an "  
           << "element\n not in '45G' in str3 is: "  
           << indexCh3b << endl << endl;  
   else  
      cout << "Elements in str3 contain only characters "  
           << " in the string '45G'. "  
           << endl  << endl;  
  
   // The fourth member function searches a string  
   // for a substring as specified by a string  
   string str4 ( "12-ab-12-ab" );  
   cout << "The original string str4 is: " << str4 << endl;  
   basic_string <char>::size_type indexCh4a, indexCh4b;  
  
   string str4a ( "b-a" );  
   indexCh4a = str4.find_last_not_of  ( str4a , 5 );  
   if ( indexCh4a != npos )  
      cout << "The index of the last occurrence of an "  
           << "element not\n in 'b-a' in str4 before the 5th "  
           << "position is: " << indexCh4a << endl;  
   else  
      cout << "Elements other than those in the substring"  
           << " 'b-a' were not found in the string str4."  
           << endl;  
  
   string str4b ( "12" );  
   indexCh4b = str4.find_last_not_of ( str4b  );  
   if ( indexCh4b != npos )  
      cout << "The index of the last occurrence of an "  
           << "element not in '12'\n in str4 before the end "  
           << "position is: " << indexCh4b << endl;  
   else  
      cout << "Elements other than those in the substring"  
           << " '12'\n were not found in the string str4."  
           << endl;  
}  
```  
  
```Output  
The original string str1 is: dddd-1dd4-abdd  
The index of the last non 'd'  
 found before the 7th position in str1 is: 5  
The index of the non 'd' found in str1 is: 11  
  
The original string str2 is: BBB-1111  
The index of the last occurrence of a element  
 not of 'B1' in str2 before the 6th position is: 3  
The elements of the substring 'B-1' were not found in str2 .  
  
The original string str3 is: 444-555-GGG  
The index of the last occurrence of an element in str3  
 other than one of the characters in '45G' is: 7  
The index of the penultimate occurrence of an element  
 not in '45G' in str3 is: 3  
  
The original string str4 is: 12-ab-12-ab  
The index of the last occurrence of an element not  
 in 'b-a' in str4 before the 5th position is: 1  
The index of the last occurrence of an element not in '12'  
 in str4 before the end position is: 10  
```  
  
##  <a name="find_last_of"></a>  basic_string::find_last_of  
 Belirtilen dizenin herhangi bir öğe eşleşen son karakter arasında bir dize arar.  
  
```  
size_type find_last_of(
    value_type _Ch,   
    size_type _Off = npos) const;

 
 
size_type find_last_of(
    const value_type* ptr,  
    size_type _Off = npos) const;

 
 
size_type find_last_of(
    const value_type* ptr,   
    size_type _Off,  
    size_type count) const;

 
 
size_type find_last_of(
    const basic_string<CharType, Traits, Allocator>& str,  
    size_type _Off = npos) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Ch`  
 Üye işlevini aranacak olduğu karakter değeri.  
  
 `_Off`  
 Bitirmek için arama olduğu konumu dizini.  
  
 `ptr`  
 C-üye fonksiyonu aranacak olduğu dize.  
  
 `count`  
 Üye işlevi aranacak olduğu C-dizesindeki ilk karakter İleri sayım karakter sayısı.  
  
 `str`  
 Üye işlevini aranacak olduğu dizesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Alt dizenin son karakter dizinini başarılı olduğunda arama; Aksi takdirde `npos`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_find_last_of.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // The first member function  
   // searches for a single character in a string  
   string str1 ( "abcd-1234-abcd-1234" );  
   cout << "The original string str1 is: " << str1 << endl;  
   basic_string <char>::size_type indexCh1a, indexCh1b;  
   static const basic_string <char>::size_type npos = -1;  
  
   indexCh1a = str1.find_last_of ( "d" , 14 );  
   if ( indexCh1a != npos )  
      cout << "The index of the last 'd' found before the 14th"  
           << " position in str1 is: " << indexCh1a << endl;  
   else  
      cout << "The character 'd' was not found in str1 ." << endl;  
  
   indexCh1b = str1.find_first_of ( "x" );  
   if ( indexCh1b != npos )  
      cout << "The index of the 'x' found in str1 is: "  
           << indexCh1b << endl << endl;  
   else  
      cout << "The character 'x' was not found in str1."  
           << endl << endl;  
  
   // The second member function searches a string  
   // for a substring as specified by a C-string  
   string str2 ( "ABCD-1234-ABCD-1234" );  
   cout << "The original string str2 is: " << str2 << endl;  
   basic_string <char>::size_type indexCh2a, indexCh2b;  
  
   const char *cstr2 = "B1";  
   indexCh2a = str2.find_last_of  ( cstr2 , 12 );  
   if (indexCh2a != npos )  
      cout << "The index of the last occurrence of an "  
           << "element of 'B1' in str2 before\n the 12th "  
           << "position is: " << indexCh2a << endl;  
   else  
      cout << "Elements of the substring 'B1' were not "  
           << "found in str2 before the 12th position."  
           << endl;  
  
   const char *cstr2b = "D2";  
   indexCh2b = str2.find_last_of  ( cstr2b );  
   if ( indexCh2b != npos )  
      cout << "The index of the last element of 'D2' "  
           << "after\n the 0th position in str2 is: "  
           << indexCh2b << endl << endl;  
   else  
      cout << "The substring 'D2' was not found in str2 ."  
           << endl << endl << endl;  
  
   // The third member function searches a string  
   // for a substring as specified by a C-string  
   string str3 ( "456-EFG-456-EFG" );  
   cout << "The original string str3 is: " << str3 << endl;  
   basic_string <char>::size_type indexCh3a;  
  
   const char *cstr3a = "5E";  
   indexCh3a = str3.find_last_of ( cstr3a , 8 , 8 );  
   if ( indexCh3a != npos )  
      cout << "The index of the last occurrence of an "  
           << "element of '5E' in str3 before\n the 8th "  
           << "position is: " << indexCh3a << endl << endl;  
   else  
      cout << "Elements of the substring '5G' were not "  
           << "found in str3\n before the 8th position."  
           << endl << endl;  
  
   // The fourth member function searches a string  
   // for a substring as specified by a string  
   string str4 ( "12-ab-12-ab" );  
   cout << "The original string str4 is: " << str4 << endl;  
   basic_string <char>::size_type indexCh4a, indexCh4b;  
  
   string str4a ( "ba3" );  
   indexCh4a = str4.find_last_of  ( str4a , 8 );  
   if ( indexCh4a != npos )  
      cout << "The index of the last occurrence of an "  
           << "element of 'ba3' in str4 before\n the 8th "  
           << "position is: " << indexCh4a << endl;  
   else  
      cout << "Elements of the substring 'ba3' were not "  
           << "found in str4\n after the 0th position."  
           << endl;  
  
   string str4b ( "a2" );  
   indexCh4b = str4.find_last_of ( str4b  );  
   if ( indexCh4b != npos )  
      cout << "The index of the last occurrence of an "  
           << "element of 'a2' in str4 before\n the 0th "  
           << "position is: " << indexCh4b << endl;  
   else  
      cout << "Elements of the substring 'a2' were not "  
           << "found in str4\n after the 0th position."  
           << endl;  
}  
```  
  
```Output  
The original string str1 is: abcd-1234-abcd-1234  
The index of the last 'd' found before the 14th position in str1 is: 13  
The character 'x' was not found in str1.  
  
The original string str2 is: ABCD-1234-ABCD-1234  
The index of the last occurrence of an element of 'B1' in str2 before  
 the 12th position is: 11  
The index of the last element of 'D2' after  
 the 0th position in str2 is: 16  
  
The original string str3 is: 456-EFG-456-EFG  
The index of the last occurrence of an element of '5E' in str3 before  
 the 8th position is: 4  
  
The original string str4 is: 12-ab-12-ab  
The index of the last occurrence of an element of 'ba3' in str4 before  
 the 8th position is: 4  
The index of the last occurrence of an element of 'a2' in str4 before  
 the 0th position is: 9  
```  
  
##  <a name="front"></a>  basic_string::Front  
 İlk öğe başvuru bir dize döndürür.  
  
```  
const_reference front() const;

 
reference front();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk öğe boş olmalıdır dizesinin bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="get_allocator"></a>  basic_string::get_allocator  
 Bir kopyasını dizesi oluşturmak için kullanılan ayırıcısı nesnesi döndürür.  
  
```  
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizesi tarafından kullanılan ayırıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini saklı ayırıcısı nesnesini döndürür.  
  
 Allocators string sınıfı için sınıf depolama nasıl yönettiğini belirtin. Kapsayıcı sınıfları ile sağlanan varsayılan allocators çoğu programlama ihtiyaçları için yeterli. Yazma ve kendi allocator sınıfı kullanarak ileri düzeyde C++ bir konudur.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_get_allocator.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   // The following lines declare objects  
   // that use the default allocator.  
   string s1;  
   basic_string <char> s2;  
   basic_string <char, char_traits< char >, allocator< char > > s3;  
  
   // s4 will use the same allocator class as s1  
   basic_string <char> s4( s1.get_allocator ( ) );  
  
   basic_string <char>::allocator_type xchar = s1.get_allocator( );  
   // You can now call functions on the allocator class xchar used by s1  
}  
```  
  
##  <a name="insert"></a>  basic_string::insert  
 Bir öğenin veya öğe sayısı veya bir dizi öğeleri belirtilen bir konumda dize ekler.  
  
```  
basic_string<CharType, Traits, Allocator>& insert(
    size_type _P0,   
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& insert(
    size_type _P0,   
    const value_type* ptr,  
    size_type count);

basic_string<CharType, Traits, Allocator>& insert(
    size_type _P0,  
    const basic_string<CharType, Traits, Allocator>& str);

basic_string<CharType, Traits, Allocator>& insert(
    size_type _P0,  
    const basic_string<CharType, Traits, Allocator>& str,   
    size_type _Off,   
    size_type count);

basic_string<CharType, Traits, Allocator>& insert(
    size_type _P0,  
    size_type count,   
    value_type _Ch);

iterator insert(
    iterator _It);

iterator insert(
    iterator _It,  
    value_type _Ch)l  
template <class InputIterator>  
void insert(
    iterator _It,   
    InputIterator first,   
    InputIterator last);

void insert(
    iterator _It,   
    size_type count,   
    value_type _Ch);

void insert(
    iterator _It,  
    const_pointer first,  
    const_pointer last);

void insert(
    iterator _It,  
    const_iterator first,  
    const_iterator last);
```  
  
### <a name="parameters"></a>Parametreler  
 *_P0*  
 Ekleme noktasını arkasında konumunun dizinini yeni karakterler.  
  
 `ptr`  
 C-tamamen veya kısmen dizeye eklenecek dize.  
  
 `count`  
 Eklenecek karakter sayısı.  
  
 `str`  
 Tamamen veya kısmen hedef dizeye eklenecek dize.  
  
 `_Off`  
 Eklenecek karakterleri sağladığını kaynak dizesi parçası dizini.  
  
 `_Ch`  
 Karakter değeri eklenecek öğe.  
  
 `_It`  
 Yineleyici bir karakter eklenecek konumu adresleme.  
  
 `first`  
 Bir giriş Yineleyici, const_pointer veya kaynak aralığındaki ilk öğe adresleme const_iterator eklenecek.  
  
 `last`  
 Bir giriş Yineleyici, const_pointer veya kaynak aralığı son öğenin ötesinde bir konumda adresleme const_iterator eklenecek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni karakterler üye fonksiyonu tarafından veya tek tek karakter eklemeler, söz konusu olduğunda karakterin eklenen adresleme yineleyici atandığı dize nesnesine başvuru ya da bağlı olarak belirli üyesi yok işlev.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_insert.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // The first member function inserting a C-string  
   // at a given position  
   basic_string <char> str1a ( "way" );  
   const char *cstr1a = "a";  
   str1a.insert ( 0, cstr1a );  
   cout << "The string with a C-string inserted at position 0 is: "  
        << str1a << "." << endl;  
  
   // The second member function inserting a C-string  
   // at a given position for a specified number of elements  
   basic_string <char> str2a ( "Good" );  
   const char *cstr2a = "Bye Bye Baby";  
   str2a.insert ( 4, cstr2a ,3 );  
   cout << "The string with a C-string inserted at the end is: "  
        << str2a << "." << endl;  
  
   // The third member function inserting a string  
   // at a given position  
   basic_string <char> str3a ( "Bye" );  
   string str3b ( "Good" );  
   str3a.insert ( 0, str3b );  
   cout << "The string with a string inserted at position 0 is: "  
        << str3a << "." << endl;  
  
   // The fourth member function inserting part of  
   // a string at a given position  
   basic_string <char> str4a ( "Good " );  
   string str4b ( "Bye Bye Baby" );  
   str4a.insert ( 5, str4b , 8 , 4 );  
   cout << "The string with part of a string inserted at position 4 is: "  
        << str4a << "." << endl;  
  
   // The fifth member function inserts a number of characters  
   // at a specified position in the string  
   string str5 ( "The number is: ." );  
   str5.insert ( 15 , 3 , '3' );  
   cout << "The string with characters inserted is: "  
        << str5 << endl;  
  
   // The sixth member function inserts a character  
   // at a specified position in the string  
   string str6 ( "ABCDFG" );  
   basic_string <char>::iterator str6_Iter = ( str6.begin ( ) + 4 );  
   str6.insert ( str6_Iter , 'e' );  
   cout << "The string with a character inserted is: "  
        << str6 << endl;  
  
   // The seventh member function inserts a range  
   // at a specified position in the string  
   string str7a ( "ABCDHIJ" );  
   string str7b ( "abcdefgh" );  
   basic_string <char>::iterator str7a_Iter = (str7a.begin ( ) + 4 );  
   str7a.insert ( str7a_Iter , str7b.begin ( ) + 4 , str7b.end ( ) -1 );  
   cout << "The string with a character inserted from a range is: "  
        << str7a << endl;  
  
   // The eigth member function inserts a number of  
   // characters at a specified position in the string  
   string str8 ( "ABCDHIJ" );  
   basic_string <char>::iterator str8_Iter = ( str8.begin ( ) + 4 );  
   str8.insert ( str8_Iter , 3 , 'e' );  
   cout << "The string with a character inserted from a range is: "  
        << str8 << endl;  
}  
```  
  
```Output  
The string with a C-string inserted at position 0 is: away.  
The string with a C-string inserted at the end is: GoodBye.  
The string with a string inserted at position 0 is: GoodBye.  
The string with part of a string inserted at position 4 is: Good Baby.  
The string with characters inserted is: The number is: 333.  
The string with a character inserted is: ABCDeFG  
The string with a character inserted from a range is: ABCDefgHIJ  
The string with a character inserted from a range is: ABCDeeeHIJ  
```  
  
##  <a name="iterator"></a>  basic_string::iterator  
 Rasgele erişim yineleyici sağlayan bir tür erişim ve okuma bir **const** dizesindeki öğesi.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür **yineleyici** bir karakterin değerini değiştirmek için kullanılan ve bir iletme yön dizesinde yinelemek için kullanılır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [başlamak](#begin) bildirme ve kullanma konusunda bir örnek için **yineleyici**.  
  
##  <a name="length"></a>  basic_string::length  
 Öğelerin geçerli bir dize döndürür.  
  
```  
size_type length() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini aynıdır [boyutu](#size).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_length.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   string str1 ("Hello world");  
   cout << "The original string str1 is: " << str1 << endl;  
  
   // The size and length member functions differ in name only  
   basic_string <char>::size_type sizeStr1, lenStr1;  
   sizeStr1 = str1.size ( );  
   lenStr1 = str1.length ( );  
  
   basic_string <char>::size_type capStr1, max_sizeStr1;  
   capStr1 = str1.capacity ( );  
   max_sizeStr1 = str1.max_size ( );  
  
   // Compare size, length, capacity & max_size of a string  
   cout << "The current size of original string str1 is: "   
        << sizeStr1 << "." << endl;  
   cout << "The current length of original string str1 is: "   
        << lenStr1 << "." << endl;  
   cout << "The capacity of original string str1 is: "  
        << capStr1 << "." << endl;  
   cout << "The max_size of original string str1 is: "   
        << max_sizeStr1 << "." << endl << endl;  
  
   str1.erase ( 6, 5 );  
   cout << "The modified string str1 is: " << str1 << endl;  
  
   sizeStr1 = str1.size ( );  
   lenStr1 = str1.length ( );  
   capStr1 = str1.capacity ( );  
   max_sizeStr1 = str1.max_size ( );  
  
   // Compare size, length, capacity & max_size of a string  
   // after erasing part of the original string  
   cout << "The current size of modified string str1 is: "   
        << sizeStr1 << "." << endl;  
   cout << "The current length of modified string str1 is: "   
        << lenStr1 << "." << endl;  
   cout << "The capacity of modified string str1 is: "  
        << capStr1 << "." << endl;  
   cout << "The max_size of modified string str1 is: "   
        << max_sizeStr1 << "." << endl;  
}  
```  
  
##  <a name="max_size"></a>  basic_string::max_size  
 En fazla bir dize içermesi karakter sayısını döndürür.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir dizeyi karakter üst sınırını içerebilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Türünde bir özel durum [length_error sınıfı](../standard-library/length-error-class.md) bir işlem en yüksek boyuttan büyük uzunluğa sahip bir dize vermediğinde oluşur.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_max_size.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   string str1 ("Hello world");  
   cout << "The original string str1 is: " << str1 << endl;  
  
   // The size and length member functions differ in name only  
   basic_string <char>::size_type sizeStr1, lenStr1;  
   sizeStr1 = str1.size ( );  
   lenStr1 = str1.length ( );  
  
   basic_string <char>::size_type capStr1, max_sizeStr1;  
   capStr1 = str1.capacity ( );  
   max_sizeStr1 = str1.max_size ( );  
  
   // Compare size, length, capacity & max_size of a string  
   cout << "The current size of original string str1 is: "   
        << sizeStr1 << "." << endl;  
   cout << "The current length of original string str1 is: "   
        << lenStr1 << "." << endl;  
   cout << "The capacity of original string str1 is: "  
        << capStr1 << "." << endl;  
   cout << "The max_size of original string str1 is: "   
        << max_sizeStr1 << "." << endl << endl;  
  
   str1.erase ( 6, 5 );  
   cout << "The modified string str1 is: " << str1 << endl;  
  
   sizeStr1 = str1.size ( );  
   lenStr1 = str1.length ( );  
   capStr1 = str1.capacity ( );  
   max_sizeStr1 = str1.max_size ( );  
  
   // Compare size, length, capacity & max_size of a string  
   // after erasing part of the original string  
   cout << "The current size of modified string str1 is: "   
        << sizeStr1 << "." << endl;  
   cout << "The current length of modified string str1 is: "   
        << lenStr1 << "." << endl;  
   cout << "The capacity of modified string str1 is: "  
        << capStr1 << "." << endl;  
   cout << "The max_size of modified string str1 is: "   
        << max_sizeStr1 << "." << endl;  
}  
```  
  
##  <a name="npos"></a>  basic_string::npos  
 "Bulunamadı" ya da gösterir -1 veya "tüm geriye kalan karakterler" başlatılan bir işaretsiz tamsayı değer başarısız olduğunda bir arama işlevi.  
  
```  
static const size_type npos = -1;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri olduğunda denetlenecek `npos` değeri, onu çalışmayabilir dönüş değeri türü olmadıkça [size_type](#size_type) ve değil ya da `int` veya `unsigned`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [Bul](#find) bildirme ve kullanma konusunda bir örnek için `npos`.  
  
##  <a name="op_add_eq"></a>  basic_string::operator +=  
 Karakterleri dizeye ekler.  
  
```  
basic_string<CharType, Traits, Allocator>& operator+=(
    value_type _Ch);

basic_string<CharType, Traits, Allocator>& operator+=(
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& operator+=(
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Ch`  
 Eklenecek karakter.  
  
 `ptr`  
 Eklenecek C dizeyi karakter.  
  
 `right`  
 Eklenecek dizeyi karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üye işlevi tarafından geçirilen karakterlerle eklenen dize nesnesi referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 Karakter eklenmiş kullanarak bir dize `operator+=` veya üye işlevleri [sona](#append) veya [push_back](#push_back). `operator+=` Tek bağımsız değişkenli ekler birden fazla bağımsız değişken Ekle sırada üye işlevi değerleri eklemek için belirtilmesi için bir dizeyi belirli bir kısmını sağlar.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_op_app.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // The first member function  
   // appending a single character to a string  
   string str1a ( "Hello" );  
   cout << "The original string str1 is: " << str1a << endl;  
   str1a +=  '!' ;  
   cout << "The string str1 appended with an exclamation is: "   
        << str1a << endl << endl;  
  
   // The second member function  
   // appending a C-string to a string  
   string  str1b ( "Hello " );  
   const char *cstr1b = "Out There";  
   cout << "The C-string cstr1b is: " << cstr1b << endl;  
   str1b +=  cstr1b;  
   cout << "Appending the C-string cstr1b to string str1 gives: "   
        << str1b << "." << endl << endl;  
  
   // The third member function  
   // appending one string to another in two ways,  
   // comparing append and operator [ ]  
   string str1d ( "Hello " ), str2d ( "Wide " ), str3d ( "World" );  
   cout << "The string str2d is: " << str2d << endl;  
   str1d.append ( str2d );  
   cout << "The appended string str1d is: "   
        << str1d << "." << endl;  
   str1d += str3d;  
   cout << "The doubly appended strig str1 is: "   
        << str1d << "." << endl << endl;  
}  
```  
  
```Output  
The original string str1 is: Hello  
The string str1 appended with an exclamation is: Hello!  
  
The C-string cstr1b is: Out There  
Appending the C-string cstr1b to string str1 gives: Hello Out There.  
  
The string str2d is: Wide   
The appended string str1d is: Hello Wide .  
The doubly appended strig str1 is: Hello Wide World.  
```  
  
##  <a name="op_eq"></a>  basic_string::operator=  
 Yeni karakter değeri bir dize içeriğini atar.  
  
```  
basic_string<CharType, Traits, Allocator>& operator=(
    value_type _Ch);

basic_string<CharType, Traits, Allocator>& operator=(
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& operator=(
    const basic_string<CharType, Traits, Allocator>& right);

basic_string<CharType, Traits, Allocator>& operator=(
    const basic_string<CharType, Traits, Allocator>&& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Ch`  
 Atanacak karakter değeri.  
  
 `ptr`  
 Hedef dizeye atamayı C dize karakterlerini gösteren bir işaretçi.  
  
 `right`  
 Hedef dizeye atamayı karakterine olan kaynak dizesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üye işlevi tarafından atanan yeni karakter dizesi nesneye başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizeleri yeni karakter değerleri atanabilir. Yeni değer bir dize ve C dize veya tek bir karakter olabilir. `operator=` Yeni değer olabiliyorsa, kullanılabilir tek bir parametre tarafından aksi üye fonksiyonu açıklanan [atamak](#assign), birden çok parametre olan bir hedefe atanacak hangi dizesinin parçası olduğunu belirtmek için kullanılamaz dize.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_op_assign.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // The first member function assigning a  
   // character of a certain value to a string  
   string str1a ( "Hello " );  
   str1a = '0';  
   cout << "The string str1 assigned with the zero character is: "   
        << str1a << endl << endl;  
  
   // The second member function assigning the  
   // characters of a C-string to a string  
   string  str1b;  
   const char *cstr1b = "Out There";  
   cout << "The C-string cstr1b is: " << cstr1b <<  "." << endl;  
   str1b = cstr1b;  
   cout << "Assigning the C-string cstr1a to string str1 gives: "   
        << str1b << "." << endl << endl;  
  
   // The third member function assigning the characters  
   // from one string to another string in two equivalent  
   // ways, comparing the assign and operator =  
   string str1c ( "Hello" ), str2c ( "Wide" ), str3c ( "World" );  
   cout << "The original string str1 is: " << str1c << "." << endl;  
   cout << "The string str2c is: " << str2c << "." << endl;  
   str1c.assign ( str2c );  
   cout << "The string str1 newly assigned with string str2c is: "   
        << str1c << "." << endl;  
   cout << "The string str3c is: " << str3c << "." << endl;  
   str1c = str3c;  
   cout << "The string str1 reassigned with string str3c is: "   
        << str1c << "." << endl << endl;  
}  
```  
  
```Output  
The string str1 assigned with the zero character is: 0  
  
The C-string cstr1b is: Out There.  
Assigning the C-string cstr1a to string str1 gives: Out There.  
  
The original string str1 is: Hello.  
The string str2c is: Wide.  
The string str1 newly assigned with string str2c is: Wide.  
The string str3c is: World.  
The string str1 reassigned with string str3c is: World.  
```  
  
##  <a name="op_at"></a>  basic_string::operator[]  
 Belirtilen bir dizinden bir dizedeki karakter başvuru sağlar.  
  
```  
const_reference operator[](size_type _Off) const;  
reference operator[](size_type _Off);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Off`  
 Başvurulacak öğesinin konumu dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karakter dizesi parametresi dizini tarafından belirtilen konumdaki bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dizin sıfır dizenin ilk öğeye sahip ve aşağıdaki öğeleri art arda pozitif tamsayılar tarafından dizinlenen böylece bir dize uzunluğu *n* sahip bir *n*th öğesi dizine sayısı ile *n* - 1.  
  
 `operator[]` üye işlevini hızlıdır [adresindeki](#at) okuma ve yazma erişimi dizesinin öğelerine sağlamak için.  
  
 `operator[]` bir parametre olarak geçirilen dizini geçerli olup, ancak üye fonksiyonu denetlemez **adresindeki** yapar ve geçerlilik kullanılması gereken şekilde kesin değildir. Geçersiz bir dizin (sıfır bir dizin daha az dize boyutuna eşit veya daha büyük) üye işlevine geçirilen **adresindeki** oluşturur bir [out_of_range sınıfı](../standard-library/out-of-range-class.md) özel durum. Geçersiz dizin geçirilen `operator[]` sonuçlarında tanımsız davranışı, ancak dizini dize uzunluğu eşit const dizeleri için geçerli bir dizin ve işleç null bu dizini geçirildiğinde karakteri döndürür.  
  
 Başvuru döndürülen geçersiz dize adetle sınırla veya ilgili olmayan değişiklikleri **const** dizeleri.  
  
 İle derleme yapılırken [ \_YİNELEYİCİ\_hata ayıklama\_düzeyi](../standard-library/iterator-debug-level.md) dizesinin sınırları dışındaki bir öğe erişmeyi denerseniz, 1 veya 2 olarak ayarlanırsa, bir çalışma zamanı hatası meydana gelir. Daha fazla bilgi için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_op_ref.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   string str1 ( "Hello world" ), str2 ( "Goodbye world" );  
   const string cstr1 ( "Hello there" ), cstr2 ( "Goodbye now" );  
   cout << "The original string str1 is: " << str1 << endl;  
   cout << "The original string str2 is: " << str2 << endl;  
  
   // Element access to the non-const strings  
   basic_string <char>::reference refStr1 = str1 [6];  
   basic_string <char>::reference refStr2 = str2.at ( 3 );  
  
   cout << "The character with an index of 6 in string str1 is: "  
        << refStr1 << "." << endl;  
   cout << "The character with an index of 3 in string str2 is: "  
        << refStr2 << "." << endl;  
  
   // Element access to the const strings  
   basic_string <char>::const_reference crefStr1 = cstr1 [ cstr1.length ( ) ];  
   basic_string <char>::const_reference crefStr2 = cstr2.at ( 8 );  
  
   if ( crefStr1 == '\0' )  
      cout << "The null character is returned as a valid reference."  
           << endl;  
   else  
      cout << "The null character is not returned." << endl;  
   cout << "The character with index of 8 in the const string cstr2 is: "  
        << crefStr2 << "." << endl;  
}  
```  
  
##  <a name="pointer"></a>  basic_string::pointer  
 Bir işaretçi bir dize veya karakter dizisi karakter öğesinde sağlayan türü.  
  
```  
typedef typename allocator_type::pointer pointer;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türüdür **allocator_type::pointer**.  
  
 Türü için **dize**, eşdeğer olan **char\***.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_pointer.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   basic_string<char>::pointer pstr1a = "In Here";  
   char *cstr1b = "Out There";  
   cout << "The string pstr1a is: " << pstr1a <<  "." << endl;  
   cout << "The C-string cstr1b is: " << cstr1b << "." << endl;  
}  
```  
  
```Output  
The string pstr1a is: In Here.  
The C-string cstr1b is: Out There.  
```  
  
##  <a name="pop_back"></a>  basic_string::pop_back  
 Dizenin son öğe siler.  
  
```  
void pop_back();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi etkili bir şekilde çağırır `erase(size() - 1)` son öğe boş olmalıdır dizisi silmek için.  
  
##  <a name="push_back"></a>  basic_string::push_back  
 Bir öğeyi dize sonuna ekler.  
  
```  
void push_back(value_type _Ch);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Ch`  
 Dize sonuna eklenecek karakter.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini etkili bir şekilde çağırır [Ekle](#insert)( [son](#end), _ *Ch* ).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_push_back.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   string str1 ( "abc" );  
   basic_string <char>::iterator str_Iter, str1_Iter;  
  
   cout << "The original string str1 is: ";  
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )  
      cout << *str_Iter;  
   cout << endl;  
  
   // str1.push_back ( 'd' );  
   str1_Iter = str1.end ( );  
   str1_Iter--;  
   cout << "The last character-letter of the modified str1 is now: "  
        << *str1_Iter << endl;  
  
   cout << "The modified string str1 is: ";  
   for ( str_Iter = str1.begin( ); str_Iter != str1.end( ); str_Iter++ )  
      cout << *str_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The original string str1 is: abc  
The last character-letter of the modified str1 is now: c  
The modified string str1 is: abc  
```  
  
##  <a name="rbegin"></a>  basic_string::rbegin  
 Yineleyici ilk öğe ters bir dize döndürür.  
  
```  
const_reverse_iterator rbegin() const;

 
reverse_iterator rbegin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Rasgele erişim yineleyici ilk öğe ne karşılık gelen unreversed dize son öğesi olacağını adresleme ters bir dize döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `rbegin` ters bir dizeyle kullanılan gibi [başlamak](#begin) bir dizeyle kullanılır.  
  
 Varsa dönüş değerini `rbegin` atanmış bir `const_reverse_iterator`, dize nesnesi değiştirilemez. Varsa dönüş değerini `rbegin` atanmış bir `reverse_iterator`, dize nesnesi değiştirilebilir.  
  
 `rbegin` bir dize üzerinden yineleme geriye doğru başlatmak için kullanılabilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_rbegin.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   string str1 ( "Able was I ere I saw Elba" ), str2;  
   basic_string <char>::reverse_iterator str_rIter, str1_rIter, str2_rIter;  
   basic_string <char>::const_reverse_iterator str1_rcIter;  
  
   str1_rIter = str1.rbegin ( );  
   // str1_rIter--;  
   cout << "The first character-letter of the reversed string str1 is: "  
        << *str1_rIter << endl;  
   cout << "The full reversed string str1 is:\n ";  
   for ( str_rIter = str1.rbegin( ); str_rIter != str1.rend( ); str_rIter++ )  
      cout << *str_rIter;  
   cout << endl;  
  
   // The dereferenced iterator can be used to modify a character  
 *str1_rIter = 'A';  
   cout << "The first character-letter of the modified str1 is now: "  
        << *str1_rIter << endl;  
   cout << "The full modified reversed string str1 is now:\n ";  
   for ( str_rIter = str1.rbegin( ); str_rIter != str1.rend( ); str_rIter++ )  
      cout << *str_rIter;  
   cout << endl;  
  
   // The following line would be an error because iterator is const  
   // *str1_rcIter = 'A';  
  
   // For an empty string, begin is equivalent to end  
   if ( str2.rbegin( ) == str2.rend ( ) )  
      cout << "The string str2 is empty." << endl;  
   else  
      cout << "The stringstr2  is not empty." << endl;  
}  
```  
  
```Output  
The first character-letter of the reversed string str1 is: a  
The full reversed string str1 is:  
 ablE was I ere I saw elbA  
The first character-letter of the modified str1 is now: A  
The full modified reversed string str1 is now:  
 AblE was I ere I saw elbA  
The string str2 is empty.  
```  
  
##  <a name="reference"></a>  basic_string::reference  
 Bir dizede depolanan bir öğe için bir başvuru sağlar türü.  
  
```  
typedef typename allocator_type::reference reference;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür **başvuru** bir öğenin değerini değiştirmek için kullanılabilir.  
  
 Eşanlamlısı türüdür **allocator_type::reference**.  
  
 Türü için **dize**, eşdeğer olan **chr &**.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [adresindeki](#at) bildirme ve kullanma konusunda bir örnek için **başvuru**.  
  
##  <a name="rend"></a>  basic_string::rend  
 Ters dize son öğesi başarılı konumu adresleri yineleyici döndürür.  
  
```  
const_reverse_iterator rend() const;

 
reverse_iterator rend();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ters dize son öğesi başarılı konumu adresleri ters rasgele erişim yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 `rend` ters bir dizeyle kullanılan gibi [son](#end) bir dizeyle kullanılır.  
  
 Varsa dönüş değerini `rend` atanmış bir `const_reverse_iterator`, dize nesnesi değiştirilemez. Varsa dönüş değerini `rend` atanmış bir `reverse_iterator`, dize nesnesi değiştirilebilir.  
  
 `rend` Ters yineleyici alt dizenin sonuna ulaştı olup olmadığını test etmek için kullanılabilir.  
  
 Tarafından döndürülen değer `rend` değil başvuru yapıldı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_rend.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   string str1 ("Able was I ere I saw Elba"), str2;  
   basic_string <char>::reverse_iterator str_rIter, str1_rIter, str2_rIter;  
   basic_string <char>::const_reverse_iterator str1_rcIter;  
  
   str1_rIter = str1.rend ( );  
   str1_rIter--;  
   cout << "The last character-letter of the reversed string str1 is: "  
        << *str1_rIter << endl;  
   cout << "The full reversed string str1 is:\n ";  
   for ( str_rIter = str1.rbegin( ); str_rIter != str1.rend( ); str_rIter++ )  
      cout << *str_rIter;  
   cout << endl;  
  
   // The dereferenced iterator can be used to modify a character  
 *str1_rIter = 'o';  
   cout << "The last character-letter of the modified str1 is now: "  
        << *str1_rIter << endl;  
   cout << "The full modified reversed string str1 is now:\n ";  
   for ( str_rIter = str1.rbegin( ); str_rIter != str1.rend( ); str_rIter++ )  
      cout << *str_rIter;  
   cout << endl;  
  
   // The following line would be an error because iterator is const  
   // *str1_rcIter = 'T';  
  
   // For an empty string, end is equivalent to begin  
   if ( str2.rbegin( ) == str2.rend ( ) )  
      cout << "The string str2 is empty." << endl;  
   else  
      cout << "The stringstr2  is not empty." << endl;  
}  
```  
  
```Output  
The last character-letter of the reversed string str1 is: A  
The full reversed string str1 is:  
 ablE was I ere I saw elbA  
The last character-letter of the modified str1 is now: o  
The full modified reversed string str1 is now:  
 ablE was I ere I saw elbo  
The string str2 is empty.  
```  
  
##  <a name="replace"></a>  basic_string::Replace  
 Belirtilen veya diğer aralıkları veya dizeler veya C dizeleri kopyalanan karakter ile belirtilen konumda bir dizedeki öğeleri değiştirir.  
  
```  
basic_string<CharType, Traits, Allocator>& replace(
    size_type _Pos1,   
    size_type _Num1,  
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& replace(
    size_type _Pos1,   
    size_type _Num1,  
    const basic_string<CharType, Traits, Allocator>& str);

basic_string<CharType, Traits, Allocator>& replace(
    size_type _Pos1,   
    size_type _Num1,  
    const value_type* ptr,   
    size_type _Num2);

basic_string<CharType, Traits, Allocator>& replace(
    size_type _Pos1,   
    size_type _Num1,  
    const basic_string<CharType, Traits, Allocator>& str,   
    size_type _Pos2,   
    size_type _Num2);

basic_string<CharType, Traits, Allocator>& replace(
    size_type _Pos1,   
    size_type _Num1,  
    size_type count,   
    value_type _Ch);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,   
    iterator last0,  
    const value_type* ptr);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,   
    iterator last0,  
    const basic_string<CharType, Traits, Allocator>& str);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,  
    iterator last0,  
    const value_type* ptr,   
    size_type _Num2);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,   
    iterator last0,  
    size_type _Num2,   
    value_type _Ch);

template <class InputIterator>  
basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,   
    iterator last0,  
    InputIterator first,   
    InputIterator last);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,  
    iterator last0,  
    const_pointer first,  
    const_pointer last);

basic_string<CharType, Traits, Allocator>& replace(
    iterator first0,  
    iterator last0,  
    const_iterator first,  
    const_iterator last);
```  
  
### <a name="parameters"></a>Parametreler  
 `str`  
 Karakter işleneni dize için bir kaynak olacak dize.  
  
 `_Pos1`  
 Hangi değiştirme başlar işleneni dize dizini.  
  
 `_Num1`  
 İşlenen dizesinde değiştirilecek karakterler maksimum sayısı.  
  
 *_Pos2*  
 Hangi kopyalamaya başlar parametre dizesi dizini.  
  
 `_Num2`  
 C-string parametresinden kullanılacak karakter sayısı.  
  
 `ptr`  
 C-karakter işleneni dize için bir kaynak olarak dize.  
  
 `_Ch`  
 İşlenen dizeye kopyalanacak karakter.  
  
 * first0*  
 İşlenen dizesinde kaldırılacak ilk karakter adresleme yineleyici.  
  
 * last0*  
 İşlenen dizesinde kaldırılacak son karakter adresleme yineleyici.  
  
 `first`  
 Bir Yineleyici, const_pointer veya ilk karakter adresleme const_iterator parametresi dizesinde kopyalanacak.  
  
 `last`  
 Bir Yineleyici, const_pointer veya son karakter adresleme const_iterator parametresi dizesinde kopyalanacak.  
  
 `count`  
 Kaç kez `_Ch` işlenen dizesine kopyalanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlenen dizesi ile yapılan değiştirme.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_replace.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // The first two member functions replace  
   // part of the operand string with  
   // characters from a parameter string or C-string  
   string result1a, result1b;  
   string s1o ( "AAAAAAAA" );  
   string s1p ( "BBB" );  
   const char* cs1p = "CCC";  
   cout << "The operand string s1o is: " << s1o << endl;  
   cout << "The parameter string s1p is: " << s1p << endl;  
   cout << "The parameter C-string cs1p is: " << cs1p << endl;  
   result1a = s1o.replace ( 1 , 3 , s1p );  
   cout << "The result of s1o.replace ( 1 , 3 , s1p )\n is "   
        << "the string: " << result1a << "." << endl;  
   result1b = s1o.replace ( 5 , 3 , cs1p );  
   cout << "The result of s1o.replace ( 5 , 3 , cs1p )\n is "   
        << "the string: " << result1b << "." << endl;  
   cout << endl;  
  
   // The third & fourth member function replace  
   // part of the operand string with characters  
   // form part of a parameter string or C-string  
   string result2a, result2b;  
   string s2o ( "AAAAAAAA" );  
   string s2p ( "BBB" );  
   const char* cs2p = "CCC";  
   cout << "The operand string s2o is: " << s2o << endl;  
   cout << "The parameter string s1p is: " << s2p << endl;  
   cout << "The parameter C-string cs2p is: " << cs2p << endl;  
   result2a = s2o.replace ( 1 , 3 , s2p , 1 , 2 );  
   cout << "The result of s2o.replace (1, 3, s2p, 1, 2)\n is "   
        << "the string: " << result2a << "." << endl;  
   result2b = s2o.replace ( 4 , 3 , cs2p , 1 );  
   cout << "The result of s2o.replace (4 ,3 ,cs2p)\n is "   
        << "the string: " << result2b << "." << endl;  
   cout << endl;  
  
   // The fifth member function replaces  
   // part of the operand string with characters  
   string result3a;  
   string s3o ( "AAAAAAAA" );  
   char ch3p = 'C';  
   cout << "The operand string s3o is: " << s3o << endl;  
   cout << "The parameter character c1p is: " << ch3p << endl;  
   result3a = s3o.replace ( 1 , 3 , 4 , ch3p );  
   cout << "The result of s3o.replace(1, 3, 4, ch3p)\n is "   
        << "the string: " << result3a << "." << endl;  
   cout << endl;  
  
   // The sixth & seventh member functions replace  
   // part of the operand string, delineated with iterators,  
   // with a parameter string or C-string  
   string s4o ( "AAAAAAAA" );  
   string s4p ( "BBB" );  
   const char* cs4p = "CCC";  
   cout << "The operand string s4o is: " << s4o << endl;  
   cout << "The parameter string s4p is: " << s4p << endl;  
   cout << "The parameter C-string cs4p is: " << cs4p << endl;  
   basic_string<char>::iterator IterF0, IterL0;  
   IterF0 = s4o.begin ( );  
   IterL0 = s4o.begin ( ) + 3;  
   string result4a, result4b;  
   result4a = s4o.replace ( IterF0 , IterL0 , s4p );  
   cout << "The result of s1o.replace (IterF0, IterL0, s4p)\n is "   
        << "the string: " << result4a << "." << endl;  
   result4b = s4o.replace ( IterF0 , IterL0 , cs4p );  
   cout << "The result of s4o.replace (IterF0, IterL0, cs4p)\n is "   
        << "the string: " << result4b << "." << endl;  
   cout << endl;  
  
   // The 8th member function replaces  
   // part of the operand string delineated with iterators  
   // with a number of characters from a parameter C-string  
   string s5o ( "AAAAAAAF" );  
   const char* cs5p = "CCCBB";  
   cout << "The operand string s5o is: " << s5o << endl;  
   cout << "The parameter C-string cs5p is: " << cs5p << endl;  
   basic_string<char>::iterator IterF1, IterL1;  
   IterF1 = s5o.begin ( );  
   IterL1 = s5o.begin ( ) + 4;  
   string result5a;  
   result5a = s5o.replace ( IterF1 , IterL1 , cs5p , 4 );  
   cout << "The result of s5o.replace (IterF1, IterL1, cs4p ,4)\n is "   
        << "the string: " << result5a << "." << endl;  
   cout << endl;  
  
   // The 9th member function replaces  
   // part of the operand string delineated with iterators  
   // with specified characters  
   string s6o ( "AAAAAAAG" );  
   char ch6p = 'q';  
   cout << "The operand string s6o is: " << s6o << endl;  
   cout << "The parameter character ch6p is: " << ch6p << endl;  
   basic_string<char>::iterator IterF2, IterL2;  
   IterF2 = s6o.begin ( );  
   IterL2 = s6o.begin ( ) + 3;  
   string result6a;  
   result6a = s6o.replace ( IterF2 , IterL2 , 4 , ch6p );  
   cout << "The result of s6o.replace (IterF1, IterL1, 4, ch6p)\n is "   
        << "the string: " << result6a << "." << endl;  
   cout << endl;  
  
   // The 10th member function replaces  
   // part of the operand string delineated with iterators  
   // with part of a parameter string delineated with iterators  
   string s7o ( "OOOOOOO" );  
   string s7p ( "PPPP" );  
   cout << "The operand string s7o is: " << s7o << endl;  
   cout << "The parameter string s7p is: " << s7p << endl;  
   basic_string<char>::iterator IterF3, IterL3, IterF4, IterL4;  
   IterF3 = s7o.begin ( ) + 1;  
   IterL3 = s7o.begin ( ) + 3;  
   IterF4 = s7p.begin ( );  
   IterL4 = s7p.begin ( ) + 2;  
   string result7a;  
   result7a = s7o.replace ( IterF3 , IterL3 , IterF4 , IterL4 );  
   cout << "The result of s7o.replace (IterF3 ,IterL3 ,IterF4 ,IterL4)\n is "   
        << "the string: " << result7a << "." << endl;  
   cout << endl;  
}  
```  
  
```Output  
The operand string s1o is: AAAAAAAA  
The parameter string s1p is: BBB  
The parameter C-string cs1p is: CCC  
The result of s1o.replace ( 1 , 3 , s1p )  
 is the string: ABBBAAAA.  
The result of s1o.replace ( 5 , 3 , cs1p )  
 is the string: ABBBACCC.  
  
The operand string s2o is: AAAAAAAA  
The parameter string s1p is: BBB  
The parameter C-string cs2p is: CCC  
The result of s2o.replace (1, 3, s2p, 1, 2)  
 is the string: ABBAAAA.  
The result of s2o.replace (4 ,3 ,cs2p)  
 is the string: ABBAC.  
  
The operand string s3o is: AAAAAAAA  
The parameter character c1p is: C  
The result of s3o.replace(1, 3, 4, ch3p)  
 is the string: ACCCCAAAA.  
  
The operand string s4o is: AAAAAAAA  
The parameter string s4p is: BBB  
The parameter C-string cs4p is: CCC  
The result of s1o.replace (IterF0, IterL0, s4p)  
 is the string: BBBAAAAA.  
The result of s4o.replace (IterF0, IterL0, cs4p)  
 is the string: CCCAAAAA.  
  
The operand string s5o is: AAAAAAAF  
The parameter C-string cs5p is: CCCBB  
The result of s5o.replace (IterF1, IterL1, cs4p ,4)  
 is the string: CCCBAAAF.  
  
The operand string s6o is: AAAAAAAG  
The parameter character ch6p is: q  
The result of s6o.replace (IterF1, IterL1, 4, ch6p)  
 is the string: qqqqAAAAG.  
  
The operand string s7o is: OOOOOOO  
The parameter string s7p is: PPPP  
The result of s7o.replace (IterF3 ,IterL3 ,IterF4 ,IterL4)  
 is the string: OPPOOOO.  
```  
  
##  <a name="reserve"></a>  basic_string::reserve  
 Dize kapasitesini sayıyı en az olarak harika bir belirtilen sayı olarak ayarlar.  
  
```  
void reserve(size_type count = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `count`  
 Bellek ayrılan karakter sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Adetle sınırla zaman alan bir işlem olduğundan ve tüm başvuruları, işaretçiler ve bir dizedeki karakter başvurmak yineleyiciler geçersiz kılar, yeterli kapasitesi sahip olmak önemlidir.  
  
 Türü dizeler nesneleri için kapasite kavramı türü vektör nesnelerin ile aynıdır. Vektör, üye fonksiyonu aksine **yedek** nesneyi kapasitesini daraltmak için çağrılabilir. İstek nonbinding ve olabilir veya değil oluşabilir. Varsayılan olarak parametresi için değer, bir çağrı sıfırdır **yedek** dize kapasitesini karakter sayısını şu anda dizesinde uyacak şekilde daraltma bağlanmayan isteğidir. Kapasite geçerli karakter sayısını hiçbir zaman azalır.  
  
 Çağırma `reserve` bir dize kapasitesini daraltmak için yalnızca olası bir yoludur. Ancak, yukarıda belirtildiği gibi bu isteğidir nonbinding ve değil oluşabilir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_reserve.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   string str1 ("Hello world");  
   cout << "The original string str1 is: " << str1 << endl;  
  
   basic_string <char>::size_type sizeStr1, sizerStr1;  
   sizeStr1 = str1.size ( );  
   basic_string <char>::size_type capStr1, caprStr1;  
   capStr1 = str1.capacity ( );  
  
   // Compare size & capacity of the original string  
   cout << "The current size of original string str1 is: "   
        << sizeStr1 << "." << endl;  
   cout << "The capacity of original string str1 is: "  
        << capStr1 << "." << endl << endl;  
  
   // Compare size & capacity of the string  
   // with added capacity  
   str1.reserve ( 40 );  
   sizerStr1 = str1.size ( );  
   caprStr1 = str1.capacity ( );  
  
   cout << "The string str1with augmented capacity is: "  
        << str1 << endl;  
   cout << "The current size of string str1 is: "   
        << sizerStr1 << "." << endl;  
   cout << "The new capacity of string str1 is: "  
        << caprStr1 << "." << endl << endl;  
  
   // Compare size & capacity of the string  
   // with downsized capacity  
   str1.reserve ( );  
   basic_string <char>::size_type sizedStr1;  
   basic_string <char>::size_type capdStr1;  
   sizedStr1 = str1.size ( );  
   capdStr1 = str1.capacity ( );  
  
   cout << "The string str1 with downsized capacity is: "  
        << str1 << endl;  
   cout << "The current size of string str1 is: "   
        << sizedStr1 << "." << endl;  
   cout << "The reduced capacity of string str1 is: "  
        << capdStr1 << "." << endl << endl;  
}  
```  
  
```Output  
The original string str1 is: Hello world  
The current size of original string str1 is: 11.  
The capacity of original string str1 is: 15.  
  
The string str1with augmented capacity is: Hello world  
The current size of string str1 is: 11.  
The new capacity of string str1 is: 47.  
  
The string str1 with downsized capacity is: Hello world  
The current size of string str1 is: 11.  
The reduced capacity of string str1 is: 47.  
```  
  
##  <a name="resize"></a>  basic_string::Resize  
 Bir dize ekleme veya silmeyi gerektiği gibi öğeleri için yeni bir boyutunu belirtir.  
  
```  
void resize(
    size_type count,);

void resize(
    size_type count,  
    _Elem _Ch);
```  
  
### <a name="parameters"></a>Parametreler  
 `count`  
 Dize yeni boyutu.  
  
 `_Ch`  
 Karakterler değeri başlatılır ile ek öğeler gerekiyorsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonuçta elde edilen boyutu en fazla karakter sayısını aşarsa, formun oluşturur `length_error`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_resize.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   string  str1 ( "Hello world" );  
   cout << "The original string str1 is: " << str1 << endl;  
  
   basic_string <char>::size_type sizeStr1;  
   sizeStr1 = str1.size ( );  
   basic_string <char>::size_type capStr1;  
   capStr1 = str1.capacity ( );  
  
   // Compare size & capacity of the original string  
   cout << "The current size of original string str1 is: "   
        << sizeStr1 << "." << endl;  
   cout << "The capacity of original string str1 is: "  
        << capStr1 << "." << endl << endl;  
  
   // Use resize to increase size by 2 elements: exclamations  
   str1.resize ( str1.size ( ) + 2 , '!' );  
   cout << "The resized string str1 is: " << str1 << endl;  
  
   sizeStr1 = str1.size ( );  
   capStr1 = str1.capacity ( );  
  
   // Compare size & capacity of a string after resizing  
   cout << "The current size of resized string str1 is: "   
        << sizeStr1 << "." << endl;  
   cout << "The capacity of resized string str1 is: "  
        << capStr1 << "." << endl << endl;  
  
   // Use resize to increase size by 20 elements:  
   str1.resize ( str1.size ( ) + 20 );  
   cout << "The resized string str1 is: " << str1 << endl;  
  
   sizeStr1 = str1.size ( );  
   capStr1 = str1.capacity ( );  
  
   // Compare size & capacity of a string after resizing  
   // note capacity increases automatically as required  
   cout << "The current size of modified string str1 is: "   
        << sizeStr1 << "." << endl;  
   cout << "The capacity of modified string str1 is: "  
        << capStr1 << "." << endl << endl;  
  
   // Use resize to downsize by 28 elements:  
   str1.resize ( str1.size ( ) - 28 );  
   cout << "The downsized string str1 is: " << str1 << endl;  
  
   sizeStr1 = str1.size (  );  
   capStr1 = str1.capacity (  );  
  
   // Compare size & capacity of a string after downsizing  
   cout << "The current size of downsized string str1 is: "   
        << sizeStr1 << "." << endl;  
   cout << "The capacity of downsized string str1 is: "  
        << capStr1 << "." << endl;  
}  
```  
  
```Output  
The original string str1 is: Hello world  
The current size of original string str1 is: 11.  
The capacity of original string str1 is: 15.  
  
The resized string str1 is: Hello world!!  
The current size of resized string str1 is: 13.  
The capacity of resized string str1 is: 15.  
  
The resized string str1 is: Hello world!!                      
The current size of modified string str1 is: 33.  
The capacity of modified string str1 is: 47.  
  
The downsized string str1 is: Hello  
The current size of downsized string str1 is: 5.  
The capacity of downsized string str1 is: 47.  
```  
  
##  <a name="reverse_iterator"></a>  basic_string::reverse_iterator  
 Bir dizede depolanan bir öğe için bir başvuru sağlar türü.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tür `reverse_iterator` bir karakterin değerini değiştirmek için kullanılabilir ve geriye doğru dizesinde yinelemek için kullanılır.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [rbegin](#rbegin) bildirme ve kullanma konusunda bir örnek için `reverse_iterator`.  
  
##  <a name="rfind"></a>  basic_string::rfind  
 Bir dizeyi belirtilen bir karakter dizisi eşleşen bir alt dizenin ilk a geçişi için geriye dönük bir yönde arar.  
  
```  
size_type rfind(
    value_type _Ch,   
    size_type _Off = npos) const;

 
size_type rfind(
    const value_type* ptr,  
    size_type _Off = npos) const;

 
size_type rfind(
    const value_type* ptr,   
    size_type _Off,  
    size_type count) const;

 
size_type rfind(
    const basic_string<CharType, Traits, Allocator>& str,  
    size_type _Off = npos) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Ch`  
 Üye işlevini aranacak olduğu karakter değeri.  
  
 `_Off`  
 Başlamak için arama olduğu konumu dizini.  
  
 `ptr`  
 C-üye fonksiyonu aranacak olduğu dize.  
  
 `count`  
 Üye işlevi aranacak olduğu C-dizesindeki ilk karakter İleri sayım karakter sayısı.  
  
 `str`  
 Üye işlevini aranacak olduğu dizesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geriye doğru arama başarılı olduğunda dizenin ilk karakteri, son a geçişi, dizin; Aksi takdirde `npos`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_rfind.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // The first member function  
   // searches for a single character in a string  
   string str1 ( "Hello Everyone" );  
   cout << "The original string str1 is: " << str1 << endl;  
   basic_string <char>::size_type indexCh1a, indexCh1b;  
   static const basic_string <char>::size_type npos = -1;  
  
   indexCh1a = str1.rfind ( "e" , 9 );  
   if ( indexCh1a != npos )  
      cout << "The index of the 1st 'e' found before the 9th"  
           << " position in str1 is: " << indexCh1a << endl;  
   else  
      cout << "The character 'e' was not found in str1 ." << endl;  
  
   indexCh1b = str1.rfind ( "x" );  
   if ( indexCh1b != npos )  
      cout << "The index of the 'x' found in str1 is: "  
           << indexCh1b << endl << endl;  
   else  
      cout << "The character 'x' was not found in str1."  
           << endl << endl;  
  
   // The second member function searches a string  
   // for a substring as specified by a C-string  
   string str2 ( "Let me make this perfectly clear." );  
   cout << "The original string str2 is: " << str2 << endl;  
   basic_string <char>::size_type indexCh2a, indexCh2b;  
  
   const char *cstr2 = "perfect";  
   indexCh2a = str2.rfind ( cstr2 , 30 );  
   if ( indexCh2a != npos )  
      cout << "The index of the 1st element of 'perfect' "  
           << "before\n the 30th position in str2 is: "  
           << indexCh2a << endl;  
   else  
      cout << "The substring 'perfect' was not found in str2 ."  
           << endl;  
  
   const char *cstr2b = "imperfectly";  
   indexCh2b = str2.rfind ( cstr2b , 30 );  
   if ( indexCh2b != npos )  
      cout << "The index of the 1st element of 'imperfect' "  
           << "before\n the 5th position in str3 is: "  
           << indexCh2b << endl;  
   else  
      cout << "The substring 'imperfect' was not found in str2 ."  
           << endl << endl;  
  
   // The third member function searches a string  
   // for a substring as specified by a C-string  
   string str3 ( "It is a nice day. I am happy." );  
   cout << "The original string str3 is: " << str3 << endl;  
   basic_string <char>::size_type indexCh3a, indexCh3b;  
  
   const char *cstr3a = "nice";  
   indexCh3a = str3.rfind ( cstr3a );  
   if ( indexCh3a != npos )  
      cout << "The index of the 1st element of 'nice' "  
           << "in str3 is: " << indexCh3a << endl;  
   else  
      cout << "The substring 'nice' was not found in str3 ."  
           << endl;  
  
   const char *cstr3b = "am";  
   indexCh3b = str3.rfind ( cstr3b , indexCh3a + 25 , 2 );  
   if ( indexCh3b != npos )  
      cout << "The index of the next occurrance of 'am' in "  
           << "str3 begins at: " << indexCh3b << endl << endl;  
   else  
      cout << "There is no next occurrence of 'am' in str3 ."  
           << endl << endl;  
  
   // The fourth member function searches a string  
   // for a substring as specified by a string  
   string str4 ( "This perfectly unclear." );  
   cout << "The original string str4 is: " << str4 << endl;  
   basic_string <char>::size_type indexCh4a, indexCh4b;  
  
   string str4a ( "clear" );  
   indexCh4a = str4.rfind ( str4a , 15 );  
   if (indexCh4a != npos )  
      cout << "The index of the 1st element of 'clear' "  
           << "before\n the 15th position in str4 is: "  
           << indexCh4a << endl;  
   else  
      cout << "The substring 'clear' was not found in str4 "  
           << "before the 15th position." << endl;  
  
   string str4b ( "clear" );  
   indexCh4b = str4.rfind ( str4b );  
   if ( indexCh4b != npos )  
      cout << "The index of the 1st element of 'clear' "  
           << "in str4 is: "  
           << indexCh4b << endl;  
   else  
      cout << "The substring 'clear' was not found in str4 ."  
           << endl << endl;  
}  
```  
  
```Output  
The original string str1 is: Hello Everyone  
The index of the 1st 'e' found before the 9th position in str1 is: 8  
The character 'x' was not found in str1.  
  
The original string str2 is: Let me make this perfectly clear.  
The index of the 1st element of 'perfect' before  
 the 30th position in str2 is: 17  
The substring 'imperfect' was not found in str2 .  
  
The original string str3 is: It is a nice day. I am happy.  
The index of the 1st element of 'nice' in str3 is: 8  
The index of the next occurrance of 'am' in str3 begins at: 20  
  
The original string str4 is: This perfectly unclear.  
The substring 'clear' was not found in str4 before the 15th position.  
The index of the 1st element of 'clear' in str4 is: 17  
```  
  
##  <a name="shrink_to_fit"></a>  basic_string::shrink_to_fit  
 Dizenin fazlalık kapasite atar.  
  
```  
void shrink_to_fit();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi kapsayıcıdaki tüm gereksiz depolama ortadan kaldırır.  
  
##  <a name="size"></a>  basic_string::size  
 Öğelerin geçerli bir dize döndürür.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dize uzunluğu.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_size.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   string str1 ("Hello world");  
   cout << "The original string str1 is: " << str1 << endl;  
  
   // The size and length member functions differ in name only  
   basic_string <char>::size_type sizeStr1, lenStr1;  
   sizeStr1 = str1.size (  );  
   lenStr1 = str1.length (  );  
  
   basic_string <char>::size_type capStr1, max_sizeStr1;  
   capStr1 = str1.capacity (  );  
   max_sizeStr1 = str1.max_size (  );  
  
   // Compare size, length, capacity & max_size of a string  
   cout << "The current size of original string str1 is: "   
        << sizeStr1 << "." << endl;  
   cout << "The current length of original string str1 is: "   
        << lenStr1 << "." << endl;  
   cout << "The capacity of original string str1 is: "  
        << capStr1 << "." << endl;  
   cout << "The max_size of original string str1 is: "   
        << max_sizeStr1 << "." << endl << endl;  
  
   str1.erase ( 6, 5 );  
   cout << "The modified string str1 is: " << str1 << endl;  
  
   sizeStr1 = str1.size ( );  
   lenStr1 = str1.length ( );  
   capStr1 = str1.capacity ( );  
   max_sizeStr1 = str1.max_size ( );  
  
   // Compare size, length, capacity & max_size of a string  
   // after erasing part of the original string  
   cout << "The current size of modified string str1 is: "   
        << sizeStr1 << "." << endl;  
   cout << "The current length of modified string str1 is: "   
        << lenStr1 << "." << endl;  
   cout << "The capacity of modified string str1 is: "  
        << capStr1 << "." << endl;  
   cout << "The max_size of modified string str1 is: "   
        << max_sizeStr1 << "." << endl;  
}  
```  
  
##  <a name="size_type"></a>  basic_string::size_type  
 Öğeleri ve bir dizede dizinlerini sayısını temsil eden bir işaretsiz tamsayı türü.  
  
```  
typedef typename allocator_type::size_type size_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşdeğer olan **allocator_type::size_type**.  
  
 Türü için **dize**, eşdeğer olan **size_t**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_size_type.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   string str1 ( "Hello world" );  
  
   basic_string <char>::size_type sizeStr1, capStr1;  
   sizeStr1 = str1.size (  );  
   capStr1 = str1.capacity (  );  
  
   cout << "The current size of string str1 is: "   
        << sizeStr1 << "." << endl;  
   cout << "The capacity of string str1 is: " << capStr1   
         << "." << endl;  
}  
```  
  
```Output  
The current size of string str1 is: 11.  
The capacity of string str1 is: 15.  
```  
  
##  <a name="substr"></a>  basic_string::SUBSTR  
 Bir dizenin karakter sayısı en çok bazı belirtilen konuma dize baştan kopyalar.  
  
```  
basic_string<CharType, Traits, Allocator> substr(
    size_type _Off = 0,  
    size_type count = npos) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Off`  
 Bir dizin öğesi, dize, varsayılan değeri 0 ile kopyası oluşturulur konumunda bulunuyor.  
  
 `count`  
 Mevcut olup olmadığını kopyalanacak karakter sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk bağımsız değişkeni tarafından belirtilen konumdaki dize işleneni başında öğelerinin bir kopyasını bir alt dize nesnesi.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_substr.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   string  str1 ("Heterological paradoxes are persistent.");  
   cout << "The original string str1 is: \n " << str1  
        << endl << endl;  
  
   basic_string <char> str2 = str1.substr ( 6 , 7 );  
   cout << "The substring str1 copied is: " << str2  
        << endl << endl;  
  
   basic_string <char> str3 = str1.substr (  );  
   cout << "The default substring str3 is: \n " << str3  
        <<  "\n which is the entire original string." << endl;  
}  
```  
  
```Output  
The original string str1 is:   
 Heterological paradoxes are persistent.  
  
The substring str1 copied is: logical  
  
The default substring str3 is:   
 Heterological paradoxes are persistent.  
 which is the entire original string.  
```  
  
##  <a name="swap"></a>  basic_string::Swap  
 İki dizeyi içeriğini exchange.  
  
```  
void swap(
    basic_string<CharType, Traits, Allocator>& str);
```  
  
### <a name="parameters"></a>Parametreler  
 `str`  
 Hedef dize de ile değiştirilmek üzere öğeleri olan kaynak dizesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Değiştiriliyor dizeleri aynı ayırıcısı nesneniz varsa `swap` üye fonksiyonu:  
  
-   Sabit zamanında oluşur.  
  
-   Hiçbir özel durum oluşturur.  
  
-   Hiçbir başvuruları, işaretçileri veya iki dizeyi öğelerinde tanımladığınız yineleyiciler geçersiz kılar.  
  
 Aksi durumda, iki denetimli sıralarında öğesi atamaları ve oluşturucu çağrıları öğe sayısını orantılı çeşitli gerçekleştirir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_swap.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "Tweedledee" );  
   string s2 ( "Tweedledum" );  
   cout << "Before swapping string s1 and s2:" << endl;  
   cout << " The basic_string s1 = " << s1 << "." << endl;  
   cout << " The basic_string s2 = " << s2 << "." << endl;  
  
   s1.swap ( s2 );  
   cout << "After swapping string s1 and s2:" << endl;  
   cout << " The basic_string s1 = " << s1 << "." << endl;  
   cout << " The basic_string s2 = " << s2 << "." << endl;  
}  
```  
  
```Output  
Before swapping string s1 and s2:  
 The basic_string s1 = Tweedledee.  
 The basic_string s2 = Tweedledum.  
After swapping string s1 and s2:  
 The basic_string s1 = Tweedledum.  
 The basic_string s2 = Tweedledee.  
```  
  
##  <a name="traits_type"></a>  basic_string::traits_type  
 Bir dizede depolanan öğelerin türü karakter özellikleri için.  
  
```  
typedef Traits traits_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İkinci şablon parametresi için bir eş anlamlı türüdür **nitelikler**.  
  
 Türü için **dize**, eşdeğer olan **char_traits\<char >**.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [kopya](../standard-library/char-traits-struct.md#copy) bildirme ve kullanma konusunda bir örnek için `traits_type`.  
  
##  <a name="value_type"></a>  basic_string::value_type  
 Karakter dizesi içinde depolanan türünü temsil eden tür.  
  
```  
typedef typename allocator_type::value_type value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşdeğer olan **traits_type::char_type** ve eşdeğerdir `char` türündeki nesneler için **dize**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// basic_string_value_type.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   basic_string<char>::value_type ch1 = 'G';  
  
   char ch2 = 'H';  
  
   cout << "The character ch1 is: " << ch1 << "." << endl;  
   cout << "The character ch2 is: " << ch2 << "." << endl;  
}  
```  
  
```Output  
The character ch1 is: G.  
The character ch2 is: H.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<dize >](../standard-library/string.md)   
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

