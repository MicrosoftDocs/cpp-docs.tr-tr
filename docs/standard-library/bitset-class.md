---
title: "bitset sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- bitset/std::bitset
- bitset/std::bitset::element_type
- bitset/std::bitset::all
- bitset/std::bitset::any
- bitset/std::bitset::count
- bitset/std::bitset::flip
- bitset/std::bitset::none
- bitset/std::bitset::reset
- bitset/std::bitset::set
- bitset/std::bitset::size
- bitset/std::bitset::test
- bitset/std::bitset::to_string
- bitset/std::bitset::to_ullong
- bitset/std::bitset::to_ulong
- bitset/std::bitset::reference
dev_langs: C++
helpviewer_keywords:
- std::bitset [C++]
- std::bitset [C++], element_type
- std::bitset [C++], all
- std::bitset [C++], any
- std::bitset [C++], count
- std::bitset [C++], flip
- std::bitset [C++], none
- std::bitset [C++], reset
- std::bitset [C++], set
- std::bitset [C++], size
- std::bitset [C++], test
- std::bitset [C++], to_string
- std::bitset [C++], to_ullong
- std::bitset [C++], to_ulong
- std::bitset [C++], reference
ms.assetid: 28b86964-87b4-429c-8124-b6c251b6c50b
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 542be13898b18fb6f73a724eebe72f135f7ebde2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="bitset-class"></a>bitset Sınıfı
Sabit sayıda bayrakları öğeler veya koşullar kümesi için koruma altında tutmada kısa bir yol sağlamak bitten oluşan bir dizi depolar nesnesi türünü açıklar. Bitset sınıfı her bit sabiti zamanı erişim sağlamak ve BITS koleksiyonunu içeren türü bitset nesnelerin işlemlerini destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <size_t N>  
class bitset  
```  
  
#### <a name="parameters"></a>Parametreler  
 *N*  
 Bit sayısını sıfır olmayan bir tamsayı türünde bitset nesnesiyle belirtir **size_t** , gerekir bilinir derleme zamanında.  
  
## <a name="remarks"></a>Açıklamalar  
 Benzer aksine [vektör\<bool > sınıfı](../standard-library/vector-bool-class.md), bitset sınıfı yineleyiciler yok ve C++ Standart Kitaplığı kapsayıcı değil. Ayrıca öğesinden farklı\<bool > şablon parametresi tarafından belirtilen boyut uygun olarak derleme zamanında sabit bazı belirli büyüklükte olma tarafından **N** zaman **bitset\<N\>**  bildirilmedi.  
  
 Bir bit değeri 1 ise ve değeri 0 ise sıfırlayın. Çevirme veya bir bit Çevir 1 yerine 0 veya 1 için 0 değerini değiştirmek için şeklindedir. **N** bir bitset bit tamsayı değerleri 0'dan tarafından dizine **N** -1, burada 0 dizinler ilk bit konumu ve **N** - 1 son bit konumu.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[bitset](#bitset)|Sınıfın bir nesnesi oluşturur `bitset\<N>` ve sıfır, belirtilen bir değer veya bir dizedeki karakter alınan değerleri BITS başlatır.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[ELEMENT_TYPE](#element_type)|Veri türü için eş anlamlı olan bir türü `bool` ve öğesi bit cinsinden başvurmak için kullanılan bir `bitset`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[tüm](#all)|Tüm bitleri bu testleri `bitset` tüm kümesine olup olmadıklarını belirlemek için `true`.|  
|[tüm](#any)|Üye işlevini dizisindeki tüm bit 1 olarak ayarlanmış olup olmadığını sınar.|  
|[sayısı](#count)|Üye işlevini bit ayarlayabilir bit sayısını döndürür.|  
|[ters çevirin](#flip)|Tüm bitleri değerini tersine çevirir bir `bitset` veya belirtilen bir konumdaki tek bir bit tersine çevirir.|  
|[yok](#none)|Yok biti 1 olarak ayarlarsanız, testleri bir `bitset` nesnesi.|  
|[Sıfırla](#reset)|Tüm bitleri sıfırlar bir `bitset` için 0 veya 0 belirtilen bir konuma bir bit hızında sıfırlar.|  
|[ayarlama](#set)|Tüm BITS ayarlar bir `bitset` 1 ya da bir bit konumunda bir belirtilen 1 ayarlar.|  
|[boyutu](#size)|Bit sayısını döndürür bir `bitset` nesnesi.|  
|[test etme](#test)|Testleri olup belirtilen bir konumda bit bir `bitset` 1 olarak ayarlayın.|  
|[to_string](#to_string)|Dönüştüren bir `bitset` nesnesinin bir dize gösterimi.|  
|[to_ullong](#to_ullong)|Bit değerlerin toplamını döndürür `bitset` olarak bir `unsigned long long`.|  
|[to_ulong](#to_ulong)|Dönüştüren bir `bitset` nesnesini `unsigned long` başlatmak için kullanılan içerdiği BITS dizisi oluşturmak `bitset`.|  
  
### <a name="member-classes"></a>Üye sınıfları  
  
|||  
|-|-|  
|[başvuru](#reference)|BITS bulunan başvurular sağlayan bir proxy sınıfı bir `bitset` erişmek ve tek tek bitleri için yardımcı sınıfı olarak işlemek için kullanılan `operator[]` sınıfının `bitset`.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator! =](#op_neq)|Bir hedef testleri `bitset` belirtilen eşitsizlik açısından `bitset`.|  
|[operator & =](#op_and_eq)|Bit kümeleri mantıksal ile Bitsel bir birleşimi gerçekleştirir `AND` işlemi.|  
|[işleç <<](#op_lshift)|Bitleri kaydırır bir `bitset` konumlar belirtilen sayıda sola ve yeni bir sonuç döndürür `bitset`.|  
|[işleç << =](#op_lshift_eq)|Bitleri kaydırır bir `bitset` konumlar belirtilen sayıda sola ve sonucu hedeflenen döndürür `bitset`.|  
|[operator ==](#op_eq_eq)|Bir hedef testleri `bitset` belirtilen eşitliği `bitset`.|  
|[İşleç >>](#op_rshift)|Bitleri kaydırır bir `bitset` konumlar belirtilen sayıda sağa ve yeni bir sonuç döndürür `bitset`.|  
|[İşleç >> =](#op_rshift_eq)|Bitleri kaydırır bir `bitset` konumlar belirtilen sayıda sağa ve sonucu hedeflenen döndürür `bitset`.|  
|[operator &#91; &#93;](#op_at)|Belirtilen bir konumda bir bit bir başvuru döndürür bir `bitset` varsa `bitset` değiştirilebilir; Aksi takdirde, bu konumda bit değerini döndürür.|  
|[operator ^ =](#op_xor_eq)|Bit kümeleri özel ile Bitsel bir birleşimi gerçekleştirir `OR` işlemi.|  
|[operator &#124; =](#op_or_eq')|Bit kümeleri dahil ile Bitsel bir birleşimi gerçekleştirir `OR` işlemi.|  
|[işleç ~](#op_dtor)|Bir hedef tüm bitleri tersine çevirir `bitset` ve sonucu döndürür.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<bitset >  
  
 **Namespace:** std  
  
##  <a name="all"></a>bitset::all  
 Tüm bitleri tüm ayarı true olup olmadığını belirlemek için bu bitset sınar.  
  
```  
bool all() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kümesindeki tüm BITS doğru olduğunda true döndürür. Döndürür **false** bir veya daha fazla BITS yanlışsa.  
  
