---
title: bitset Sınıfı
ms.date: 03/27/2019
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
ms.openlocfilehash: f580e56efe1db42e464deedfa66da861ff897bcb
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/17/2019
ms.locfileid: "58566123"
---
# <a name="bitset-class"></a>bitset Sınıfı

Bit bayrakları için bir dizi öğeleri veya koşulları tutma kısa bir yol sağlayan bir sabit sayının oluşan bir dizi depolar nesnesi türünü açıklar. Bitset sınıfı BITS koleksiyonunu içeren ve sabit zamanlı her bit erişmeyi türü bitset nesnelerin işlemleri destekler.

## <a name="syntax"></a>Sözdizimi

```cpp
template <size_t N>
class bitset
```

### <a name="parameters"></a>Parametreler

*N*<br/>
Bitset nesnesindeki sıfır olmayan bir tamsayı türü ile bit sayısını belirtir. `size_t` , gerekir bilinir derleme zamanında.

## <a name="remarks"></a>Açıklamalar

Benzer aksine [vektör\<bool > sınıfı](../standard-library/vector-bool-class.md), bitset sınıfı yineleyiciler yok ve C++ Standart Kitaplığı kapsayıcı değil. Ayrıca öğesinden farklı\<bool > durdurulmasını ve şablon parametresi tarafından belirtilen boyut uygun olarak derleme zamanında sabit bazı belirli boyut tarafından *N* olduğunda **bitset\<N\>**  bildirilir.

