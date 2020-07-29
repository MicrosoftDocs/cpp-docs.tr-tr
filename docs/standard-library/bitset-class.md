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
ms.openlocfilehash: 9a822e635ea3a1fd035a6a4b1d2b38250c96158a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217850"
---
# <a name="bitset-class"></a>bitset Sınıfı

Öğelerin veya koşulların bir kümesi için bayrakları tutmanın kompakt bir yolunu sağlayan sabit bir bit sayısından oluşan bir diziyi depolayan bir nesne türünü tanımlar. Bitset sınıfı bit kümesi türündeki nesneler üzerinde işlemleri destekler ve her bir bit için sabit zamanlı erişim sağlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <size_t N>
class bitset
```

### <a name="parameters"></a>Parametreler

*No*\
Bit kümesi nesnesindeki bit sayısını, `size_t` derleme zamanında bilinmesi gereken, sıfır dışında bir tamsayı olan türde belirtir.

## <a name="remarks"></a>Açıklamalar

Benzer [vektör \<bool> sınıfından](../standard-library/vector-bool-class.md)farklı olarak, bitset Sınıfı yineleyiciler Içermez ve bir C++ standart kitaplık kapsayıcısı değildir. Ayrıca \<bool> , **bit kümesi \<N\> ** bildirildiği zaman, *N* şablon parametresi tarafından belirtilen boyuta uygun olarak, derleme zamanında düzeltilen belirli bir boyut kadar vektörden farklılık gösterir.

Değeri 1 ise ve değeri 0 ise sıfırlandığında bir bit ayarlanır. Bir biti çevirmek veya tersine çevirmek için değerini 1 ' den 0 ' a veya 0 ' dan 1 ' e değiştirin. Bitset içindeki *N* bitleri, 0 ile *N* -1 arasındaki tamsayı değerleriyle dizinlenir; burada 0, Ilk bit konumu ve *n* -1 son bit konumunu oluşturur.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[bitset](#bitset)|Sınıfının bir nesnesini oluşturur `bitset\<N>` ve bitleri sıfıra, belirli bir değere veya bir dizedeki karakterlerden elde edilen değerlere başlatır.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[element_type](#element_type)|Veri türü için eş anlamlı bir tür **`bool`** ve içindeki öğe bitlerini başvurmak için kullanılabilir `bitset` .|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[Bütün](#all)|`bitset`Bunların tümünün olarak ayarlanmış olup olmadığını anlamak için bu tüm bitleri sınar **`true`** .|
|[kaydedilmemiş](#any)|Üye işlevi, dizideki herhangi bir bitin 1 olarak ayarlanmış olup olmadığını sınar.|
|[biriktirme](#count)|Üye işlevi, bit dizisinde ayarlanan bit sayısını döndürür.|
|[yazmayı](#flip)|' Deki tüm bitlerin değerini tersine çevirir `bitset` veya belirtilen konumda tek bir bit 'e ters çevirir.|
|[yok](#none)|Bir nesne içinde 1 olarak ayarlanmış bir bit yoksa sınar `bitset` .|
|[döndürmek](#reset)|A içindeki tüm bitleri 0 ' a sıfırlar `bitset` veya belirtilen konumdaki bir biti 0 olarak sıfırlar.|
|[kurmak](#set)|A 'daki tüm bitleri 1 ' `bitset` e ayarlar veya belirtilen konumdaki bir bit ' i 1 olarak ayarlar.|
|[boyutla](#size)|Bir nesnedeki bit sayısını döndürür `bitset` .|
|[sınamanız](#test)|İçindeki belirtilen konumdaki bitin 1 olarak ayarlanmış olup olmadığını sınar `bitset` .|
|[to_string](#to_string)|Bir `bitset` nesneyi dize gösterimine dönüştürür.|
|[to_ullong](#to_ullong)|İçindeki bit değerlerinin toplamını döndürür `bitset` **`unsigned long long`** .|
|[to_ulong](#to_ulong)|' A bir `bitset` nesnesi, **`unsigned long`** başlatmak için kullanılmışsa içerilen bit dizisini üretecek öğesine dönüştürür `bitset` .|

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[başvurunun](#reference)|`bitset`Sınıfı için bir yardımcı sınıf olarak tek tek bitleri erişmek ve işlemek için kullanılan, içinde bulunan bit sayısına başvurular sağlayan bir proxy sınıfı `operator[]` `bitset` .|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç! =](#op_neq)|`bitset`Belirtilen ile eşitsizlik için hedefi sınar `bitset` .|
|[işleç&=](#op_and_eq)|Mantıksal bir işlemle Bitsets 'in bit düzeyinde birleşimini uygular `AND` .|
|[işleç<<](#op_lshift)|Bit içindeki bitleri `bitset` belirtilen sayıda konum sola kaydırır ve sonucu yeni bir olarak döndürür `bitset` .|
|[işleç<<=](#op_lshift_eq)|Bit içindeki bitleri `bitset` belirtilen sayıda konum sola kaydırır ve sonucu hedeflenen öğesine döndürür `bitset` .|
|[işleç = =](#op_eq_eq)|Bir hedefi `bitset` , belirtilen bir eşitlik için sınar `bitset` .|
|[işleç>>](#op_rshift)|Bit içindeki bitleri `bitset` belirtilen sayıda konum sağına kaydırır ve sonucu yeni bir olarak döndürür `bitset` .|
|[işleç>>=](#op_rshift_eq)|Bit içindeki bitleri `bitset` belirtilen sayıda konum sağına kaydırır ve sonucu hedeflenen öğesine döndürür `bitset` .|
|[işleç&#91;&#93;](#op_at)|Değiştirilebilir ise, belirtilen konumdaki bir bite bir başvuru döndürür `bitset` `bitset` ; Aksi takdirde, o konumdaki bit değerini döndürür.|
|[işleç ^ =](#op_xor_eq)|Özel işlemle Bitsets 'in bit düzeyinde birleşimini uygular `OR` .|
|[işleç&#124;=](#op_or_eq)|Kapsamlı işlemle Bitsets 'in bit düzeyinde birleşimini uygular `OR` .|
|[işleç ~](#op_not)|Bir hedefteki tüm bitleri ters çevirir `bitset` ve sonucu döndürür.|

### <a name="structures"></a>Yapılar

|||
|-|-|
|[yla](#hash)||

### <a name="all"></a><a name="all"></a>Bütün

Bu bit kümesindeki tüm bitleri, tümünün true olarak ayarlandığını belirleyecek şekilde sınar.

```cpp
bool all() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Bu küme içindeki tüm bitler true ise true döndürür. **`false`** Bir veya daha fazla bitlerin yanlış olduğunu döndürür.