##  <a name="any"></a>bitset::Any  
 Dizisindeki tüm bit 1 olarak ayarlanmış olup olmadığını sınar.  
  
```  
bool any() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** bitset herhangi bir bit 1'e; ayarlarsanız **false** tüm bitleri 0 ise.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_any.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   bitset<5> b1 ( 6 );  
   bool b, rb;  
  
   cout << "The original bitset b1( 6 ) is: ( "<< b1 << " )"  
        << endl;  
  
   b = b1.any ( );  
  
   if ( b )  
      cout << "At least one of the bits in bitset is set to 1."  
           << endl;  
   else  
      cout << "None of the bits in bitset are set to 1."  
           << endl;  
  
   bitset<5> rb1;  
   rb1 = b1.reset ( );  
  
   cout << "The reset bitset is: ( "<< b1 << " )"  
        << endl;  
  
   rb = rb1.any ( );  
  
   if ( rb )  
      cout << "At least one of the bits in the reset bitset "  
           << "are set to 1." << endl;  
   else  
      cout << "None of the bits in bitset b1 are set to 1."  
           << endl;  
}  
```  
  
```Output  
The original bitset b1( 6 ) is: ( 00110 )  
At least one of the bits in bitset is set to 1.  
The reset bitset is: ( 00000 )  
None of the bits in bitset b1 are set to 1.  
```  
  
##  <a name="bitset"></a>bitset::bitset  
 Sınıfın bir nesnesi oluşturur `bitset\<N>` ve sıfır veya belirtilen bir değer veya bir dizedeki karakter alınan değerleri BITS başlatır.  
  
```  
bitset();

bitset(
    unsigned long long val);

explicit bitset(
    const char* _CStr);

template <class CharType,   
    class Traits,   
    class Allocator>  
explicit bitset(
    const basic_string<CharType, Traits, Allocator>& str,  
    typename basic_string<CharType, Traits, Allocator>::size_type _Pos = 0);

template <class CharType,  
    class Traits,  
    class Allocator>  
explicit bitset(
    const basic_string<CharType, Traits, Allocator>& str,  
    typename basic_string<CharType, Traits, Allocator>::size_type _Pos,  
    typename basic_string<CharType, Traits, Allocator>::size_type count,  
    CharType _Zero = CharType ('0'),   
    CharType _One = CharType ('1'));
```  
  
### <a name="parameters"></a>Parametreler  
 `val`  
 İşaretsiz tamsayı olan temel iki gösterimi yapılandırılan bitset bitleri başlatmak için kullanılır.  
  
 `str`  
 Sıfırlar ve bitset bit değerlerini başlatmak için kullanılan olanları dizesi.  
  
 `_CStr`  
 C türü dizesi sıfırlar ve bitset bit değerlerini başlatmak için kullanılan olanlar.  
  
 `_Pos`  
 Dizedeki karakter soldan sağa sayım ve bitset ilk bit başlatmak için kullanılan sıfır ile başlayarak.  
  
 `count`  
 Bitset bitleri için başlangıç değerlerini sağlamak için kullanılan dizedeki karakter sayısı.  
  
 `_Zero`  
 Sıfır temsil etmek için kullanılan karakter. Varsayılan değer '0' dir.  
  
 `_One`  
 Bir tane temsil etmek için kullanılan karakter. Varsayılan değer '1' dir.  
  
### <a name="remarks"></a>Açıklamalar  
 Üç Oluşturucular, obects sınıfının oluşturmak için kullanılabilir `bitset\<N>`:  
  
-   İlk Oluşturucusu herhangi bir parametre kabul eder, sınıfın bir nesnesi oluşturur `bitset\<N>` ve sıfır tüm N BITS varsayılan bir değer ile başlatır.  
  
-   İkinci oluşturucu sınıfın bir nesnesi oluşturur `bitset\<N>` ve tek kullanarak BITS başlatır `unsigned long long` parametresi.  
  
-   Sınıfın bir nesnesi üçüncü Oluşturucusu oluşturur `bitset\<N>`, N başlatma BITS sıfırlar ve olanları c tarzı karakter dizesi içinde sağlanan karakter karşılık gelen değerleri. Dize bir dize türüne dönüştürmeyi olmadan Oluşturucusu arayın:`bitset<5> b5("01011");`  
  
 Sağlanan iki Oluşturucusu şablonları vardır:  
  
