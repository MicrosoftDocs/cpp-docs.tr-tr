---
title: basic_ios Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ios/std::basic_ios
- ios/std::basic_ios::char_type
- ios/std::basic_ios::int_type
- ios/std::basic_ios::off_type
- ios/std::basic_ios::pos_type
- ios/std::basic_ios::traits_type
- ios/std::basic_ios::bad
- ios/std::basic_ios::clear
- ios/std::basic_ios::copyfmt
- ios/std::basic_ios::eof
- ios/std::basic_ios::exceptions
- ios/std::basic_ios::fail
- ios/std::basic_ios::fill
- ios/std::basic_ios::good
- ios/std::basic_ios::imbue
- ios/std::basic_ios::init
- ios/std::basic_ios::move
- ios/std::basic_ios::narrow
- ios/std::basic_ios::rdbuf
- ios/std::basic_ios::rdstate
- ios/std::basic_ios::set_rdbuf
- ios/std::basic_ios::setstate
- ios/std::basic_ios::swap
- ios/std::basic_ios::tie
- ios/std::basic_ios::widen
- ios/std::basic_ios::explicit operator bool
helpviewer_keywords:
- std::basic_ios [C++]
- std::basic_ios [C++], char_type
- std::basic_ios [C++], int_type
- std::basic_ios [C++], off_type
- std::basic_ios [C++], pos_type
- std::basic_ios [C++], traits_type
- std::basic_ios [C++], bad
- std::basic_ios [C++], clear
- std::basic_ios [C++], copyfmt
- std::basic_ios [C++], eof
- std::basic_ios [C++], exceptions
- std::basic_ios [C++], fail
- std::basic_ios [C++], fill
- std::basic_ios [C++], good
- std::basic_ios [C++], imbue
- std::basic_ios [C++], init
- std::basic_ios [C++], move
- std::basic_ios [C++], narrow
- std::basic_ios [C++], rdbuf
- std::basic_ios [C++], rdstate
- std::basic_ios [C++], set_rdbuf
- std::basic_ios [C++], setstate
- std::basic_ios [C++], swap
- std::basic_ios [C++], tie
- std::basic_ios [C++], widen
ms.assetid: 4fdcd8e1-62d2-4611-8a70-1e4f58434007
ms.openlocfilehash: b730933879df04d2455b5eae6fc5abf16bbf4484
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219280"
---
# <a name="basic_ios-class"></a>basic_ios Sınıfı

Sınıf şablonu, şablon parametrelerine bağlı olan giriş akışları (sınıf şablonu [basic_istream](../standard-library/basic-istream-class.md)) ve çıkış akışları (sınıf şablonu [basic_ostream](../standard-library/basic-ostream-class.md)) için ortak depolama ve üye işlevlerini açıklar. (Sınıf [ios_base](../standard-library/ios-base-class.md) , ortak olduğunu ve şablon parametrelerine bağlı olanları açıklar.) ** \<class Elem, class Traits> Basic_ios** sınıfının bir nesnesi `Elem` , karakter nitelikleri sınıf tarafından belirlenen türdeki öğelerle bir akışı denetlemeye yardımcı olur `Traits` .

## <a name="syntax"></a>Söz dizimi

```cpp

template <class Elem, class Traits>
class basic_ios : public ios_base
```

### <a name="parameters"></a>Parametreler

*Elem*\
Bir tür.

*Lerdir*\
Türünde bir değişken `char_traits` .

## <a name="remarks"></a>Açıklamalar

**Basic_ios \<class Elem, class Traits> ** depolayan bir nesne:

- [Basic_istream](../standard-library/basic-istream-class.md)türünde bir nesne için bağlama işaretçisi **\<Elem, Traits>** .

- [Basic_streambuf](../standard-library/basic-streambuf-class.md)türünde bir nesneye akış arabelleği işaretçisi **\<Elem, Traits >** .

- [Biçimlendirme bilgileri](../standard-library/ios-base-class.md).

- [İos_base](../standard-library/ios-base-class.md)türünde bir temel nesne içindeki [akış durumu bilgisi](../standard-library/ios-base-class.md) .