### <a name="any"></a><a name="any"></a>kaydedilmemiş

Dizideki herhangi bir bitin 1 olarak ayarlanmış olup olmadığını sınar.

```cpp
bool any() const;
```

#### <a name="return-value"></a>Dönüş Değeri

**`true`** bitset içinde herhangi bir bit 1 olarak ayarlandıysa; **`false`** tüm bitleri 0 ise.

#### <a name="example"></a>Örnek

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

### <a name="bitset"></a><a name="bitset"></a>bitset

Sınıfının bir nesnesini oluşturur `bitset\<N>` ve bitleri sıfıra veya belirli bir değere ya da bir dizedeki karakterlerden elde edilen değerlere başlatır.

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

#### <a name="parameters"></a>Parametreler

*Acil*\
Oluşturulan bitset içindeki bitleri başlatmak için temel iki temsili kullanan işaretsiz tamsayı.

*üstbilgisine*\
Bitset bit değerlerini başlatmak için kullanılan sıfırların ve bunların dizesi.

*_CStr*\
Bit kümesi bit değerlerini başlatmak için kullanılan sıfırlar ve sıfırlardan oluşan C stili bir dize.

*_Pos*\
Bit kümesindeki ilk biti başlatmak için kullanılan, dizenin karakter, soldan sağa ve sıfıra başlayarak sıfır olarak sayımının bulunduğu konum.

*biriktirme*\
Bit kümesindeki bitlerin başlangıç değerlerini sağlamak için kullanılan dizedeki karakterlerin sayısı.

*_Zero*\
Bir sıfırı temsil etmek için kullanılan karakter. Varsayılan değer ' 0 ' dır.

*_One*\
Bir tane temsil etmek için kullanılan karakter. Varsayılan değer ' 1 ' dir.

#### <a name="remarks"></a>Açıklamalar