-   Sınıfın bir nesnesi ilk Oluşturucusu şablon oluşturur `bitset\<N>` ve sıfırlar ve olanları dizesinde karakter bitten başlatır. 0 veya 1 dışındaki tüm karakterler dizesinin yer alıyorsa, sınıfın bir nesnesi Oluşturucusu oluşturur [geçersiz bağımsız değişken](../standard-library/invalid-argument-class.md). Konumu belirtilmişse ( `_Pos`) Oluşturucusu sınıfın bir nesnesi oluşturur, dize uzunluğunu aştı olduğundan [out_of_range](../standard-library/out-of-range-class.md). Oluşturucu yalnızca bu BITS konumunda ayarlar *j* bitset kendisi de konumunda dizedeki karakter `_Pos + j` 1'dir. Varsayılan olarak, `_Pos` 0'dır.  
  
-   İkinci oluşturucu şablonu ilk benzer, ancak ek bir parametre içerir ( `count`) başlatmak için bit sayısını belirtmek için kullanılır. Ayrıca isteğe bağlı parametrelerden sahip `_Zero` ve `_One`, belirtmek ne de karakter `str` 0 olan bir bit ve 1 bit sırasıyla anlamına gelir yorumlanacağını.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_bitset.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   // Using the default constructor  
   using namespace std;  
   bitset<2> b0;  
   cout << "The set of bits in bitset<2> b0 is: ( "  
        << b0 << " )." << endl;  
  
   // Using the second member function  
   bitset<5> b1 ( 6 );  
   cout << "The set of bits in bitset<5> b1( 6 ) is: ( "  
        << b1 << " )." << endl;  
  
   // The template parameter N can be an expresssion  
   bitset< 2 * sizeof ( int ) > b2;  
   cout << "The set of bits in bitset<2 * sizeof ( int ) > b2 is: ( "  
        << b2 << " )." << endl;  
  
   // The base two representation will be truncated  
   // if its length exceeds the size of the bitset  
   bitset<3> b3 ( 6 );  
   cout << "The set of bits in bitset<3> b3( 6 ) is ( "  
        << b3 << " )." << endl;  
  
   // Using a c-style string to initialize the bitset  
    bitset<7> b3andahalf ( "1001001" );  
    cout << "The set of bits in bitset<7> b3andahalf ( \"1001001\" )"  
         << " is ( " << b3andahalf << " )." << endl;   
  
   // Using the fifth member function with the first parameter  
   string bitval4 ( "10011" );  
   bitset<5> b4 ( bitval4 );  
   cout << "The set of bits in bitset<5> b4( bitval4 ) is ( "  
        << b4 << " )." << endl;  
  
   // Only part of the string may be used for initialization  
  
   // Starting at position 3 for a length of 6 (100110)  
   string bitval5 ("11110011011");  
   bitset<6> b5 ( bitval5, 3, 6 );  
   cout << "The set of bits in bitset<11> b5( bitval, 3, 6 ) is ( "  
        << b5 << " )." << endl;  
  
   // The bits not initialized with part of the string  
   // will default to zero  
   bitset<11> b6 ( bitval5, 3, 5 );  
   cout << "The set of bits in bitset<11> b6( bitval5, 3, 5 ) is ( "  
        << b6 << " )." << endl;  
  
   // Starting at position 2 and continue to the end of the string  
   bitset<9> b7 ( bitval5, 2 );  
   cout << "The set of bits in bitset<9> b7( bitval, 2 ) is ( "  
        << b7 << " )." << endl;  
}  
```  
  
```Output  
The set of bits in bitset<2> b0 is: ( 00 ).  
The set of bits in bitset<5> b1( 6 ) is: ( 00110 ).  
The set of bits in bitset<2 * sizeof ( int ) > b2 is: ( 00000000 ).  
The set of bits in bitset<3> b3( 6 ) is ( 110 ).  
The set of bits in bitset<5> b4( bitval4 ) is ( 10011 ).  
The set of bits in bitset<11> b5( bitval, 3, 6 ) is ( 100110 ).  
The set of bits in bitset<11> b6( bitval5, 3, 5 ) is ( 00000010011 ).  
The set of bits in bitset<9> b7( bitval, 2 ) is ( 110011011 ).  
```  
  
##  <a name="count"></a>bitset::Count  
 Bit ayarlayabilir bit sayısını döndürür.  
  
```  
size_t count() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
Bit sayısını bit sırasını ayarlayın.  
  
### <a name="example"></a>Örnek  
  
Aşağıdaki örnek bitset::count üye fonksiyonu kullanımını göstermektedir.  
  
```cpp  
// bitset_count.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
    using namespace std;  
  
    bitset<5> b1(4);  
  
    cout << "The collection of bits in the original bitset is: ( "  
         << b1 << " )" << endl;  
  
    size_t i;  
    i = b1.count();  
    cout << "The number of bits in the bitset set to 1 is: "  
         << i << "." << endl;  
  
    bitset<5> fb1;  
    fb1 = b1.flip();  
  
    cout << "The collection of flipped bits in the modified bitset "  
         << "is: ( " << b1 << " )" << endl;  
  
    size_t ii;  
    ii = fb1.count();  
    cout << "The number of bits in the bitset set to 1 is: "  
         << ii << "." << endl;  
}  
```  
  
```Output  
The collection of bits in the original bitset is: ( 00100 )  
The number of bits in the bitset set to 1 is: 1.  
The collection of flipped bits in the modified bitset is: ( 11011 )  
The number of bits in the bitset set to 1 is: 4.  
```  
  
##  <a name="element_type"></a>bitset::ELEMENT_TYPE  
 Veri türü için eş anlamlı olan bir türü `bool` ve bir bitset öğesi bit başvurmak için kullanılabilir.  
  