Bir bit değeri 1 ise ayarlayın ve değeri 0'dır sıfırlayabilirsiniz. Veya biraz ters çevir 0, 1 veya 0-1 değerini değiştirmeniz önerilir. *N* bir bitset bit tamsayı değerleri 0'dan tarafından dizini oluşturulmuş *N* -1, burada ilk bit konumu 0 dizinler ve *N* - 1 son bit konumu.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[bitset](#bitset)|Sınıfın bir nesnesi oluşturur `bitset\<N>` ve bitler sıfır, belirtilen bir değer veya bir dizedeki karakter alınan değerleri başlatır.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[element_type](#element_type)|Veri türü için bir eşanlamlı bir türe **bool** ve öğe bit başvurmak için kullanılan bir `bitset`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Tüm](#all)|Tüm bitleri bu testleri `bitset` tüm ayarlanmış olup olmadığını belirlemek için **true**.|
|[Tüm](#any)|Üye işlevi, dizideki herhangi bir bit 1 olarak ayarlanmış olup olmadığını sınar.|
|[Sayısı](#count)|Üye işlevi bit sırayı ayarlamak bit sayısını döndürür.|
|[Çevir](#flip)|Değeri içindeki tüm bitleri tersine çevirir bir `bitset` veya tek bir bit belirtilen konumda tersine çevirir.|
|[Yok](#none)|Yok biti 1 olarak ayarlarsanız, testleri bir `bitset` nesne.|
|[Sıfırlama](#reset)|İçindeki tüm bitleri sıfırlar bir `bitset` 0 veya 0 belirtilen konumda bir bit sıfırlar.|
|[set](#set)|Tüm bitleri ayarlar bir `bitset` 1 veya 1 için'belirtilen konumda bir bit ayarlar.|
|[Boyutu](#size)|Bit sayısı döndürür bir `bitset` nesne.|
|[Test](#test)|Testleri olmadığını bit içinde belirtilen konumda bir `bitset` 1 olarak ayarlayın.|
|[to_string](#to_string)|Dönüştürür bir `bitset` nesnenin dize gösterimi.|
|[to_ullong](#to_ullong)|Bit değerlerin toplamını döndürür `bitset` olarak bir **işaretsiz long long**.|
|[to_ulong](#to_ulong)|Dönüştürür bir `bitset` nesnesini **işaretsiz uzun** dizisi başlatmak için kullanılan içerdiği bit oluşturmak `bitset`.|

### <a name="member-classes"></a>Üye sınıfları

|Üye sınıfı|Açıklama|
|-|-|
|[Başvuru](#reference)|Başvuruların bitlere atanmasına bulunan sağlayan bir ara sunucu sınıfı bir `bitset` erişmek ve tek tek bitleri için yardımcı sınıfı olarak işlemek için kullanılan `operator[]` sınıfın `bitset`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](#op_neq)|Bir hedef test `bitset` belirtilen eşitsizliği `bitset`.|
|[işleç & =](#op_and_eq)|Mantıksal ile bitsets Bitsel bir birleşimi gerçekleştirir `AND` işlemi.|
|[işleç <<](#op_lshift)|BITS kaydırır bir `bitset` sola belirli sayıdaki uzaklığına ve sonuç yeni bir döndürür `bitset`.|
|[işleç << =](#op_lshift_eq)|BITS kaydırır bir `bitset` sola belirli sayıdaki uzaklığına ve sonucu hedeflenen döndürür `bitset`.|
|[operator==](#op_eq_eq)|Bir hedef test `bitset` belirtilen eşitliği `bitset`.|
|[İşleç >>](#op_rshift)|BITS kaydırır bir `bitset` sağındaki belirli sayıdaki uzaklığına ve sonuç yeni bir döndürür `bitset`.|
|[İşleç >> =](#op_rshift_eq)|BITS kaydırır bir `bitset` sağındaki belirli sayıdaki uzaklığına ve sonucu hedeflenen döndürür `bitset`.|
|[işleci&#91;&#93;](#op_at)|Bir bit içinde belirtilen konumda bir başvuru döndürür bir `bitset` varsa `bitset` değiştirilebilir; Aksi takdirde, bu konumda bit değerini döndürür.|
|[operator^=](#op_xor_eq)|Özel ile bitsets Bitsel bir birleşimi gerçekleştirir `OR` işlemi.|
|[İşleç&#124;=](#op_or_eq)|Kapsamlı ile bitsets Bitsel bir birleşimi gerçekleştirir `OR` işlemi.|
|[işleç ~](#op_not)|Bir hedef içindeki tüm bitleri tersine çevirir `bitset` ve sonucu döndürür.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bitset >

**Namespace:** std

## <a name="all"></a>  bitset::all

Bunların hepsi true olup olmadığını belirlemek için bu bitset içindeki tüm bitleri sınar.

```cpp
bool all() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu küme içindeki tüm bitleri doğru olduğunda true döndürür. Döndürür **false** bir veya daha fazla BITS false ise.

## <a name="any"></a>  bitset::Any

Dizideki herhangi bir bit 1 olarak ayarlanmış olup olmadığını sınar.

```cpp
bool any() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** bitset herhangi bir bit; 1 olarak ayarlanmışsa **false** tüm bitleri 0 ise.

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

## <a name="bitset"></a>  bitset::bitset

Sınıfın bir nesnesi oluşturur `bitset\<N>` ve bitler sıfır ya da belirtilen bir değer veya bir dizedeki karakter alınan değerleri başlatır.

```cpp
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

*VAL*<br/>
İki temel temsili yapılandırılmakta bitset bitler başlatmak için kullanılan işaretsiz tamsayı.

*str*<br/>
Sıfır ve bitset bit değerleri başlatmak için kullanılan değerler dizisi.

*_CStr*<br/>
Sıfır ve vm'lere bitset bit değerleri başlatmak için kullanılan bir C tarzı dizesi.

*_Pos*<br/>
Soldan sağa sayım ve bitset'in ilk bit başlatmak için kullanılan sıfır ile başlayarak dizedeki karakter konumu.

*Sayısı*<br/>
Bitset bitler için başlangıç değerlerini sağlamak için kullanılan dize karakter sayısı.

*_Zero*<br/>
Sıfır temsil etmek için kullanılan karakter. '0' varsayılandır.

*_Bir*<br/>
Bir tane temsil etmek için kullanılan karakter. '1' varsayılandır.

### <a name="remarks"></a>Açıklamalar

Üç oluşturucular obects sınıfı oluşturmak için kullanılabilir `bitset\<N>`:

- İlk Oluşturucu, parametre kabul eder, sınıfın bir nesnesi oluşturur `bitset\<N>` ve sıfır tüm N BITS varsayılan bir değere başlatır.

- İkinci Oluşturucu, sınıfın bir nesnesi oluşturur `bitset\<N>` ve tek kullanarak BITS başlatır **işaretsiz long long** parametresi.

- Üçüncü Oluşturucu, sınıfın bir nesnesi oluşturur `bitset\<N>`, N başlatma bitler sıfır ve vm'lere c stili karakter dizesi içinde sağlanan karakterlere karşılık gelen değerlere. Oluşturucu, dizenin bir dize türüne atmadan çağırın: `bitset<5> b5("01011");`

Sağlanan iki Oluşturucu şablonlar vardır:

- İlk Oluşturucu şablon sınıfın bir nesnesi oluşturur `bitset\<N>` ve sağlanan sıfırlar ve vm'lere bir dizede karakter bitten başlatır. Herhangi bir karakter dizesinin dışında 0 veya 1 ise oluşturucunun sınıfın bir nesnesi oluşturması [geçersiz bağımsız değişken](../standard-library/invalid-argument-class.md). Belirtilen konum (*_Pos*) Oluşturucu sınıfın bir nesnesi oluşturur. ardından dizenin uzunluğu dışında olan [out_of_range](../standard-library/out-of-range-class.md). Oluşturucu yalnızca bu BITS konumuna ayarlar. *j* bitset kendisi içinde konumunda dizedeki karakter `_Pos + j` 1'dir. Varsayılan olarak, *_Pos* 0'dır.

- İkinci oluşturucu şablon ilkine benzer, ancak ek bir parametre içerir (*sayısı*) başlatmak için bit sayısını belirtmek için kullanılır. Ayrıca iki isteğe bağlı parametreye sahiptir *_Zero* ve *_Bir*, ne de karakter göstermek *str* sırasıyla auto'yu 0 olan bir bit ve bir 1 bit yorumlanacağını.

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

## <a name="count"></a>  bitset::Count

Bit sırayı ayarlamak bit sayısını döndürür.

```cpp
size_t count() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit bit sırasını ayarlayın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bitset::count üye işlevinin kullanımını gösterir.

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

## <a name="element_type"></a>  bitset::element_type

Veri türü için bir eşanlamlı bir türe **bool** ve bir bitset öğesi BITS başvurmak için kullanılabilir.

```cpp
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

## <a name="flip"></a>  bitset::Flip

Değeri bir bitset içindeki tüm bitleri tersine çevirir veya tek bir bit belirtilen konumda tersine çevirir.

```cpp
bitset\<N>& flip();
bitset\<N>& flip(size_t _Pos);
```

### <a name="parameters"></a>Parametreler

*_Pos*<br/>
Ters için değeri olan bit konumu.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi en iyi duruma çağrıldı değiştirilmiş bitset bir kopyası.

### <a name="remarks"></a>Açıklamalar

İkinci üye işlevi oluşturur bir [out_of_range](../standard-library/out-of-range-class.md) parametre olarak belirtilen konumu boyutundan büyükse, özel durum *N* , **bitset\<**  *N* **>** biti ters.

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

## <a name="none"></a>  bitset::none

Bitset nesnesindeki 1 yok biti ayarlanmışsa sınar.

```cpp
bool none() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** bitset içinde yok biti 1 olarak; ayarlarsanız **false** en az bir biti 1 olarak ayarlarsanız.

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

## <a name="op_neq"></a>  bitset::operator! =

Belirtilen bitset ile bir hedef bitset eşitsizlik için test eder.

```cpp
bool operator!=(const bitset\<N>& right) const;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Eşitsizlik için hedef bitset karşılaştırılacak olan bitset.

### <a name="return-value"></a>Dönüş Değeri

**doğru** bitsets farklıysa; **false** aynı olmaları durumunda.

### <a name="remarks"></a>Açıklamalar

Bitsets üye işleci işlevi tarafından eşitsizlik için test edilecek aynı boyutta olması gerekir.

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

## <a name="op_and_eq"></a>  bitset::operator&amp;=

Mantıksal ile bitsets Bitsel bir birleşimi gerçekleştirir `AND` işlemi.

```cpp
bitset\<N>& operator&=(const bitset\<N>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bit düzeyinde hedef bitset ile birleştirilecek olan bitset.

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde sonuçları değiştirilmiş hedef bitset `AND` parametre olarak belirtilen bitset işlemi.

### <a name="remarks"></a>Açıklamalar

İki bit birleştirilmiş tarafından `AND` işleci dönüş **true** her bit true; Aksi takdirde, bunların bir bileşimini döndürür **false**.

Bitsets Bitsel birleştirilmesini aynı boyutta olmalıdır `AND` üye işleci işlevi tarafından işleci.

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
        << "the target bitset b1 becomes:   ( "<< b1 << " )."
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

## <a name="op_lshift"></a> bitset::operator\<\<

Bir bitset bitler belirli sayıdaki uzaklığına sola kaydırılır ve yeni bir bitset için sonuç döndürür.

```cpp
bitset\<N> operator<<(size_t _Pos) const;
```

### <a name="parameters"></a>Parametreler

*_Pos*<br/>
Bitset bitler kaydırılmasına olan sol konumlara sayısı.

### <a name="return-value"></a>Dönüş Değeri

BITS ile değiştirilmiş bitset konumları gereken sayıda sola kaydırılır.

### <a name="remarks"></a>Açıklamalar

Üye işleç işlevinin döndürdüğü **bitset**(  **\*bu**) **<< pos, =** burada [ <<= ](#op_lshift_eq) kaydırır Sol taraftaki belirli sayıdaki uzaklığına bir bitset bitler ve için hedeflenen bitset sonucu döndürür.

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

## <a name="op_lshift_eq"></a>  bitset::operator&lt;&lt;=

Bir bitset bitler belirli sayıdaki uzaklığına sola kaydırılır ve için hedeflenen bitset sonucu döndürür.

```cpp
bitset\<N>& operator<<=(size_t _Pos);
```

### <a name="parameters"></a>Parametreler

*_Pos*<br/>
Sol kaydırılmasına bitset bitler olan konumlara sayısı.

### <a name="return-value"></a>Dönüş Değeri

BITS değerinin değiştirilmesi hedeflenen bitset sola kaydırılacak konum gerekli sayısı.

### <a name="remarks"></a>Açıklamalar

Konumuna kaydırmak için herhangi bir öğe varsa, işlev bir değer bite 0 temizler.

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
        << "the target bitset b1 becomes: ( "<< b1 << " )."
        << endl;
}
```

```Output
The target bitset b1 is: ( 00111 ).
After shifting the bits 2 positions to the left,
the target bitset b1 becomes: ( 11100 ).
```

## <a name="op_eq_eq"></a>  bitset::operator ==

Belirtilen bitset ile bir hedef bitset eşitliği sınar.

```cpp
bool operator==(const bitset\<N>& right) const;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Hedef bitset eşitlik için karşılaştırılması gereken olan bitset.

### <a name="return-value"></a>Dönüş Değeri

**doğru** bitsets; aynıysa **false** farklı olmaları durumunda.

### <a name="remarks"></a>Açıklamalar

Bitsets üye işleci işlevi tarafından eşitlik için test edilecek aynı boyutta olması gerekir.

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

## <a name="op_rshift"></a>  bitset::operator&gt;&gt;

Bir bitset bitler belirli sayıdaki uzaklığına sağa doğru kayar ve için yeni bir bitset sonucu döndürür.

```cpp
bitset\<N> operator>>(size_t _Pos) const;
```

### <a name="parameters"></a>Parametreler

*_Pos*<br/>
Bitset bitler kaydırılmasına olan konum sağındaki sayısı.

### <a name="return-value"></a>Dönüş Değeri

BITS olduğu yere bir yeni bitset hedeflenen bitset göreli konum gerekli sayısına sağa doğru kayar.

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
        << "the bitset b2 is: ( "<< b2 << " )."
        << endl;
   bitset<5> b3 = b2 >> 1;

   cout << "After shifting the bits 1 position to the right,\n"
        << "the bitset b3 is: ( " << b3 << " )."
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

## <a name="op_rshift_eq"></a>  bitset::operator&gt;&gt;=

Bir bitset bitler belirli sayıdaki uzaklığına sağa doğru kayar ve için hedeflenen bitset sonucu döndürür.

```cpp
bitset\<N>& operator>>=(size_t _Pos);
```

### <a name="parameters"></a>Parametreler

*_Pos*<br/>
Bitset bitler kaydırılmasına olan konum sağındaki sayısı.

### <a name="return-value"></a>Dönüş Değeri

BITS değerinin değiştirilmesi hedeflenen bitset konum gerekli sayısına sağa doğru kayar.

### <a name="remarks"></a>Açıklamalar

Konumuna kaydırmak için herhangi bir öğe varsa, işlev bir değer bite 0 temizler.

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
        << "the target bitset b1 becomes: ( "<< b1 << " )."
        << endl;
}
```

```Output
The target bitset b1 is: ( 11100 ).
After shifting the bits 2 positions to the right,
the target bitset b1 becomes: ( 00111 ).
```

## <a name="op_at"></a>  bitset::operator]

Bitset değiştirilebilir bir bit bir bitset belirtilen konumda bir başvuru döndürür; Aksi takdirde, bu konumda bit değerini döndürür.

```cpp
bool operator[](size_t _Pos) const;
reference operator[](size_t _Pos);
```

### <a name="parameters"></a>Parametreler

*_Pos*<br/>
Bitset içindeki bit bulma konumu.

### <a name="remarks"></a>Açıklamalar

Tanımladığınızda [ \_YİNELEYİCİ\_hata ayıklama\_düzeyi](../standard-library/iterator-debug-level.md) bitset sınırları dışında bir öğeye erişmeyi denerseniz, 1 veya 2 derleme olarak, bir çalışma zamanı hatası yürütülebilir dosyanın içinde oluşur. Daha fazla bilgiler için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

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

## <a name="op_xor_eq"></a>  bitset::operator^=

Özel ile bitsets Bitsel bir birleşimi gerçekleştirir `OR` işlemi.

```cpp
bitset\<N>& operator^=(const bitset\<N>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bit düzeyinde hedef bitset ile birleştirilecek olan bitset.

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde özel sonuçları değiştirilmiş hedef bitset `OR` parametre olarak belirtilen bitset işlemi.

### <a name="remarks"></a>Açıklamalar

İki bit birleştirilmiş tarafından özel **veya** işleci dönüş **true** en az bir, ancak iki değil, BITS **true**; Aksi takdirde bunlarınbirbileşiminidöndürür**false**.

Bit düzeyinde dışlamalı ile birleştirilecek aynı boyutta olması Bitsets `OR` üye işleç işlevini işleciyle.

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
        << "the target bitset b1 becomes:   ( "<< b1 << " )."
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

## <a name="op_or_eq"></a>  bitset::operator&#124;=

Kapsamlı ile bitsets Bitsel bir birleşimi gerçekleştirir `OR` işlemi.

```cpp
bitset\<N>& operator|=(const bitset\<N>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bit düzeyinde hedef bitset ile birleştirilecek olan bitset.

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde sonuçları değiştirilmiş hedef bitset kapsamlı `OR` parametre olarak belirtilen bitset işlemi.

### <a name="remarks"></a>Açıklamalar

Kapsamlı tarafından birleştirilmiş iki bit `OR` işleci dönüş **true** en az bir bit ise **true**; her iki bit **false**, bunların bir bileşimini döndürür **false**.

Bit düzeyinde kapsamlı birleştirilmek üzere aynı boyutta olması Bitsets `OR` üye işleci işlevi tarafından işleci.

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
        << "the target bitset b1 becomes:   ( "<< b1 << " )."
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

## <a name="op_not"></a>  bitset::operator ~

Bir hedef bitset içindeki tüm bitleri tersine çevirir ve sonucu döndürür.

```cpp
bitset\<N> operator~() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bitset hedeflenen bitset göre tersine, BITS ile.

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

## <a name="reference"></a>  bitset::Reference

Başvuruların bitlere atanmasına erişmek ve tek tek bitleri için yardımcı sınıfı olarak işlemek için kullanılan bir bitset bulunan sağlayan bir ara sunucu sınıf `operator[]` sınıfı bitset biri.

```cpp
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

*VAL*<br/>
Nesne türü değeri **bool** biraz içinde bir bitset atanacak.

*_Bitref*<br/>
Bir formun başvurusu *x [i]* konumunda bit *miyim* bitset içinde *x*.

### <a name="return-value"></a>Dönüş Değeri

Bitset sınıfı başvuru beşinci üye işlevleri ve birinci, ikinci bağımsız değişken konumu tarafından belirtilen bit başvuru ve **true** veya **false**değiştirilmiş bit değerini yansıtmak için bitset sınıfı başvuru üçüncü ve dördüncü üye işlevleri için.

### <a name="remarks"></a>Açıklamalar

Sınıf `reference` bitset yardımcı bir sınıf olarak yalnızca mevcut `operator[]`. Üye sınıfı bir bitset içinde tek bir bit erişebilen bir nesneyi tanımlar. İzin *b* türünde bir nesne olması **bool**, *x* ve *y* türünden nesnelerin **bitset\<**  *N* **>**, ve *miyim* ve *j* böyle bir nesnenin içinde geçerli konumları. Bu gösterim *x [i]* bit konuma başvuran *miyim* bitset içinde *x*. Sınıfın üye işlevleri `reference` , sırayla şu işlemleri sağlar:

|Çalışma|Tanım|
|---------------|----------------|
|*x*[*i*] = *b*|Depoları **bool** değer *b* bit konumunda *miyim* bitset içinde *x*.|
|*x*[*i*] = *y*[*j*]|Bit değeri depolar *y*[ *j*] bit konumunda *miyim* bitset içinde *x*.|
|*b* = ~ *x*[*i*]|Bit çevrilen değerini depolar *x*[ *miyim*] içinde **bool** *b*.|
|*b* = *x*[*i*]|Bit değeri depolar *x*[ *miyim*] içinde **bool** *b*.|
|*x*[*i*]. `flip`( )|Bit çevrilen değerini depolar *x*[ *miyim*] geri bit konumunda *miyim* içinde *x*.|

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
        << "is: ( "<< b1 << " )" << endl;

   // Example of x [i] = y [j] storing the bool value of the
   // bit at position j in bitset y at bit position i in bitset x
   b2 [4] = b1 [0];      // b1 [0] = true
   cout << "The bitset<5> b2 with the bit at position 4 set to the "
        << "value\nof the bit at position 0 of the bit in "
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
        << "bitset b2,\nit is ( "<<  b2  << " )." << endl;
   b2 [4].flip( );
   cout << "After flipping the value of the bit at position 4 in "
        << "bitset b2,\nit becomes ( "<<  b2  << " )." << endl;
   bool c;
   c = b2 [4].flip( );
   cout << "After a second flip, the value of the position 4 "
        << "bit in b2 is now: " << c << ".";
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

## <a name="reset"></a>  bitset::reset

Bir bitset içindeki tüm bitleri 0 değerine Sıfırlanan veya 0 belirtilen konumda bir bit sıfırlar.

```cpp
bitset\<N>& reset();
bitset\<N>& reset(size_t _Pos);
```

### <a name="parameters"></a>Parametreler

*_Pos*<br/>
Bit konumu 0 olarak sıfırlanması bitset içinde.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi en iyi duruma çağrıldı bitset bir kopyası.

### <a name="remarks"></a>Açıklamalar

İkinci üye işlevi oluşturur bir [out_of_range](../standard-library/out-of-range-class.md) belirtilen konumu bitset boyutundan büyükse, özel durum.

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
        << "third bit of bitset b1 is: ( "<< b1r3 << " )"
        << endl;

   bitset<5> b1r;
   b1r = b1.reset( );
   cout << "The collecion of bits obtained from resetting all\n"
        << "the elements of the bitset b1 is: ( "<< b1r << " )"
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

## <a name="set"></a>  bitset::set

Tüm bitleri 1 veya kümeleri bir bitset biraz 1 belirtilen konumda ayarlar.

```cpp
bitset\<N>& set();

bitset\<N>& set(
    size_t _Pos,
    bool val = true);
```

### <a name="parameters"></a>Parametreler

*_Pos*<br/>
Bit konumu bitset ayarlamak için bir değer atanır.

*VAL*<br/>
Belirtilen konumdaki bite atanacak değer.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi en iyi duruma çağrıldı bitset bir kopyası.

### <a name="remarks"></a>Açıklamalar

İkinci üye işlevi oluşturur bir [out_of_range](../standard-library/out-of-range-class.md) belirtilen konumu bitset boyutundan büyükse, özel durum.

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
        << "zeroth bit of bitset b1 is: ( "<< b1s0 << " )"
        << endl;

   bitset<5> bs1;
   bs1 = b1.set( );
   cout << "The collecion of bits obtained from setting all the\n"
        << "elements of the bitset b1 is: ( "<< bs1 << " )"
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

## <a name="size"></a>  bitset::size

Bitset nesnesinde bit sayısını döndürür.

```cpp
size_t size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit sayısını *N*, içinde bir bitset\<N >.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bitset::size üye işlevinin kullanımını gösterir.

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

## <a name="test"></a>  bitset::test

Belirtilen bir konumda bir bitset bit 1 olarak ayarlanmış olup olmadığını sınar.

```cpp
bool test(size_t _Pos) const;
```

### <a name="parameters"></a>Parametreler

*_Pos*<br/>
Bitset değeri için test edilecek bit konumu.

### <a name="return-value"></a>Dönüş Değeri

**doğru** 1'e; bağımsız değişken konumu tarafından belirtilen bit ayarlanmışsa, aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Üye işlevin bir [out_of_range](../standard-library/out-of-range-class.md)

## <a name="to_string"></a> bitset::to_string

Bitset nesnesini bir dize gösterimine dönüştürür.

```
template <class charT = char, class traits = char_traits<charT>, class Allocator = allocator<charT> >
   basic_string<charT, traits, Allocator> to_string(charT zero = charT('0'), charT one = charT('1')) const;
```

### <a name="return-value"></a>Dönüş değeri

Sınıfın bir dize nesnesi `basic_string`, burada her içinde bitset biti 1 karaktere karşılık gelen bir sahip ve bir karakter 0 ise, biti ayarlanmamış.

### <a name="example"></a>Örnek

```cpp
// bitset_to_string.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 7 );

   cout << "The ordered set of bits in the bitset<5> b1( 7 )"
        << "\n  that was generated by the number 7 is: ( "
        << b1 << " )" << endl;

   string s1;
   s1 =  b1.template to_string<char, 
   char_traits<char>, allocator<char> >( );
   cout << "The string returned from the bitset b1"
        << "\n  by the member function to_string( ) is: "
        << s1 << "." << endl;
}
```

```Output
The ordered set of bits in the bitset<5> b1( 7 )
  that was generated by the number 7 is: ( 00111 )
The string returned from the bitset b1
  by the member function to_string( ) is: 00111.
```

## <a name="to_ullong"></a> bitset::to_ullong

Döndürür bir **işaretsiz long long** aynı BITS içeren değer bitset nesnenin içeriğini ayarlayın.

```
unsigned long long to_ullong() const;
```

### <a name="return-value"></a>Dönüş değeri

Bit sırada bit değerlerin toplamını geri döndüren bir **işaretsiz long long**. Bu **işaretsiz long long** değeri yeniden oluşturursanız aynı belirlenmiş bitleri bir bitset başlatmak için kullanılır.

### <a name="exceptions"></a>Özel Durumlar

Oluşturur bir [overflow_error](overflow-error-class.md) bit dizideki herhangi bir bit olan bir bit değeri, nesne türünde bir değer gösterilemez **işaretsiz long long**.

### <a name="remarks"></a>Açıklamalar

Bit sırada bit değerlerin toplamını geri döndüren bir **işaretsiz long long**.

## <a name="to_ulong"></a> bitset::to_ulong

Bitset nesne bitset başlatmak için kullanılan, içerdiği bit dizisini oluşturur bir tamsayıya dönüştürür.

```
unsigned long to_ulong( ) const;
```

### <a name="return-value"></a>Dönüş değeri

BITS bir bitset bitset başlatmada kullanılan üretir bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Üye işlevini uygulayarak BITS bitset içinde yer alan bir dizi içinde bulunan aynı 1 ve 0 basamak dizisi içeren tamsayı döndürür.

Üye işlevin bir [overflow_error](overflow-error-class.md) bit dizideki herhangi bir bit olan bir bit değeri, nesne türünde bir değer gösterilemez **işaretsiz uzun**.

### <a name="example"></a>Örnek

```cpp
// bitset_to_ulong.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 7 );

   cout << "The ordered set of bits in the bitset<5> b1( 7 )"
        << "\n  that was generated by the number 7 is: ( "
        << b1 << " )" << endl;

   unsigned long int i;
   i = b1.to_ulong( );
   cout << "The integer returned from the bitset b1,"
        << "\n  by the member function to_long( ), that"
        << "\n  generated the bits as a base two number is: "
        << i << "." << endl;
}
```

```Output
The ordered set of bits in the bitset<5> b1( 7 )
  that was generated by the number 7 is: ( 00111 )
The integer returned from the bitset b1,
  by the member function to_long( ), that
  generated the bits as a base two number is: 7.
```

## <a name="see-also"></a>Ayrıca bkz.

[\<bitset >](bitset.md)<br/>
[bitset işleçleri](bitset-operators.md)<br/>