Sınıfının obects 'leri oluşturmak için üç Oluşturucu kullanılabilir `bitset\<N>` :

- İlk Oluşturucu hiçbir parametre kabul etmez, sınıfının bir nesnesini oluşturur `bitset\<N>` ve tüm N bitleri varsayılan sıfır değerine başlatır.

- İkinci Oluşturucu, sınıfının bir nesnesini oluşturur `bitset\<N>` ve tek parametresini kullanarak bitleri başlatır **`unsigned long long`** .

- Üçüncü Oluşturucu, `bitset\<N>` N bitini, sıfırlardan oluşan c stili karakter dizesinde belirtilen karakterlere karşılık gelen değerlere başlatarak, bir sınıfının nesnesini oluşturur. Oluşturucuyu dizeyi bir dize türüne atamadan çağırın:`bitset<5> b5("01011");`

Ayrıca, iki Oluşturucu şablonu sağlanır:

- İlk Oluşturucu şablonu, sınıfının bir nesnesini oluşturur `bitset\<N>` ve bir sıfır dizesinde belirtilen karakterlerden bitleri başlatır. Dizedeki herhangi bir karakter 0 veya 1 ' den büyükse, Oluşturucu [geçersiz bağımsız değişken](../standard-library/invalid-argument-class.md)sınıfından bir nesne oluşturur. Belirtilen konum (*_Pos*) dizenin uzunluğunun ötesinde, Oluşturucu [out_of_range](../standard-library/out-of-range-class.md)sınıfının bir nesnesini oluşturur. Oluşturucu yalnızca, konumdaki dizedeki karakteri 1 olan bit kümesinde *j* konumunda bulunan bitleri ayarlar `_Pos + j` . Varsayılan olarak, *_Pos* 0 ' dır.

- İkinci Oluşturucu şablonu ilki ile benzerdir, ancak başlatılacak bit sayısını belirtmek için kullanılan ek bir parametre (*Count*) içerir. Ayrıca, *Str* içindeki hangi karakterin 0 bit ve 1 bit olmak üzere yorumlanması gerektiğini belirten *_Zero* ve *_One*iki isteğe bağlı parametreye sahiptir.

#### <a name="example"></a>Örnek

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

### <a name="count"></a><a name="count"></a>biriktirme

Bit dizisinde ayarlanan bit sayısını döndürür.