```  
typedef bool element_type;  
```  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_elem_type.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   bitset<3> b1 ( 2 );  
   cout << "Original bitset b1(6) is: ( "<< b1 << " )"  
        << endl;  
  
   //Compare two ways to reference bits in a bitset  
   bool b;  
   bitset<5>::element_type e;  
  
   b = b1.test ( 2 );  
   if ( b )  
      cout << "The bit at position 2 of bitset b1"  
           << "has a value of 1." << endl;  
   else  
      cout << "The bit at position 2 of bitset b1"  
           << "has a value of 0." << endl;  
   b1[2] = 1;  
   cout << "Bitset b1 modified by b1[2] = 1 is: ( "<< b1 << " )"  
        << endl;  
  
   e = b1.test ( 2 );  
   if ( e )  
      cout << "The bit at position 2 of bitset b1"  
           << "has a value of 1." << endl;  
   else  
      cout << "The bit at position 2 of bitset b1"  
           << "has a value of 0." << endl;  
}  
```  
  
```Output  
Original bitset b1(6) is: ( 010 )  
The bit at position 2 of bitset b1has a value of 0.  
Bitset b1 modified by b1[2] = 1 is: ( 110 )  
The bit at position 2 of bitset b1has a value of 1.  
```  
  
##  <a name="flip"></a>bitset::Flip  
 Bir bitset tüm bitleri değerini tersine çevirir veya belirtilen bir konumdaki tek bir bit tersine çevirir.  
  
```  
bitset\<N>& flip();  
bitset\<N>& flip(size_t _Pos);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Pos`  
 Ters için değeri olan bit konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üye işlevini en iyi duruma çağrıldı değiştirilmiş bitset kopyası.  
  
### <a name="remarks"></a>Açıklamalar  
 İkinci üye işlevi oluşturur bir [out_of_range](../standard-library/out-of-range-class.md) parametre olarak belirtilen konumdaki boyuttan büyükse, özel durum *N* , **bitset\<**  *N*  **>**  , bit ters.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_flip.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   bitset<5> b1 ( 6 );  
  
   cout << "The collection of bits in the original bitset is: ( "  
        << b1 << " )" << endl;  
  
   bitset<5> fb1;  
   fb1 = b1.flip ( );  
  
   cout << "After flipping all the bits, the bitset becomes: ( "  
        << fb1 << " )" << endl;  
  
   bitset<5> f3b1;  
   f3b1 = b1.flip ( 3 );  
  
   cout << "After flipping the fourth bit, the bitset becomes: ( "  
        << f3b1 << " )" << endl << endl;  
  
   bitset<5> b2;  
   int i;  
   for ( i = 0 ; i <= 4 ; i++ )  
   {  
      b2.flip(i);  
      cout << b2 << "  The bit flipped is in position "  
           << i << ".\n";  
   }  
}  
```  
  
```Output  
The collection of bits in the original bitset is: ( 00110 )  
After flipping all the bits, the bitset becomes: ( 11001 )  
After flipping the fourth bit, the bitset becomes: ( 10001 )  
  
00001  The bit flipped is in position 0.  
00011  The bit flipped is in position 1.  
00111  The bit flipped is in position 2.  
01111  The bit flipped is in position 3.  
11111  The bit flipped is in position 4.  
```  
  
##  <a name="none"></a>bitset::none  
 Testleri yok biti 1 bitset nesnesi olarak ayarlayın.  
  
```  
bool none() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** bitset içinde yok biti 1 olarak; ayarlarsanız **false** en az bir bit 1 olarak ayarlarsanız.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_none.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   bitset<5> b1 ( 6 );  
   bool b, rb;  
  
   cout << "Original bitset b1(6) is: ( " << b1 << " )"  
        << endl;  
  
   b = b1.none ( );  
  
   if ( b )  
      cout << "None of the bits in bitset b1 are set to 1."  
           << endl;  
   else  
      cout << "At least one of the bits in bitset b1 is set to 1."  
           << endl;  
  
   bitset<5> rb1;  
   rb1 = b1.reset ( );  
   rb = rb1.none ( );  
   if ( rb )  
      cout << "None of the bits in bitset b1 are set to 1."  
           << endl;  
   else  
      cout << "At least one of the bits in bitset b1 is set to 1."  
           << endl;  
}  
```  
  
```Output  
Original bitset b1(6) is: ( 00110 )  
At least one of the bits in bitset b1 is set to 1.  
None of the bits in bitset b1 are set to 1.  
```  
  
##  <a name="op_neq"></a>bitset::operator! =  
 Belirtilen bitset ile eşitsizlik için bir hedef bitset sınar.  
  
```  
bool operator!=(const bitset\<N>& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Eşitsizlik hedef bitset karşılaştırılacak olan bitset.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** bit kümeleri farklıysa; **false** aynı olmaları durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 Bit kümeleri üye işleci işlevi tarafından eşitsizlik için sınanacak aynı boyutta olmalıdır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_op_NE.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   bitset<5> b1 ( 7 );  
   bitset<5> b2 ( 7 );  
   bitset<5> b3 ( 2 );  
   bitset<4> b4 ( 7 );  
  
   if ( b1 != b2 )  
      cout << "Bitset b1 is different from bitset b2." << endl;  
   else  
      cout << "Bitset b1 is the same as bitset b2." << endl;  
  
   if ( b1 != b3 )  
      cout << "Bitset b1 is different from bitset b3." << endl;  
   else  
      cout << "Bitset b1 is the same as bitset b3." << endl;  
  
   // This would cause an error because bitsets must have the  
   // same size to be tested  
   // if ( b1 != b4 )  
   //   cout << "Bitset b1 is different from bitset b4." << endl;  
   // else  
   //   cout << "Bitset b1 is the same as bitset b4." << endl;  
}  
```  
  
```Output  
Bitset b1 is the same as bitset b2.  
Bitset b1 is different from bitset b3.  
```  
  
##  <a name="op_and_eq"></a>bitset::operator&amp;=  
 Bit kümeleri mantıksal ile Bitsel bir birleşimi gerçekleştirir **ve** işlemi.  
  