- Türünde bir nesnedeki bir Fill karakteri `char_type` .

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_ios](#basic_ios)|Sınıfını oluşturur `basic_ios` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Şablon parametresi için bir eş anlamlı `Elem` .|
|[int_type](#int_type)|İçin bir eş anlamlı `Traits::int_type` .|
|[off_type](#off_type)|İçin bir eş anlamlı `Traits::off_type` .|
|[pos_type](#pos_type)|İçin bir eş anlamlı `Traits::pos_type` .|
|[traits_type](#traits_type)|Şablon parametresi için bir eş anlamlı `Traits` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Hatalı](#bad)|Akış arabelleğinin bütünlüğünden oluşan bir kayıp olduğunu gösterir.|
|[lediğiniz](#clear)|Tüm hata bayraklarını temizler.|
|[copyfmt](#copyfmt)|Bayrakları bir akıştan diğerine kopyalar.|
|[EOF](#eof)|Akışın sonuna ulaşıldığını gösterir.|
|[larý](#exceptions)|Akış tarafından hangi özel durumların atılamayacağını belirtir.|
|[Neden](#fail)|Akıştan geçerli bir alan ayıklama hatası olduğunu gösterir.|
|[doldurması](#fill)|Metin akış kadar genişse kullanılacak karakteri belirtir veya döndürür.|
|[iyi](#good)|Akışın iyi koşullarda olduğunu gösterir.|
|[imbue](#imbue)|Yerel ayarı değiştirir.|
|[init](#init)|Oluşturucular tarafından çağırılır `basic_ios` .|
|[geçiş](#move)|Stream buffer işaretçisi dışındaki tüm değerleri, parametresinden geçerli nesneye taşıtır.|
|[narrow](#narrow)|Verilen karakterin eşdeğerini bulur `char_type` .|
|[rdbuf](#rdbuf)|Akışı belirtilen arabelleğe yönlendirir.|
|[rdstate](#rdstate)|Bayrakların bitlerin durumunu okur.|
|[set_rdbuf](#set_rdbuf)|Bu akış nesnesi için okuma arabelleği olacak bir akış arabelleği atar.|
|[setstate](#setstate)|Ek bayrakları ayarlar.|
|[Kur](#swap)|Bu `basic_ios` nesnedeki değerleri başka bir nesne için değiş tokuş eder `basic_ios` . Akış arabelleklerine yönelik işaretçiler takas edilmez.|
|[formlarınızı](#tie)|Bir akışın başka bir akıştan önce işlenmesini sağlar.|
|[Genişlet](#widen)|`char_type`Verilen bir Char 'ın eşdeğerini bulur.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[Açık işleç bool](#op_bool)|Nesnesinin olarak kullanılmasına izin verir `basic_ios` **`bool`** . Ortak, istenmeyen yan etkileri engellemek için otomatik tür dönüştürmesi devre dışıdır.|
|[void * işleci](#op_void_star)|Akışın hala iyi olup olmadığını gösterir.|
|[işlecinde!](#op_not)|Akışın bozuk olup olmadığını gösterir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<ios>

**Ad alanı:** std

## <a name="basic_iosbad"></a><a name="bad"></a>basic_ios:: Bad

Akış arabelleğinin bütünlüğünden oluşan bir kayıp olduğunu belirtir

```cpp
bool bad() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`**`rdstate & badbit`sıfır değilse, tersi durumda **`false`** .

Hakkında daha fazla bilgi için `badbit` bkz. [ios_base:: ıostate](../standard-library/ios-base-class.md#iostate).

### <a name="example"></a>Örnek

```cpp
// basic_ios_bad.cpp
// compile with: /EHsc
#include <iostream>

int main( void )
{
    using namespace std;
    bool b = cout.bad( );
    cout << boolalpha;
    cout << b << endl;

    b = cout.good( );
    cout << b << endl;
}
```

## <a name="basic_iosbasic_ios"></a><a name="basic_ios"></a>basic_ios:: basic_ios

Basic_ios sınıfını oluşturur.

```cpp
explicit basic_ios(basic_streambuf<Elem,  Traits>* sb);
basic_ios();
```

### <a name="parameters"></a>Parametreler

*ise*\
Giriş veya çıkış öğelerini depolamak için standart arabellek.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, [init](#init)(_ *SB*) çağırarak üye nesnelerini başlatır. İkinci (protected) Oluşturucu, üye nesnelerini başlatılmamış halde bırakır. Daha sonraki bir çağrısının `init` , güvenli bir şekilde yok edilebilmesi için nesneyi başlatması gerekir.

## <a name="basic_ioschar_type"></a><a name="char_type"></a>basic_ios:: char_type

Şablon parametresi için bir eş anlamlı `Elem` .

```cpp
typedef Elem char_type;
```

## <a name="basic_iosclear"></a><a name="clear"></a>basic_ios:: Clear

Tüm hata bayraklarını temizler.

```cpp
void clear(iostate state = goodbit, bool reraise = false);
void clear(io_state state);
```

### <a name="parameters"></a>Parametreler

*durumunda*\
Seçim Tüm bayrakları temizledikten sonra ayarlamak istediğiniz bayraklar. Varsayılan olarak olur `goodbit` .

*reraise*\
Seçim Özel durumun yeniden oluşturulup oluşturulmayacağını belirtir. Varsayılan olarak olarak **`false`** değişir (özel durumu yeniden oluşturmaz).

### <a name="remarks"></a>Açıklamalar

Bayrakları,, `goodbit` `failbit` `eofbit` ve `badbit` . Bu bayrakları [iyi](#good), [bozuk](#bad), [EOF](#eof)ve [başarısız](#fail) ile test edin

Üye işlevi, depolanan akış durumu bilgisini ile değiştirir:

`state`&#124; `(` [rdarabelleğe](#rdbuf) ! = 0 **goodbit** : **badbit**)

`state` **&** [Özel durumlar](#exceptions) sıfır değilse, bir sınıf [hatası](../standard-library/ios-base-class.md#failure)nesnesi oluşturur.

### <a name="example"></a>Örnek

Using örnekleri için bkz. [rdstate](#rdstate) ve [getline](../standard-library/string-functions.md#getline) `clear` .

## <a name="basic_ioscopyfmt"></a><a name="copyfmt"></a>basic_ios:: copyfmt

Bayrakları bir akıştan diğerine kopyalar.

```cpp
basic_ios<Elem, Traits>& copyfmt(
const basic_ios<Elem, Traits>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bayraklarını kopyalamak istediğiniz akış.

### <a name="return-value"></a>Dönüş Değeri

**`this`** Bayrakları kopyaladığınız akışın nesnesi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi geri çağırma olayı **silme \_ olayını**raporlar. Daha sonra bu, *doğrudan* ** \* Bu** Fill karakterine, bağlama işaretçisine ve biçimlendirme bilgilerine kopyalar. Özel durum maskesini değiştirmeden önce geri çağırma olayını raporlar `copyfmt_event` . Kopyalama işlemi tamamlandıktan sonra, **durum &** [özel durumları](#exceptions) sıfır dışında olduğunda, işlev [rdstate](#rdstate)bağımsız değişkeniyle [clear](#clear) öğesini etkin bir şekilde çağırır. ** \* Bunu döndürür.**

### <a name="example"></a>Örnek

```cpp
// basic_ios_copyfmt.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
    using namespace std;
    ofstream x( "test.txt" );
    int i = 10;

    x << showpos;
    cout << i << endl;
    cout.copyfmt( x );
    cout << i << endl;
}
```

## <a name="basic_ioseof"></a><a name="eof"></a>basic_ios:: EOF

Akışın sonuna ulaşıldığını gösterir.

```cpp
bool eof() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** akışın sonuna ulaşılırsa, **`false`** tersi durumda.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, **`true`** [rdstate](#rdstate) `& eofbit` sıfırdan farklı olursa döndürür. Hakkında daha fazla bilgi için `eofbit` bkz. [ios_base:: ıostate](../standard-library/ios-base-class.md#iostate).

### <a name="example"></a>Örnek

```cpp
// basic_ios_eof.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

using namespace std;

int main( int argc, char* argv[] )
{
    fstream   fs;
    int n = 1;
    fs.open( "basic_ios_eof.txt" );   // an empty file
    cout << boolalpha
    cout << fs.eof() << endl;
    fs >> n;   // Read the char in the file
    cout << fs.eof() << endl;
}
```

## <a name="basic_iosexceptions"></a><a name="exceptions"></a>basic_ios:: Exceptions

Akış tarafından hangi özel durumların atılamayacağını belirtir.

```cpp
iostate exceptions() const;
void exceptions(iostate Newexcept);
void exceptions(io_state Newexcept);
```

### <a name="parameters"></a>Parametreler

*Newexcept*\
Özel durum oluşturmak istediğiniz bayraklar.

### <a name="return-value"></a>Dönüş Değeri

Şu anda akış için bir özel durum oluşturdu için belirtilen bayraklar.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, saklı özel durum maskesini döndürür. İkinci üye işlevi, özel durum maskesinde *_Except* depolar ve önceki depolanmış değerini döndürür. Yeni bir özel durum maskesinin depolanması, çağrı [Temizleme](#clear)( [rdstate](#rdstate) ) gibi bir özel durum oluşturabilir.

### <a name="example"></a>Örnek

```cpp
// basic_ios_exceptions.cpp
// compile with: /EHsc /GR
#include <iostream>

int main( )
{
    using namespace std;

    cout << cout.exceptions( ) << endl;
    cout.exceptions( ios::eofbit );
    cout << cout.exceptions( ) << endl;
    try
    {
        cout.clear( ios::eofbit );   // Force eofbit on
    }
    catch ( exception &e )
    {
        cout.clear( );
        cout << "Caught the exception." << endl;
        cout << "Exception class: " << typeid(e).name()  << endl;
        cout << "Exception description: " << e.what() << endl;
    }
}
```

```Output
0
1
Caught the exception.
Exception class: class std::ios_base::failure
Exception description: ios_base::eofbit set
```

## <a name="basic_iosfail"></a><a name="fail"></a>basic_ios:: Fail

Akıştan geçerli bir alan ayıklama hatası olduğunu gösterir.

```cpp
bool fail() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`**[rdstate](#rdstate) `& (badbit|failbit)` sıfır değilse, tersi durumda **`false`** .

Hakkında daha fazla bilgi için `failbit` bkz. [ios_base:: ıostate](../standard-library/ios-base-class.md#iostate).

### <a name="example"></a>Örnek

```cpp
// basic_ios_fail.cpp
// compile with: /EHsc
#include <iostream>

int main( void )
{
    using namespace std;
    bool b = cout.fail( );
    cout << boolalpha;
    cout << b << endl;
}
```

## <a name="basic_iosfill"></a><a name="fill"></a>basic_ios:: Fill

Metin akış kadar genişse kullanılacak karakteri belirtir veya döndürür.

```cpp
char_type fill() const;
char_type fill(char_type Char);
```

### <a name="parameters"></a>Parametreler

*Char*\
İstediğiniz karakter, Fill karakteri olarak.

### <a name="return-value"></a>Dönüş Değeri

Geçerli Fill karakteri.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi depolanan Fill karakterini döndürür. İkinci üye işlevi, *char* karakterini Fill karakteriyle depolar ve önceki depolanmış değerini döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_ios_fill.cpp
// compile with: /EHsc
#include <iostream>
#include <iomanip>

int main( )
{
    using namespace std;

    cout << setw( 5 ) << 'a' << endl;
    cout.fill( 'x' );
    cout << setw( 5 ) << 'a' << endl;
    cout << cout.fill( ) << endl;
}
```

```Output
a
xxxxa
x
```

## <a name="basic_iosgood"></a><a name="good"></a>basic_ios:: iyi

Akışın iyi koşullarda olduğunu gösterir.

```cpp
bool good() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`**[rdstate](#rdstate) `== goodbit` (hiçbir durum bayrağı ayarlanmamışsa), aksi takdirde, **`false`** .

Hakkında daha fazla bilgi için `goodbit` bkz. [ios_base:: ıostate](../standard-library/ios-base-class.md#iostate).

### <a name="example"></a>Örnek

Bkz. [basic_ios::](#bad) using bir örnek için `good` .

## <a name="basic_iosimbue"></a><a name="imbue"></a>basic_ios:: imbue

Yerel ayarı değiştirir.

```cpp
locale imbue(const locale& Loc);
```

### <a name="parameters"></a>Parametreler

*Çerçeve*\
Yerel ayar dizesi.

### <a name="return-value"></a>Dönüş Değeri

Önceki yerel ayar.

### <a name="remarks"></a>Açıklamalar

[Rdarabelleğe](#rdbuf) bir null işaretçi değilse, üye işlevi çağırır

`rdbuf`-> [pubimbue](../standard-library/basic-streambuf-class.md#pubimbue)(_ *loc*)

Herhangi bir durumda [ios_base:: imbue](../standard-library/ios-base-class.md#imbue)(_ *loc*) döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_ios_imbue.cpp
// compile with: /EHsc
#include <iostream>
#include <locale>

int main( )
{
    using namespace std;

    cout.imbue( locale( "french_france" ) );
    double x = 1234567.123456;
    cout << x << endl;
}
```

## <a name="basic_iosinit"></a><a name="init"></a>basic_ios:: init

Basic_ios oluşturucular tarafından çağırılır.

```cpp
void init(basic_streambuf<Elem,Traits>* _Sb, bool _Isstd = false);
```

### <a name="parameters"></a>Parametreler

*_Sb*\
Giriş veya çıkış öğelerini depolamak için standart arabellek.

*_Isstd*\
Bunun standart bir akış olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, değerleri tüm üye nesnelerinde depolar, böylece:

- [rdarabelleğe](#rdbuf) *_Sb döndürüyor.*

- bağlama, null bir [işaretçi döndürüyor.](#tie)

- [rdstate](#rdstate) , *_Sb* sıfır değilse, [goodbit](../standard-library/ios-base-class.md#iostate) döndürür; Aksi halde, [badbit](../standard-library/ios-base-class.md#iostate)döndürür.

- [özel durumlar](#exceptions) döndürülür `goodbit` .

- [bayraklar](../standard-library/ios-base-class.md#flags) [skipws](../standard-library/ios-base-class.md#fmtflags) &#124; [Ara](../standard-library/ios-base-class.md#fmtflags)döndürür.

- [Genişlik](../standard-library/ios-base-class.md#width) 0 döndürür.

- [duyarlık](../standard-library/ios-base-class.md#precision) 6 döndürür.

- [Fill](#fill) boşluk karakterini döndürür.

- [getloc](../standard-library/ios-base-class.md#getloc) döndürüyor `locale::classic` .

- [ıword](../standard-library/ios-base-class.md#iword) sıfır döndürüyor ve [pword](../standard-library/ios-base-class.md#pword) tüm bağımsız değişken değerleri için bir null işaretçi döndürüyor.

## <a name="basic_iosint_type"></a><a name="int_type"></a>basic_ios:: int_type

İçin bir eş anlamlı `traits_type::int_type` .

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="basic_iosmove"></a><a name="move"></a>basic_ios:: Move

Stream buffer işaretçisi dışındaki tüm değerleri, parametresinden geçerli nesneye taşıtır.

```cpp
void move(basic_ios&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`ios_base`Değerlerin taşınacağı nesne.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi, sağda depolanan tüm değerleri, *right* **`*this`** `stream buffer pointer` *sağ* tarafta değişmeyen ve içinde null bir işaretçiye ayarlanmış olan ' a doğru olarak kaydırır **`*this`** . Depolanan, `tie pointer` *sağ tarafta*null bir işaretçiye ayarlanır.

## <a name="basic_iosnarrow"></a><a name="narrow"></a>basic_ios:: dar

Verilen karakterin eşdeğerini bulur `char_type` .

```cpp
char narrow(char_type Char, char Default = '\0') const;
```

### <a name="parameters"></a>Parametreler

*Char*\
**`char`** Dönüştürülecek.

*Varsayılanını*\
Eşdeğer değilse, **`char`** döndürülmesini istediğiniz.

### <a name="return-value"></a>Dönüş Değeri

**`char`** Verilen değerine eşdeğerdir `char_type` .

### <a name="remarks"></a>Açıklamalar

Üye işlevi [use_facet](../standard-library/basic-filebuf-class.md#open) \<ctype\<E> > döndürür ( [getloc](../standard-library/ios-base-class.md#getloc)()). `narrow` ( `Char`, `Default`).

### <a name="example"></a>Örnek

```cpp
// basic_ios_narrow.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <wchar.h>

int main( )
{
    using namespace std;
    wchar_t *x = L"test";
    char y[10];
    cout << x[0] << endl;
    wcout << x << endl;
    y[0] = wcout.narrow( x[0] );
    cout << y[0] << endl;
}
```

## <a name="basic_iosoff_type"></a><a name="off_type"></a>basic_ios:: off_type

İçin bir eş anlamlı `traits_type::off_type` .

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="basic_iosoperator-void-"></a><a name="op_void_star"></a>basic_ios:: operator void *

Akışın hala iyi olup olmadığını gösterir.

```cpp
operator void *() const;
```

### <a name="return-value"></a>Dönüş Değeri

İşleci yalnızca [başarısız](#fail)olursa, null bir işaretçi döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_ios_opgood.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    cout << (bool)(&cout != 0) << endl;   // Stream is still good
}
```

```Output
1
```

## <a name="basic_iosoperator"></a><a name="op_not"></a>basic_ios:: operator!

Akışın bozuk olup olmadığını gösterir.

```cpp
bool operator!() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Başarısız](#fail)sonucunu döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_ios_opbad.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    cout << !cout << endl;   // Stream is not bad
}
```

```Output
0
```

## <a name="basic_iosoperator-bool"></a><a name="op_bool"></a>basic_ios:: operator bool

Nesnesinin olarak kullanılmasına izin verir `basic_ios` **`bool`** . Ortak, istenmeyen yan etkileri engellemek için otomatik tür dönüştürmesi devre dışıdır.

```cpp
explicit operator bool() const;
```

### <a name="remarks"></a>Açıklamalar

İşleci yalnızca öğesine dönüştürülebilir bir değer döndürür **`false`** `fail()` . Dönüş türü, türüne **`bool`** değil, türüne `void *` veya başka bilinen skalar türe dönüştürülebilir.

## <a name="basic_iospos_type"></a><a name="pos_type"></a>basic_ios::p os_type

İçin bir eş anlamlı `traits_type::pos_type` .

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="basic_iosrdbuf"></a><a name="rdbuf"></a>basic_ios:: rdarabelleğe

Akışı belirtilen arabelleğe yönlendirir.

```cpp
basic_streambuf<Elem, Traits> *rdbuf() const;
basic_streambuf<Elem, Traits> *rdbuf(
basic_streambuf<Elem, Traits>* _Sb);
```

### <a name="parameters"></a>Parametreler

*_Sb*\
Bir akış.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi depolanan akış arabelleği işaretçisini döndürür.

İkinci üye işlevi depolanan akış arabelleği işaretçisine *_Sb* depolar ve daha önce depolanan değeri döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_ios_rdbuf.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <fstream>

int main( )
{
    using namespace std;
    ofstream file( "rdbuf.txt" );
    streambuf *x = cout.rdbuf( file.rdbuf( ) );
    cout << "test" << endl;   // Goes to file
    cout.rdbuf(x);
    cout << "test2" << endl;
}
```

```Output
test2
```

## <a name="basic_iosrdstate"></a><a name="rdstate"></a>basic_ios:: rdstate

Bayrakların bitlerin durumunu okur.

```cpp
iostate rdstate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan akış durumu bilgileri.

### <a name="example"></a>Örnek

```cpp
// basic_ios_rdstate.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>
using namespace std;

void TestFlags( ios& x )
{
    cout << ( x.rdstate( ) & ios::badbit ) << endl;
    cout << ( x.rdstate( ) & ios::failbit ) << endl;
    cout << ( x.rdstate( ) & ios::eofbit ) << endl;
    cout << endl;
}

int main( )
{
    fstream x( "c:\test.txt", ios::out );
    x.clear( );
    TestFlags( x );
    x.clear( ios::badbit | ios::failbit | ios::eofbit );
    TestFlags( x );
}
```

```Output
0
0
0

4
2
1
```

## <a name="basic_iossetstate"></a><a name="setstate"></a>basic_ios:: setstate

Ek bayrakları ayarlar.

```cpp
void setstate(iostate _State);
```

### <a name="parameters"></a>Parametreler

*_State*\
Ayarlanacak ek bayraklar.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, [clear](#clear)(_ *State* &#124; [rdstate](#rdstate)) öğesini etkin bir şekilde çağırır.

### <a name="example"></a>Örnek

```cpp
// basic_ios_setstate.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
using namespace std;

int main( )
{
    bool b = cout.bad( );
    cout << b << endl;   // Good
    cout.clear( ios::badbit );
    b = cout.bad( );
    // cout.clear( );
    cout << b << endl;   // Is bad, good
    b = cout.fail( );
    cout << b << endl;   // Not failed
    cout.setstate( ios::failbit );
    b = cout.fail( );
    cout.clear( );
    cout << b << endl;   // Is failed, good
    return 0;
}
```

```Output
0
1
```

## <a name="basic_iosset_rdbuf"></a><a name="set_rdbuf"></a>basic_ios:: set_rdbuf

Bu akış nesnesi için okuma arabelleği olacak bir akış arabelleği atar.

```cpp
void set_rdbuf(
basic_streambuf<Elem, Tr>* strbuf)
```

### <a name="parameters"></a>Parametreler

*strarabelleğe*\
Okuma arabelleği olacak akış arabelleği.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi içinde *strarabelleğe* depolar `stream buffer pointer` . Çağrı yapmaz `clear` .

## <a name="basic_iostie"></a><a name="tie"></a>basic_ios:: kravat

Bir akışın başka bir akıştan önce işlenmesini sağlar.

```cpp
basic_ostream<Elem, Traits> *tie() const;
basic_ostream<Elem, Traits> *tie(
basic_ostream<Elem, Traits>* str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
Bir akış.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi, depolanan bağlama işaretçisini döndürür. İkinci üye işlevi, *Str* 'yi bağlama işaretçisine depolar ve önceki depolanmış değerini döndürür.

### <a name="remarks"></a>Açıklamalar

`tie`, bir akışla ilgili işlemler diğer akıştaki işlemler tamamlandıktan sonra meydana gelen iki akışın eşitlenmesine neden olur.

### <a name="example"></a>Örnek

Bu örnekte, cin ile cout arasında geçiş yaparak, "bir sayı girin:" dizesinin, sayının kendisi cin öğesinden ayıklanmadan konsola gidecektir. Bu, "bir sayı gir:" dizesinin arabellekte hala oturmakta olduğunu ortadan kaldırır, böylece kullanıcının yanıt vermesi için gerçekten bir istem olduğundan emin olur. Varsayılan olarak, cin ve cout bağlıdır.

```cpp
#include <ios>
#include <iostream>

int main( )
{
    using namespace std;
    int i;
    cin.tie( &cout );
    cout << "Enter a number:";
    cin >> i;
}
```

## <a name="basic_iostraits_type"></a><a name="traits_type"></a>basic_ios:: traits_type

Şablon parametresi için bir eş anlamlı `Traits` .

```cpp
typedef Traits traits_type;
```

## <a name="basic_ioswiden"></a><a name="widen"></a>basic_ios:: Genişlet

`char_type`Verilen öğesine denk bulur **`char`** .

```cpp
char_type widen(char Char) const;
```

### <a name="parameters"></a>Parametreler

*Char*\
Dönüştürülecek karakter.

### <a name="return-value"></a>Dönüş Değeri

`char_type`Verilen öğesine denk bulur **`char`** .

### <a name="remarks"></a>Açıklamalar

Üye işlevi [use_facet](../standard-library/basic-filebuf-class.md#open) <  **CType** \< **E**> > ( [getloc](../standard-library/ios-base-class.md#getloc)) döndürüyor. `widen`( `Char`).

### <a name="example"></a>Örnek

```cpp
// basic_ios_widen.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <wchar.h>

int main( )
{
    using namespace std;
    char *z = "Hello";
    wchar_t y[2] = {0,0};
    cout << z[0] << endl;
    y[0] = wcout.widen( z[0] );
    wcout << &y[0] << endl;
}
```

## <a name="basic_iosswap"></a><a name="swap"></a>basic_ios:: swap

Bu `basic_ios` nesnedeki değerleri başka bir nesne için değiş tokuş eder `basic_ios` . Ancak, akış arabelleklerine yönelik işaretçiler takas edilmez.

```cpp
void swap(basic_ios&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`basic_ios`Değer değişimi için kullanılan nesne.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi, depolanan her türlü değeri, *right* **`*this`** depolandıkları hariç tüm değerleri değiştirir `stream buffer pointer` .

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