```cpp
size_t count() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Bit dizisinde ayarlanan bit sayısı.

#### <a name="example"></a>Örnek

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

### <a name="element_type"></a><a name="element_type"></a>element_type

Veri türü için bir eş anlamlı olan **`bool`** ve bir bitset içindeki öğe bitlerini başvurmak için kullanılabilen bir tür.

```cpp
typedef bool element_type;
```

#### <a name="example"></a>Örnek

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

### <a name="flip"></a><a name="flip"></a>yazmayı

Bit kümesindeki tüm bitlerin değerini tersine çevirir veya belirtilen konumda tek bir bit 'e ters çevirir.

```cpp
bitset\<N>& flip();
bitset\<N>& flip(size_t _Pos);
```

#### <a name="parameters"></a>Parametreler

*_Pos*\
Değer ters çevrilme yapılacak bit konumu.

#### <a name="return-value"></a>Dönüş Değeri

Üye işlevin çağrıldığı değiştirilmiş bitset 'in bir kopyası.

#### <a name="remarks"></a>Açıklamalar

İkinci üye işlevi, bir parametre olarak belirtilen konum, biti ters çevrilen **bitset \<** *N* **> ** değerinden büyükse [out_of_range](../standard-library/out-of-range-class.md) bir özel *N* durum oluşturur.

#### <a name="example"></a>Örnek

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

### <a name="hash"></a><a name="hash"></a>yla

```cpp
template <class T> struct hash;
template <size_t N> struct hash<bitset<N>>;
```

### <a name="none"></a><a name="none"></a>seçim

Bitset nesnesinde hiçbir bit 1 olarak ayarlanmamışsa sınar.

```cpp
bool none() const;
```

#### <a name="return-value"></a>Dönüş Değeri

**`true`** bitset içinde hiçbir bit 1 olarak ayarlanmamışsa; **`false`** en az bir bit 1 olarak ayarlanmışsa.

#### <a name="example"></a>Örnek

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

### <a name="operator"></a><a name="op_neq"></a>işleç! =

Belirtilen bit kümesiyle eşitsizlik için bir hedef bit kümesini sınar.

```cpp
bool operator!=(const bitset\<N>& right) const;
```

#### <a name="parameters"></a>Parametreler

*Right*\
Eşitsizlik için hedef bit kümesiyle Karşılaştırılacak bit kümesi.

#### <a name="return-value"></a>Dönüş Değeri

**`true`** Bitsets 'ler farklıysa; **`false`** varsa.

#### <a name="remarks"></a>Açıklamalar

Bitsets 'ler, Üye operatörü işlevi tarafından eşitsizlik için test edilecek boyutta olmalıdır.

#### <a name="example"></a>Örnek

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

### <a name="operatoramp"></a><a name="op_and_eq"></a>işlecinde&amp;=

Mantıksal bir işlemle Bitsets 'in bit düzeyinde birleşimini uygular `AND` .

```cpp
bitset\<N>& operator&=(const bitset\<N>& right);
```

#### <a name="parameters"></a>Parametreler

*Right*\
Hedef bitset ile bit düzeyinde birleştirilecek bit kümesi.

#### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde `AND` işlem tarafından parametre olarak belirtilen bit kümesi ile sonuçlanan değiştirilen Target bit kümesi.

#### <a name="remarks"></a>Açıklamalar

Her bir bit doğru ise, işleç tarafından birleştirilmiş iki bit döndürülür `AND` **`true`** ; Aksi takdirde, bunların birleşimi döndürülür **`false`** .

Bitsets 'ler, `AND` işleç ile üye işleci işlevi ile birleştirilerek aynı boyutta olmalıdır.

#### <a name="example"></a>Örnek

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

### <a name="operator"></a><a name="op_lshift"></a>işlecinde\<\<

Bit kümesindeki bitleri belirtilen sayıda konum sola kaydırır ve sonucu yeni bir bit kümesine döndürür.

```cpp
bitset\<N> operator<<(size_t _Pos) const;
```

#### <a name="parameters"></a>Parametreler

*_Pos*\
Sol tarafta bit kümesindeki bitlerin kaydırılacağı konum sayısı.

#### <a name="return-value"></a>Dönüş Değeri

BITS ile değiştirilen bit kümesi, gereken sayıda konum için sola kaydırır.

#### <a name="remarks"></a>Açıklamalar

Üye işleci işlevi **bitset**( ** \* this**) **<<= POS döndürür,** burada [<<=](#op_lshift_eq) bit kümesindeki bitler belirtilen sayıda konum sola kayar ve sonuç hedeflenen bitset 'e döndürülür.

#### <a name="example"></a>Örnek

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

### <a name="operatorltlt"></a><a name="op_lshift_eq"></a>işlecinde&lt;&lt;=

Bit kümesindeki bitleri belirtilen sayıda konum sola kaydırır ve sonucu hedeflenen bitset 'e döndürür.

```cpp
bitset\<N>& operator<<=(size_t _Pos);
```

#### <a name="parameters"></a>Parametreler

*_Pos*\
Bit kümesindeki bitlerin sol tarafındaki konumların sayısı kaydırılacağı.

#### <a name="return-value"></a>Dönüş Değeri

Hedeflenen bitset, bitlerin istenen sayıda konum için sola kaydırılacağı şekilde değiştirildi.

#### <a name="remarks"></a>Açıklamalar

Konuma kaydıramak için bir öğe yoksa, işlev, biti 0 değerine temizler.

#### <a name="example"></a>Örnek

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

### <a name="operator"></a><a name="op_eq_eq"></a>işleç = =

Belirtilen bit kümesiyle eşitlik için bir hedef bit kümesini sınar.

```cpp
bool operator==(const bitset\<N>& right) const;
```

#### <a name="parameters"></a>Parametreler

*Right*\
Eşitlik için hedef bit kümesiyle Karşılaştırılacak bit kümesi.

#### <a name="return-value"></a>Dönüş Değeri

**`true`** Bitsets 'ler aynıysa; **`false`** bunlar farklıysa.

#### <a name="remarks"></a>Açıklamalar

Bitsets 'ler, Üye operatörü işlevi tarafından eşitlik için test edilecek boyutta olmalıdır.

#### <a name="example"></a>Örnek

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

### <a name="operatorgtgt"></a><a name="op_rshift"></a>işlecinde&gt;&gt;

Bit kümesindeki bitleri belirtilen sayıda konum sağına kaydırır ve sonucu yeni bir bit kümesine döndürür.

```cpp
bitset\<N> operator>>(size_t _Pos) const;
```

#### <a name="parameters"></a>Parametreler

*_Pos*\
Bitset 'teki bitlerin sağ tarafındaki konumların sayısı kaydırılacağı.

#### <a name="return-value"></a>Dönüş Değeri

Bitlerin hedeflenen bitset 'e göre gereken sayıda konuma doğru kaydırılacağı yeni bir bit kümesi.

#### <a name="example"></a>Örnek

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

### <a name="operatorgtgt"></a><a name="op_rshift_eq"></a>işlecinde&gt;&gt;=

Bit kümesindeki bitleri belirtilen sayıda konum sağına kaydırır ve sonucu hedeflenen bitset 'e döndürür.

```cpp
bitset\<N>& operator>>=(size_t _Pos);
```

#### <a name="parameters"></a>Parametreler

*_Pos*\
Bitset 'teki bitlerin sağ tarafındaki konumların sayısı kaydırılacağı.

#### <a name="return-value"></a>Dönüş Değeri

Hedeflenen bitset, bitlerin gerekli sayıda konum sağına kaydırılacağı şekilde değiştirildi.

#### <a name="remarks"></a>Açıklamalar

Konuma kaydıramak için bir öğe yoksa, işlev, biti 0 değerine temizler.

#### <a name="example"></a>Örnek

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

### <a name="operator"></a><a name="op_at"></a>operator []

Bitset değiştirilebilir ise, bit kümesinde belirtilen konumdaki bir bite bir başvuru döndürür; Aksi takdirde, bu konumdaki bit değerini döndürür.

```cpp
bool operator[](size_t _Pos) const;
reference operator[](size_t _Pos);
```

#### <a name="parameters"></a>Parametreler

*_Pos*\
Bit kümesi içindeki bit konumunu bulma konumu.

#### <a name="remarks"></a>Açıklamalar

Derlemede 1 veya 2 olarak [ \_ Yineleyici \_ hata ayıklama \_ düzeyi](../standard-library/iterator-debug-level.md) tanımladığınızda, bit kümesinin sınırları dışında bir öğeye erişmeyi denerseniz yürütülebilir dosyada bir çalışma zamanı hatası oluşur. Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md).

#### <a name="example"></a>Örnek

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

### <a name="operator"></a><a name="op_xor_eq"></a>işleç ^ =

Özel işlemle Bitsets 'in bit düzeyinde birleşimini uygular `OR` .

```cpp
bitset\<N>& operator^=(const bitset\<N>& right);
```

#### <a name="parameters"></a>Parametreler

*Right*\
Hedef bitset ile bit düzeyinde birleştirilecek bit kümesi.

#### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde dışlamalı `OR` işlem, parametre olarak belirtilen bitset ile sonuçlanan değiştirilen Target bit kümesi.

#### <a name="remarks"></a>Açıklamalar

Bit **ya** da işleçle birleştirilmiş iki bit, **`true`** en az bir, ancak bitlerin her ikisi de olmasa da döndürülür **`true`** ; Aksi takdirde, bunların kombinasyonu döndürülür **`false`** .

Bitsets 'ler, `OR` Üye operatörü işlevi tarafından dışlamalı işleçle birleştirilerek aynı boyutta olmalıdır.

#### <a name="example"></a>Örnek

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

### <a name="operator124"></a><a name="op_or_eq"></a>işleç&#124;=

Kapsamlı işlemle Bitsets 'in bit düzeyinde birleşimini uygular `OR` .

```cpp
bitset\<N>& operator|=(const bitset\<N>& right);
```

#### <a name="parameters"></a>Parametreler

*Right*\
Hedef bitset ile bit düzeyinde birleştirilecek bit kümesi.

#### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde kapsamlı `OR` işlem tarafından parametre olarak belirtilen bitset ile sonuçlanan değiştirilen Target bit kümesi.

#### <a name="remarks"></a>Açıklamalar

`OR` **`true`** Bir bitten en az biri olduğunda, birlikte bulunan işleci tarafından birleştirilmiş iki bit bulunur **`true`** ; her iki bit de varsa **`false`** , bunların birleşimi döndürür **`false`** .

Bitsets 'ler, `OR` Üye operatörü işlevi tarafından birlikte bulunan işleçle birleştirilerek bit düzeyinde birleştirilecek boyutta olmalıdır.

#### <a name="example"></a>Örnek

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

### <a name="operator"></a><a name="op_not"></a>işleç ~

Bir hedef bit kümesindeki tüm bitleri ters çevirir ve sonucu döndürür.

```cpp
bitset\<N> operator~() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Tüm bitleri ters çevrilerek hedeflenen bitset 'e göre bitset.