```  
bitset\<N>& operator&=(const bitset\<N>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Bit düzeyinde ile hedef bitset birleştirilecek olan bitset.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit düzeyinde sonuçları değiştirilmiş hedef bitset **ve** parametre olarak belirtilen bitset işlemi.  
  
### <a name="remarks"></a>Açıklamalar  
 İki BITS birleştirilmiş tarafından **ve** işleci dönüş **true** her bit true; Aksi halde, kendi birleşimi döndürür **false**.  
  
 Bit kümeleri Bitsel birleştirilmesini aynı boyutta olmalıdır **ve** üye işleci işlevi tarafından işleci.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_op_bitwise.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   bitset<5> b1 ( 7 );  
   bitset<5> b2 ( 11 );  
   bitset<4> b3 ( 7 );  
  
   cout << "The target bitset b1 is:    ( "<< b1 << " )." << endl;  
   cout << "The parameter bitset b2 is: ( "<< b2 << " )." << endl;  
   cout << endl;  
  
   b1 &= b2;  
   cout << "After bitwise AND combination,\n"  
        << " the target bitset b1 becomes:   ( "<< b1 << " )."   
        << endl;  
  
   // Note that the parameter-specified bitset is unchanged  
   cout << "The parameter bitset b2 remains: ( "<< b2 << " )."   
        << endl;  
  
   // The following would cause an error because the bisets   
   // must be of the same size to be combined  
   // b1 &= b3;  
}  
```  
  
```Output  
The target bitset b1 is:    ( 00111 ).  
The parameter bitset b2 is: ( 01011 ).  
  
After bitwise AND combination,  
 the target bitset b1 becomes:   ( 00011 ).  
The parameter bitset b2 remains: ( 01011 ).  
```  

##  <a name="op_lshift"></a>bitset::operator\<\<    
  
Bir bitset bitleri konumlar belirtilen sayıda Sola kaydırır ve yeni bitset için sonuç döndürür.  
  
```  
bitset\<N> operator<<(size_t _Pos) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Pos`  
 Bitset bitleri gölgeye üzeresiniz sol konumlara sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 BITS ile değiştirilmiş bitset sola konumlar gereken sayıda kaydırılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci işlevinin döndürdüğü **bitset**(  **\*bu**) **<< pos, =** nerede [ <<= ](#op_lshift_eq) kaydırır bitset konumlar belirtilen sayıda sola bitleri ve hedeflenen bitset sonucu döndürür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_op_LS.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   bitset<5> b1 ( 7 );  
  
   cout << "The bitset b1 is: ( "<< b1 << " )." << endl;  
  
   bitset<5> b2;  
   b2 = b1 << 2;  
  
   cout << "After shifting the bits 2 positions to the left,\n"  
        << " the bitset b2 is: ( "<< b2 << " )."  
        << endl;  
  
   bitset<5> b3 = b2 >> 1;  
  
   cout << "After shifting the bits 1 position to the right,\n"  
        << " the bitset b3 is: ( " << b3 << " )."  
        << endl;  
}  
```  
  
##  <a name="op_lshift_eq"></a>bitset::operator&lt;&lt;=  
 Bir bitset bitleri konumlar belirtilen sayıda Sola kaydırır ve hedeflenen bitset sonucunu döndürür.  
  
```  
bitset\<N>& operator<<=(size_t _Pos);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Pos`  
 Bitset bitleri gölgeye üzeresiniz konum sola sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 BITS kaldırılmış şekilde değiştirilebilir hedeflenen bitset sola konumlar gereken sayıda gölgeye.  
  
### <a name="remarks"></a>Açıklamalar  
 Konumda kaydırmak için herhangi bir öğe zaten varsa, işlev değeri için bit 0 temizler.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_op_LSE.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   bitset<5> b1 ( 7 );  
   cout << "The target bitset b1 is: ( "<< b1 << " )." << endl;  
   b1 <<= 2;  
   cout << "After shifting the bits 2 positions to the left,\n"  
        << " the target bitset b1 becomes: ( "<< b1 << " )."   
        << endl;  
}  
```  
  
```Output  
The target bitset b1 is: ( 00111 ).  
After shifting the bits 2 positions to the left,  
 the target bitset b1 becomes: ( 11100 ).  
```  
  
##  <a name="op_eq_eq"></a>bitset::operator ==  
 Belirtilen bitset sahip bir hedef bitset eşitlik için test eder.  
  
```  
bool operator==(const bitset\<N>& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Hedef bitset eşitlik için karşılaştırılması gereken olduğu bitset.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** bit kümeleri; aynıysa **false** farklı ise.  
  
### <a name="remarks"></a>Açıklamalar  
 Bit kümeleri üye işleci işlevi tarafından eşitlik için test edilmesi için aynı boyutta olmalıdır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_op_EQ.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   bitset<5> b1 ( 7 );  
   bitset<5> b2 ( 7 );  
   bitset<5> b3 ( 2 );  
   bitset<4> b4 ( 7 );  
  
   if ( b1 == b2 )  
      cout << "Bitset b1 is the same as bitset b2." << endl;  
   else  
      cout << "Bitset b1 is different from bitset b2." << endl;  
  
   if ( b1 == b3 )  
      cout << "Bitset b1 is the same as bitset b3." << endl;  
   else  
      cout << "Bitset b1 is different from bitset b3." << endl;  
  
   // This would cause an error because bitsets must have the   
   // same size to be tested  
   // if ( b1 == b4 )  
   //   cout << "Bitset b1 is the same as bitset b4." << endl;  
   // else  
   //   cout << "Bitset b1 is different from bitset b4." << endl;  
}  
```  
  
```Output  
Bitset b1 is the same as bitset b2.  
Bitset b1 is different from bitset b3.  
```  
  
##  <a name="op_rshift"></a>bitset::operator&gt;&gt;  
 Bir bitset bitleri konumlar belirtilen sayıda sağa kaydırır ve yeni bitset için sonuç döndürür.  
  
```  
bitset\<N> operator>>(size_t _Pos) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Pos`  
 Bitset bitleri gölgeye üzeresiniz konum sağa sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 BITS olduğu yere bir yeni bitset sağa gölgeye hedeflenen bitset göreli konum gerekli sayısı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_op_RS.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   bitset<5> b1 ( 7 );  
   cout << "The bitset b1 is: ( "<< b1 << " )." << endl;  
  
   bitset<5> b2;  
   b2 = b1 << 2;  
  
   cout << "After shifting the bits 2 positions to the left,\n"  
        << " the bitset b2 is: ( "<< b2 << " )."  
        << endl;  
   bitset<5> b3 = b2 >> 1;  
  
   cout << "After shifting the bits 1 position to the right,\n"  
        << " the bitset b3 is: ( " << b3 << " )."  
        << endl;  
}  
```  
  
```Output  
The bitset b1 is: ( 00111 ).  
After shifting the bits 2 positions to the left,  
 the bitset b2 is: ( 11100 ).  