#### <a name="example"></a>Örnek

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

### <a name="reference"></a><a name="reference"></a>başvurunun

Bit kümesinde bulunan bitlerin bir bit kümesinde bulunan ve bit kümesi için bir yardımcı sınıf olarak tek tek bitleri erişmek ve işlemek için kullanılan bitler için başvurular sağlayan bir proxy sınıfı `operator[]` .

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

#### <a name="parameters"></a>Parametreler

*Acil*\
**`bool`** Bit kümesindeki bir bite atanacak olan nesne değeri.

*_Bitref*\
*X [i]* biçimindeki bir, bitset *x*içinde *i* konumundaki bite bir başvuru.

#### <a name="return-value"></a>Dönüş Değeri

Bit kümesinde, sınıf başvurusunun birinci, ikinci ve beşinci üye işlevleri için bağımsız değişken konumuyla belirtilen bit kümesindeki bir başvuru ve **`true`** veya **`false`** , sınıf başvurusunun üçüncü ve dördüncü üye işlevleri için bit kümesinde değiştirilen bitin değerini yansıtacak şekilde.

#### <a name="remarks"></a>Açıklamalar

Sınıfı `reference` yalnızca bitset için yardımcı sınıf olarak mevcuttur `operator[]` . Üye sınıfı bir bit kümesindeki tek bir bite erişebilen bir nesneyi tanımlar. *B* 'nin bir nesne **`bool`** içinde ** \<** *N* **> bitset**ve *i* ve *j* türünde nesne türünde, *x* ve *y* nesnelerinin bir nesnesi olmasına izin verin. *X [i]* gösterimi bitset *x*içinde *i* konumundaki bit 'e başvuruyor. Sınıfının üye işlevleri, `reference` aşağıdaki işlemleri sırasıyla sağlar:

|İşlem|Tanım|
|---------------|----------------|
|*x*[*i*] = *b*|**`bool`** *B* değerini bitset *x*' te *i* bit konumunda depolar.|
|*x*[*i*] = *y*[*j*]|Bit *y*[ *j*] değerini bitset *x* *içinde bit* konumu olarak depolar.|
|*b* = ~ *x*[*i*]|Bit *x*[ *i*] ile çevrilmiş değeri **`bool`** *b*içinde depolar.|
|*b*  =  *x*[*i*]|Bit *x*[ *i*] değerini **`bool`** *b*içinde depolar.|
|*x*[*i*]. `flip`( )|Bit *x*[ *i*] ile çevrilmiş değeri *x*' *i* bit konumu olarak saklar.|

#### <a name="example"></a>Örnek

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

### <a name="reset"></a><a name="reset"></a>döndürmek

Bit kümesindeki tüm bitleri 0 olarak sıfırlar veya belirtilen konumdaki bir biti 0 olarak sıfırlar.

```cpp
bitset\<N>& reset();
bitset\<N>& reset(size_t _Pos);
```

#### <a name="parameters"></a>Parametreler

*_Pos*\
Bit kümesindeki bitin 0 olarak sıfırlanma konumu.

#### <a name="return-value"></a>Dönüş Değeri

Üye işlevin çağrıldığı bitset 'in bir kopyası.

#### <a name="remarks"></a>Açıklamalar

Belirtilen konum bitset boyutundan büyükse ikinci üye işlevi [out_of_range](../standard-library/out-of-range-class.md) bir özel durum oluşturur.

#### <a name="example"></a>Örnek

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

### <a name="set"></a><a name="set"></a>kurmak

Bit kümesindeki tüm bitleri 1 olarak ayarlar veya belirtilen konumdaki bit ' i 1 olarak ayarlar.

```cpp
bitset\<N>& set();

bitset\<N>& set(
    size_t _Pos,
    bool val = true);
```