After shifting the bits 1 position to the right,  
 the bitset b3 is: ( 01110 ).  
```  
  
##  <a name="op_rshift_eq"></a>bitset::operator&gt;&gt;=  
 Bir bitset bitleri konumlar belirtilen sayıda sağa kaydırır ve hedeflenen bitset sonucunu döndürür.  
  
```  
bitset\<N>& operator>>=(size_t _Pos);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Pos`  
 Bitset bitleri gölgeye üzeresiniz konum sağa sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 BITS kaldırılmış şekilde değiştirilebilir hedeflenen bitset sağa konumlar gereken sayıda gölgeye.  
  
### <a name="remarks"></a>Açıklamalar  
 Konumda kaydırmak için herhangi bir öğe zaten varsa, işlev değeri için bit 0 temizler.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_op_RSE.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   bitset<5> b1 ( 28 );  
   cout << "The target bitset b1 is: ( "<< b1 << " )." << endl;  
  
   b1 >>= 2;  
   cout << "After shifting the bits 2 positions to the right,\n"  
        << " the target bitset b1 becomes: ( "<< b1 << " )."   
        << endl;  
}  
```  
  
```Output  
The target bitset b1 is: ( 11100 ).  
After shifting the bits 2 positions to the right,  
 the target bitset b1 becomes: ( 00111 ).  
```  
  
##  <a name="op_at"></a>bitset::operator]  
 Bitset değiştirilebilir ise biraz bir bitset belirtilen konumda bir başvuru döndürür; Aksi takdirde, bu konumda bit değerini döndürür.  
  
```  
bool operator[](size_t _Pos) const;
reference operator[](size_t _Pos);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Pos`  
 Bitset içinde bit bulma konumu.  
  
### <a name="remarks"></a>Açıklamalar  
Tanımladığınızda [ \_YİNELEYİCİ\_hata ayıklama\_düzeyi](../standard-library/iterator-debug-level.md) bitset sınırları dışındaki bir öğe erişmeye 1 veya 2'de, yapı olarak, bir çalışma zamanı hatası, yürütülebilir dosya ortaya çıkar. Daha fazla bilgiler için bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_op_REF.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   bool b;  
   bitset<5> b1 ( 6 );  
   cout << "The initialized bitset<5> b1( 2 ) is: ( "<< b1 << " )."  
        << endl;  
  
   int i;  
   for ( i = 0 ; i <= 4 ; i++ )  
   {  
      b = b1[ i ];  
      cout << "  The bit in position "  
           << i << " is " << b << ".\n";  
   }  
}  
```  
  
##  <a name="op_xor_eq"></a>bitset::operator ^ =  
 Bit kümeleri özel ile Bitsel bir birleşimi gerçekleştirir `OR` işlemi.  
  
```  
bitset\<N>& operator^=(const bitset\<N>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Bit düzeyinde ile hedef bitset birleştirilecek olan bitset.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit düzeyinde özel sonuçları değiştirilmiş hedef bitset `OR` parametre olarak belirtilen bitset işlemi.  
  
### <a name="remarks"></a>Açıklamalar  
 İki BITS birleştirilmiş tarafından özel **veya** işleci dönüş **true** en az bir varsa, ancak ikisini, bit **true**; Aksi halde, kendi birleşimi döndürür**yanlış**.  
  
 Bit kümeleri ile özel Bitsel birleştirilecek aynı boyutta olmalıdır `OR` üye işleci işlevi tarafından işleci.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_op_bitwiseOR.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   bitset<5> b1 ( 7 );  
   bitset<5> b2 ( 11 );  
   bitset<4> b3 ( 7 );  
  
   cout << "The target bitset b1 is:    ( "<< b1 << " )." << endl;  
   cout << "The parameter bitset b2 is: ( "<< b2 << " )." << endl;  
   cout << endl;  
  
   b1 ^= b2;  
   cout << "After bitwise exclusive OR combination,\n"  
        << " the target bitset b1 becomes:   ( "<< b1 << " )."   
        << endl;  
  
   // Note that the parameter-specified bitset in unchanged  
   cout << "The parameter bitset b2 remains: ( "<< b2 << " )."   
        << endl;  
  
   // The following would cause an error because the bisets   
   // must be of the same size to be combined  
   // b1 |= b3;  
}  
```  
  
```Output  
The target bitset b1 is:    ( 00111 ).  
The parameter bitset b2 is: ( 01011 ).  
  
After bitwise exclusive OR combination,  
 the target bitset b1 becomes:   ( 01100 ).  
The parameter bitset b2 remains: ( 01011 ).  
```  
  
##  <a name="op_or_eq"></a>bitset::operator &#124; =  
 Bit kümeleri dahil ile Bitsel bir birleşimi gerçekleştirir `OR` işlemi.  
  
```  
bitset\<N>& operator|=(const bitset\<N>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Bit düzeyinde ile hedef bitset birleştirilecek olan bitset.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit düzeyinde sonuçları değiştirilmiş hedef bitset dahil `OR` parametre olarak belirtilen bitset işlemi.  
  
### <a name="remarks"></a>Açıklamalar  
 İki BITS birleştirilmiş dahil tarafından `OR` işleci dönüş **true** BITS en az biri olduğunda **true**; bitlerin her ikisi de varsa **yanlış**, kendi birleşimini döndürür **false**.  
  
 Bit kümeleri bit düzeyinde kapsayıcı ile birleştirilecek aynı boyutta olmalıdır `OR` üye işleci işlevi tarafından işleci.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_op_BIO.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   bitset<5> b1 ( 7 );  
   bitset<5> b2 ( 11 );  
   bitset<4> b3 ( 7 );  
  
   cout << "The target bitset b1 is:    ( "<< b1 << " )." << endl;  
   cout << "The parameter bitset b2 is: ( "<< b2 << " )." << endl;  
   cout << endl;  
  
   b1 |= b2;  
   cout << "After bitwise inclusive OR combination,\n"  
        << " the target bitset b1 becomes:   ( "<< b1 << " )."   
        << endl;  
  
   // Note that the parameter-specified bitset in unchanged  
   cout << "The parameter bitset b2 remains: ( "<< b2 << " )."   
        << endl;  
  
   // The following would cause an error because the bisets   
   // must be of the same size to be combined  
   // b1 |= b3;  
}  
```  
  
```Output  
The target bitset b1 is:    ( 00111 ).  
The parameter bitset b2 is: ( 01011 ).  
  
After bitwise inclusive OR combination,  
 the target bitset b1 becomes:   ( 01111 ).  
The parameter bitset b2 remains: ( 01011 ).  
```  
  
##  <a name="op_dtor"></a>bitset::operator ~  
 Hedef bitset tüm bitleri tersine çevirir ve sonucu döndürür.  
  
```  
bitset\<N> operator~() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bitset göre hedeflenen bitset tersine, BITS ile.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_op_invert.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <bitset>  
  
int main( )  
{  
   using namespace std;  
  
   bitset<5> b1 ( 7 );  
   bitset<5> b2;  
   b2 = ~b1;  
  
   cout << "Bitset b1 is: ( "<< b1 << " )." << endl;  
   cout << "Bitset b2 = ~b1 is: ( "<< b2 << " )." << endl;  
  
   // These bits could also be flipped using the flip member function  
   bitset<5> b3;  
   b3 = b1.flip( );  
   cout << "Bitset b3 = b1.flip( ) is: ( "<< b2 << " )." << endl;  
}  
```  
  
```Output  
Bitset b1 is: ( 00111 ).  
Bitset b2 = ~b1 is: ( 11000 ).  
Bitset b3 = b1.flip( ) is: ( 11000 ).  
```  
  
##  <a name="reference"></a>bitset::Reference  
 BITS erişmek ve tek tek bitleri için yardımcı sınıfı olarak işlemek için kullanılan bir bitset bulunan başvurular sağlayan bir proxy sınıfı `operator[]` sınıfı bitset biri.  
  
```  
class reference {  
   friend class bitset\<N>;  
public: 
   reference& operator=(bool val);
   reference& operator=(const reference& _Bitref);
   bool operator~() const;
   operator bool() const;
   reference& flip();
};  
```    
  
### <a name="parameters"></a>Parametreler  
 `val`  
 Nesne türü değeri `bool` biraz bir bitset atanacak.  
  
 `_Bitref`  
 Bir başvuru formun *x [i]* konumunda bit *ı* bitset içinde *x*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bitset sınıfı referansın beşinci üye işlevleri ve birinci, ikinci bağımsız değişkeni konumunu tarafından belirtilen bit başvuru ve **true** veya **false**değiştirilmiş bit değerini yansıtmak için bitset sınıfı başvuru üçüncü ve dördüncü üye işlevleri için.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınıf `reference` yalnızca bitset yönelik bir yardımcı sınıfını bulunan `operator[]`. Üye sınıfı bir bitset içinde tek bir bit erişmek için bir nesne açıklar. Let *b* türünde bir nesne olması `bool`, *x* ve *y* türündeki nesneler **bitset\<***N*  **>** , ve *ı* ve *j* böyle bir nesnenin içinde geçerli konumlar. Gösterimi *x [i]* konumunda bit başvuran *ı* bitset içinde *x*. Sınıf üyesi işlevleri `reference` sağlar, sırasıyla aşağıdaki işlemleri:  
  
|Çalışma|Tanım|  
|---------------|----------------|  
|*x*[*ı*] = *b*|Depoları `bool` değeri *b* bit konumunda *ı* bitset içinde *x*.|  
|*x*[*ı*] = *y*[*j*]|Bit değerini depolar *y*[ *j*] bit konumunda *ı* bitset içinde *x*.|  
|*b* = ~ *x*[*ı*]|Bit çevrilen değerini depolar *x*[ *ı*] içinde `bool` *b*.|  
|*b* = *x*[*ı*]|Bit değerini depolar *x*[ *ı*] içinde `bool` *b*.|  
|*x*[*ı*]. `flip`( )|Bit çevrilen değerini depolar *x*[ *ı*] bit konumunda geri *ı* içinde *x*.|  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_reference.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   bitset<5> b1 ( 2 );  
   bitset<5> b2 ( 6 );  
   cout << "The initialized bitset<5> b1( 2 ) is: ( "<< b1 << " )."  
        << endl;  
   cout << "The initialized bitset<5> b2( 6 ) is: ( "<< b2 << " )."  
        << endl;  
  
   // Example of x [i] = b storing bool b at bit position i  
   // in bitset x  
   b1[ 0 ] = true;  
   cout << "The bitset<5> b1 with the bit at position 0 set to 1"  
        << " is: ( "<< b1 << " )" << endl;  
  
   // Example of x [i] = y [j] storing the bool value of the  
   // bit at position j in bitset y at bit position i in bitset x  
   b2 [4] = b1 [0];      // b1 [0] = true  
   cout << "The bitset<5> b2 with the bit at position 4 set to the "  
        << "value\n of the bit at position 0 of the bit in "  
        << "bitset<5> b1 is: ( "<<  b2  << " )" << endl;  
  
   // Example of b = ~x [i] flipping the value of the bit at  
   // position i of bitset x and storing the value in an   
   // object b of type bool  
   bool b = ~b2 [4];      // b2 [4] = false  
   if ( b )  
      cout << "The value of the object b = ~b2 [4] "  
           << "of type bool is true." << endl;  
   else  
      cout << "The value of the object b = ~b2 [4] "  
           << "of type bool is false." << endl;  
  
   // Example of b = x [i] storing the value of the bit at  
   // position i of bitset x in the object b of type bool  
   b = b2 [4];  
   if ( b )  
      cout << "The value of the object b = b2 [4] "  
           << "of type bool is true." << endl;  
   else  
      cout << "The value of the object b = b2 [4] "  
           << "of type bool is false." << endl;  
  
   // Example of x [i] . flip ( ) toggling the value of the bit at  
   // position i of bitset x  
   cout << "Before flipping the value of the bit at position 4 in "  
        << "bitset b2,\n it is ( "<<  b2  << " )." << endl;  
   b2 [4].flip( );  
   cout << "After flipping the value of the bit at position 4 in "  
        << "bitset b2,\n it becomes ( "<<  b2  << " )." << endl;  
   bool c;  
   c = b2 [4].flip( );  
   cout << "After a second flip, the value of the position 4"  
        << " bit in b2 is now: " << c << ".";  
}  
```  
  