#### <a name="parameters"></a>Parametreler

*_Pos*\
Bit kümesindeki bitin bir değere atanacak şekilde ayarlanabileceği konumu.

*Acil*\
Belirtilen konumda bite atanacak değer.

#### <a name="return-value"></a>Dönüş Değeri

Üye işlevin çağrıldığı bitset 'in bir kopyası.

#### <a name="remarks"></a>Açıklamalar

Belirtilen konum bitset boyutundan büyükse ikinci üye işlevi [out_of_range](../standard-library/out-of-range-class.md) bir özel durum oluşturur.

#### <a name="example"></a>Örnek

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

### <a name="size"></a><a name="size"></a>boyutla

Bitset nesnesindeki bit sayısını döndürür.

```cpp
size_t size() const;
```

#### <a name="return-value"></a>Dönüş Değeri

Bitset içindeki bit, *N*sayısı \<N> .

#### <a name="example"></a>Örnek

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

### <a name="test"></a><a name="test"></a>sınamanız

Bit kümesinde belirtilen konumdaki bitin 1 olarak ayarlanmış olup olmadığını sınar.

```cpp
bool test(size_t _Pos) const;
```

#### <a name="parameters"></a>Parametreler

*_Pos*\
Bit kümesindeki bitin değeri için test edilecek konumu.

#### <a name="return-value"></a>Dönüş Değeri

**`true`** bağımsız değişken konumuyla belirtilen bit 1 olarak ayarlanırsa Aksi takdirde, **`false`** .

#### <a name="remarks"></a>Açıklamalar

Üye işlevi bir [out_of_range](../standard-library/out-of-range-class.md) oluşturur

### <a name="to_string"></a><a name="to_string"></a>to_string

Bit kümesi nesnesini dize gösterimine dönüştürür.

```cpp
template <class charT = char, class traits = char_traits<charT>, class Allocator = allocator<charT> >
   basic_string<charT, traits, Allocator> to_string(charT zero = charT('0'), charT one = charT('1')) const;
```

#### <a name="return-value"></a>Döndürülen değer

`basic_string`Bit kümesindeki her bir bit kümesinde karşılık gelen 1 karakteri ve bit ayarlanmamışsa 0 karakteri bulunan sınıfının dize nesnesi.

#### <a name="example"></a>Örnek

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

### <a name="to_ullong"></a><a name="to_ullong"></a>to_ullong

**`unsigned long long`** Bitset nesnesinin içeriğiyle aynı bit kümesini içeren bir değer döndürür.

```cpp
unsigned long long to_ullong() const;
```

#### <a name="return-value"></a>Döndürülen değer

Bit dizisindeki bit değerlerinin toplamını olarak döndürür **`unsigned long long`** . Bu **`unsigned long long`** değer, bir bit kümesini başlatmak için kullanılıyorsa aynı küme bitlerini yeniden oluşturur.

#### <a name="exceptions"></a>Özel durumlar

Bit dizisindeki herhangi bir bit, türünde bir değer olarak temsil edilemeyecek bit değeri içeriyorsa, bir [overflow_error](overflow-error-class.md) nesnesi oluşturur **`unsigned long long`** .

#### <a name="remarks"></a>Açıklamalar

Bit dizisindeki bit değerlerinin toplamını olarak döndürür **`unsigned long long`** .

### <a name="to_ulong"></a><a name="to_ulong"></a>to_ulong

Bit kümesini başlatmak için kullanılmışsa, bir bitset nesnesini, içerilen bit dizisini üreten tamsayıya dönüştürür.

```cpp
unsigned long to_ulong( ) const;
```

#### <a name="return-value"></a>Döndürülen değer

Bitset 'in başlatılmasında kullanılan bir bit kümesinde bitleri üreten bir tamsayı.

#### <a name="remarks"></a>Açıklamalar

Üye işlevi uygulandığında, bit kümesinde bulunan bit dizisinde bulunan 1 ve 0 basamaklı aynı diziye sahip tamsayı döndürülür.

Bit dizisindeki herhangi bir bit, türünde bir değer olarak temsil edilemeyecek bit değeri içeriyorsa, üye işlevi bir [overflow_error](overflow-error-class.md) nesnesi oluşturur **`unsigned long`** .

#### <a name="example"></a>Örnek

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