```Output  
The initialized bitset<5> b1( 2 ) is: ( 00010 ).  
The initialized bitset<5> b2( 6 ) is: ( 00110 ).  
The bitset<5> b1 with the bit at position 0 set to 1 is: ( 00011 )  
The bitset<5> b2 with the bit at position 4 set to the value  
 of the bit at position 0 of the bit in bitset<5> b1 is: ( 10110 )  
The value of the object b = ~b2 [4] of type bool is false.  
The value of the object b = b2 [4] of type bool is true.  
Before flipping the value of the bit at position 4 in bitset b2,  
 it is ( 10110 ).  
After flipping the value of the bit at position 4 in bitset b2,  
 it becomes ( 00110 ).  
After a second flip, the value of the position 4 bit in b2 is now: 1.  
```  
  
##  <a name="reset"></a>bitset::reset  
 Bir bitset tüm bitleri 0 olarak sıfırlar veya 0 belirtilen konumda bir bit sıfırlar.  
  
```  
bitset\<N>& reset();  
bitset\<N>& reset(size_t _Pos);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Pos`  
 Konumu bit bitset 0 değerine sıfırlanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üye işlevini en iyi duruma çağrıldı bitset kopyası.  
  
### <a name="remarks"></a>Açıklamalar  
 İkinci üye işlevi oluşturur bir [out_of_range](../standard-library/out-of-range-class.md) belirtilen konumdaki bitset boyuttan büyükse, özel durum.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_reset.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   bitset<5> b1 ( 13 );  
   cout << "The set of bits in bitset<5> b1(13) is: ( "<< b1 << " )"  
        << endl;  
  
   bitset<5> b1r3;  
   b1r3 = b1.reset( 2 );  
   cout << "The collecion of bits obtained from resetting the\n"  
        << " third bit of bitset b1 is: ( "<< b1r3 << " )"   
        << endl;  
  
   bitset<5> b1r;  
   b1r = b1.reset( );  
   cout << "The collecion of bits obtained from resetting all\n"  
        << " the elements of the bitset b1 is: ( "<< b1r << " )"  
        << endl;  
}  
```  
  
```Output  
The set of bits in bitset<5> b1(13) is: ( 01101 )  
The collecion of bits obtained from resetting the  
 third bit of bitset b1 is: ( 01001 )  
The collecion of bits obtained from resetting all  
 the elements of the bitset b1 is: ( 00000 )  
```  
  
##  <a name="set"></a>bitset::set  
 Tüm BITS bitset 1 veya kümeleri için biraz 1 belirtilen konumda ayarlar.  
  
```   
bitset\<N>& set();

bitset\<N>& set(
    size_t _Pos,   
    bool val = true);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Pos`  
 Bitset ayarlamak için bit konumda bir değer atanmış.  
  
 `val`  
 Belirtilen konumdaki bit atanacak değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üye işlevini en iyi duruma çağrıldı bitset kopyası.  
  
### <a name="remarks"></a>Açıklamalar  
 İkinci üye işlevi oluşturur bir [out_of_range](../standard-library/out-of-range-class.md) belirtilen konumdaki bitset boyuttan büyükse, özel durum.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_set.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   bitset<5> b1 ( 6 );  
   cout << "The set of bits in bitset<5> b1(6) is: ( "<< b1 << " )"  
        << endl;  
  
   bitset<5> b1s0;  
   b1s0 = b1.set( 0 );  
   cout << "The collecion of bits obtained from setting the\n"  
        << " zeroth bit of bitset b1 is: ( "<< b1s0 << " )"   
        << endl;  
  
   bitset<5> bs1;  
   bs1 = b1.set( );  
   cout << "The collecion of bits obtained from setting all the\n"  
        << " elements of the bitset b1 is: ( "<< bs1 << " )"  
        << endl;  
}  
```  
  
```Output  
The set of bits in bitset<5> b1(6) is: ( 00110 )  
The collecion of bits obtained from setting the  
 zeroth bit of bitset b1 is: ( 00111 )  
The collecion of bits obtained from setting all the  
 elements of the bitset b1 is: ( 11111 )  
```  
  
##  <a name="size"></a>bitset::size  
 Bitset nesnesinde bit sayısını döndürür.  
  
```  
size_t size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 BITS, sayısı *N*, bir bitset içinde\<N >.  
  
### <a name="example"></a>Örnek  
  Aşağıdaki örnek bitset::size üye fonksiyonu kullanımını göstermektedir.  
  
```cpp  
// bitset_size.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    bitset<5> b1(6);  
    size_t i;  
  
    cout << "The set of bits in bitset<5> b1( 6 ) is: ( "<< b1 << " )"  
         << endl;  
  
    i = b1.size();  
  
    cout << "The number of bits in bitset b1 is: " << i << "."  
         << endl;  
}  
```  
  
```Output  
The set of bits in bitset<5> b1( 6 ) is: ( 00110 )  
The number of bits in bitset b1 is: 5.  
```  
  
##  <a name="test"></a>bitset::test  
 Belirtilen konumda bir bitset biti 1 olarak ayarlanmış olup olmadığını sınar.  
  
```  
bool test(size_t _Pos) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Pos`  
 Değeri için sınanacak bitset bit konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** bağımsız değişkeni konumu tarafından belirtilen bit 1'e; ayarlanmışsa, aksi takdirde, **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini oluşturur bir [out_of_range](../standard-library/out-of-range-class.md)

