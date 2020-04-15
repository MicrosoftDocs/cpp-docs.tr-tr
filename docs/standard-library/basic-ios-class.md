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
ms.openlocfilehash: c8f883dd4f946c03aaa22dffcf5a3164a539d041
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364918"
---
# <a name="basic_ios-class"></a>basic_ios Sınıfı

Sınıf şablonu, hem giriş akışlarında (sınıf şablonu [basic_istream)](../standard-library/basic-istream-class.md)hem de şablon parametrelerine bağlı çıktı akışları (sınıf şablonu [basic_ostream)](../standard-library/basic-ostream-class.md)için ortak olan depolama ve üye işlevleri açıklar. (Sınıf [ios_base](../standard-library/ios-base-class.md) ortak ve şablon parametrelerine bağlı olmayan açıklar.) **Sınıf basic_ios\<sınıf Elem, sınıf Özellikleri>** bir nesne olan karakter özellikleri sınıf `Elem` `Traits`tarafından belirlenir türü öğeleri ile bir akışı kontrol yardımcı olur.

## <a name="syntax"></a>Sözdizimi

```cpp

template <class Elem, class Traits>
class basic_ios : public ios_base
```

### <a name="parameters"></a>Parametreler

*Elem*\
Bir tür.

*Özellik*\
Bir tür `char_traits`değişkeni.

## <a name="remarks"></a>Açıklamalar

**Sınıf basic_ios\<sınıf Elem, sınıf Özellikleri>** depoları bir nesne:

- Elem, Özellikler>basic_istream [türü](../standard-library/basic-istream-class.md)bir nesneye bir kravat işaretçisi .**\< **

- Elem, Özellikler >basic_streambuf [türübir](../standard-library/basic-streambuf-class.md)nesneye bir akış arabellek işaretçisi .**\< **

- [Bilgileri biçimlendirme.](../standard-library/ios-base-class.md)

- Tür [ios_base](../standard-library/ios-base-class.md)temel nesnesindeki [durum bilgilerini akışı.](../standard-library/ios-base-class.md)

- Türdeki `char_type`bir nesnedeki dolgu karakteri.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Basic_ios](#basic_ios)|`basic_ios` Sınıfı kurar.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|Şablon parametresi `Elem`için eşanlamlı.|
|[Int_type](#int_type)|Bir eşanlamlı `Traits::int_type`.|
|[off_type](#off_type)|Bir eşanlamlı `Traits::off_type`.|
|[pos_type](#pos_type)|Bir eşanlamlı `Traits::pos_type`.|
|[traits_type](#traits_type)|Şablon parametresi `Traits`için eşanlamlı.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Kötü](#bad)|Akış arabelleği bütünlüğünün kaybolduğunu gösterir.|
|[Temizleyin](#clear)|Tüm hata bayraklarını temizler.|
|[copyfmt](#copyfmt)|Bayrakları bir akıştan diğerine kopyalar.|
|[eof](#eof)|Bir akışın sonuna ulaşılıp ulaşıldığını gösterir.|
|[Özel durum](#exceptions)|Akış tarafından hangi özel durumların atılacağını gösterir.|
|[Başarısız](#fail)|Bir akıştan geçerli bir alanın ayıklanmasının başarısız olduğunu gösterir.|
|[fill](#fill)|Metin akış kadar geniş olmadığında kullanılacak karakteri belirtir veya döndürür.|
|[Iyi](#good)|Akışın iyi durumda olduğunu gösterir.|
|[imbue](#imbue)|Yerel alanı değiştirir.|
|[init](#init)|Yapıcılar `basic_ios` tarafından çağrıldı.|
|[Hareket](#move)|İşaretçi dışındaki tüm değerleri, parametreden geçerli nesneye akış arabelleğini taşır.|
|[Dar](#narrow)|Belirli `char_type`bir eşdeğer char bulur.|
|[Rdbuf](#rdbuf)|Yolları akışı belirtilen arabelleğe aktarın.|
|[rdstate](#rdstate)|Bayraklar için bit durumunu okur.|
|[set_rdbuf](#set_rdbuf)|Bu akış nesnesi için okuma arabelleği olması için bir akış arabelleği atar.|
|[setstate](#setstate)|Ek bayraklar ayarlar.|
|[Takas](#swap)|Bu `basic_ios` nesnedeki değerleri başka bir `basic_ios` nesnenin değerleriyle değiştirir. Akış arabelleklerine işaretçiler değiştirilmez.|
|[Kravat](#tie)|Bir akışın başka bir akışdan önce işlenmesini sağlar.|
|[Genişlet -mek](#widen)|Belirli bir `char_type` char eşdeğerini bulur.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[açık operatör bool](#op_bool)|Bir `basic_ios` nesnenin **bool**olarak kullanılmasını sağlar. Sık karşılaşılan istenmeyen yan etkileri önlemek için otomatik tür dönüştürme devre dışı bırakılır.|
|[operatör geçersiz *](#op_void_star)|Akışın hala iyi olup olmadığını gösterir.|
|[Işleç!](#op_not)|Akış kötü değilse gösterir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<ios>

**Ad alanı:** std

## <a name="basic_iosbad"></a><a name="bad"></a>basic_ios::kötü

Akış arabelleği bütünlüğünün kaybını gösterir

```cpp
bool bad() const;
```

### <a name="return-value"></a>Dönüş Değeri

`rdstate & badbit` sıfır değilse **doğru;** aksi takdirde **yanlış**.

Hakkında daha `badbit`fazla bilgi için, [ios_base bakın::iostate](../standard-library/ios-base-class.md#iostate).

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

## <a name="basic_iosbasic_ios"></a><a name="basic_ios"></a>basic_ios:basic_ios

basic_ios sınıfını kurar.

```cpp
explicit basic_ios(basic_streambuf<Elem,  Traits>* sb);
basic_ios();
```

### <a name="parameters"></a>Parametreler

*Sb*\
Giriş veya çıktı öğelerini depolamak için standart arabellek.

### <a name="remarks"></a>Açıklamalar

İlk kurucu, üye nesnelerini [init](#init)(_ *Sb)* çağırarak başharfe çözer. İkinci (korumalı) oluşturucu üye nesnelerini baş harfe getirilmemiş olarak bırakır. Daha sonra `init` bir çağrı güvenli bir şekilde yok edilebilmelidir önce nesnenin başlatılması gerekir.

## <a name="basic_ioschar_type"></a><a name="char_type"></a>basic_ios::char_type

Şablon parametresi `Elem`için eşanlamlı.

```cpp
typedef Elem char_type;
```

## <a name="basic_iosclear"></a><a name="clear"></a>basic_ios::açık

Tüm hata bayraklarını temizler.

```cpp
void clear(iostate state = goodbit, bool reraise = false);
void clear(io_state state);
```

### <a name="parameters"></a>Parametreler

*Durum*\
(İsteğe bağlı) Tüm bayrakları temizledikten sonra ayarlamak istediğiniz bayraklar. Varsayılan `goodbit`değer.

*yeniden yükseltmek*\
(İsteğe bağlı) Özel durum yeniden yükseltilmesi gerekip gerekmediğini belirtir. Varsayılan **false** (özel durumu yeniden yükseltmez).

### <a name="remarks"></a>Açıklamalar

Bayraklar `goodbit`, `failbit` `eofbit`, `badbit`, ve . [Test iyi](#good)ile bu bayraklar için , [kötü](#bad), [eof](#eof), ve [başarısız](#fail)

Üye işlev, depolanan akış durumu bilgilerinin yerine şu şekilde gelir:

`state`&#124; `(` [rdbuf](#rdbuf) != 0 **goodbit** : **badbit**)

Özel durumlar sıfır değilse, sınıf [hatası](../standard-library/ios-base-class.md#failure)nesnesi atar. [exceptions](#exceptions) `state` **&**

### <a name="example"></a>Örnek

Aşağıdakileri kullanarak `clear`örnekler için [rdstate](#rdstate) ve [getline](../standard-library/string-functions.md#getline) bakın.

## <a name="basic_ioscopyfmt"></a><a name="copyfmt"></a>basic_ios::copyfmt

Bayrakları bir akıştan diğerine kopyalar.

```cpp
basic_ios<Elem, Traits>& copyfmt(
const basic_ios<Elem, Traits>& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bayraklarını kopyalamak istediğiniz akış.

### <a name="return-value"></a>Dönüş Değeri

Bayrakları kopyaladığın akış için **bu** nesne.

### <a name="remarks"></a>Açıklamalar

Üye işlev, geri arama olayını **silme\_olayını**bildirir. Daha sonra ** \*bu** dolgu karakteri, kravat işaretçisi ve biçimlendirme bilgileri *içine sağdan* kopyalar. Özel durum maskesini değiştirmeden önce, `copyfmt_event`geri arama olayını bildirir. Kopya tamamlandıktan sonra durum **&** [özel durumlar](#exceptions) sıfır değilse, işlev etkin bir şekilde bağımsız değişken [rdstate](#rdstate)ile [açık](#clear) çağırır. ** \*Bunu**döndürür.

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

## <a name="basic_ioseof"></a><a name="eof"></a>basic_ios::eof

Bir akışın sonuna ulaşılıp ulaşıldığını gösterir.

```cpp
bool eof() const;
```

### <a name="return-value"></a>Dönüş Değeri

akışın sonuna ulaşıldıysa **doğru,** aksi takdirde **yanlış.**

### <a name="remarks"></a>Açıklamalar

[Rdstate](#rdstate) `& eofbit` sıfır değilse üye işlev **doğru** döndürür. Hakkında daha `eofbit`fazla bilgi için, [ios_base bakın::iostate](../standard-library/ios-base-class.md#iostate).

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

## <a name="basic_iosexceptions"></a><a name="exceptions"></a>basic_ios::özel durumlar

Akış tarafından hangi özel durumların atılacağını gösterir.

```cpp
iostate exceptions() const;
void exceptions(iostate Newexcept);
void exceptions(io_state Newexcept);
```

### <a name="parameters"></a>Parametreler

*Yeni Hariç*\
Bir özel durum atmak istediğiniz bayraklar.

### <a name="return-value"></a>Dönüş Değeri

Şu anda akış için bir özel durum atmak için belirtilen bayraklar.

### <a name="remarks"></a>Açıklamalar

İlk üye işlev, depolanan özel durum maskesini döndürür. İkinci üye *işlev, özel* durum maskesinde _Except depolar ve önceki depolanan değerini döndürür. Yeni bir özel durum maskesi depolamanın, çağrı [açık](#clear) [(rdstate)](#rdstate) gibi bir özel durum ortaya çıkarabileceğini unutmayın.

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

## <a name="basic_iosfail"></a><a name="fail"></a>basic_ios::başarısız

Bir akıştan geçerli bir alanın ayıklanmasının başarısız olduğunu gösterir.

```cpp
bool fail() const;
```

### <a name="return-value"></a>Dönüş Değeri

[rdstate](#rdstate) `& (badbit|failbit)` sıfır değilse **doğru,** aksi takdirde **yanlış**.

Hakkında daha `failbit`fazla bilgi için, [ios_base bakın::iostate](../standard-library/ios-base-class.md#iostate).

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

## <a name="basic_iosfill"></a><a name="fill"></a>basic_ios::doldur

Metin akış kadar geniş olmadığında kullanılacak karakteri belirtir veya döndürür.

```cpp
char_type fill() const;
char_type fill(char_type Char);
```

### <a name="parameters"></a>Parametreler

*Char*\
Dolgu karakteri olarak istediğiniz karakter.

### <a name="return-value"></a>Dönüş Değeri

Geçerli dolgu karakteri.

### <a name="remarks"></a>Açıklamalar

İlk üye işlev depolanan dolgu karakterini döndürür. İkinci üye *işlev, Char'ı* dolgu karakterinde saklar ve önceki depolanan değerini döndürür.

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

## <a name="basic_iosgood"></a><a name="good"></a>basic_ios::iyi

Akışın iyi durumda olduğunu gösterir.

```cpp
bool good() const;
```

### <a name="return-value"></a>Dönüş Değeri

**rdstate** [rdstate](#rdstate) `== goodbit` (hiçbir durum bayrakları ayarlanırsa), aksi takdirde, **yanlış**eğer doğru .

Hakkında daha `goodbit`fazla bilgi için, [ios_base bakın::iostate](../standard-library/ios-base-class.md#iostate).

### <a name="example"></a>Örnek

[Bkz. basic_ios::kötü](#bad) kullanma `good`örneği için.

## <a name="basic_iosimbue"></a><a name="imbue"></a>basic_ios::imbue

Yerel alanı değiştirir.

```cpp
locale imbue(const locale& Loc);
```

### <a name="parameters"></a>Parametreler

*Loc*\
Yerel bir dize.

### <a name="return-value"></a>Dönüş Değeri

Önceki yerel.

### <a name="remarks"></a>Açıklamalar

[Rdbuf](#rdbuf) null işaretçi değilse, üye işlev

`rdbuf`-> [pubimbue](../standard-library/basic-streambuf-class.md#pubimbue)(_ *Loc*)

Her durumda, [ios_base döndürür::imbue](../standard-library/ios-base-class.md#imbue)(_ *Loc).*

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

## <a name="basic_iosinit"></a><a name="init"></a>basic_ios::init

basic_ios yapıcılar tarafından çağrıldı.

```cpp
void init(basic_streambuf<Elem,Traits>* _Sb, bool _Isstd = false);
```

### <a name="parameters"></a>Parametreler

*_Sb*\
Giriş veya çıktı öğelerini depolamak için standart arabellek.

*_Isstd*\
Bunun standart bir akış olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

Üye işlev değerleri tüm üye nesnelerde depolar, böylece:

- [rdbuf](#rdbuf) *_Sb döndürür.*

- [kravat](#tie) null işaretçisi döndürür.

- *_Sb* sıfır değilse, [rdstate](#rdstate) [goodbit'i](../standard-library/ios-base-class.md#iostate) döndürür; aksi takdirde, [badbit](../standard-library/ios-base-class.md#iostate)döndürür.

- [özel](#exceptions) durumlar `goodbit`döndürür.

- bayraklar [skipws](../standard-library/ios-base-class.md#fmtflags) [&#124; aralık](../standard-library/ios-base-class.md#fmtflags) [döndürür.](../standard-library/ios-base-class.md#flags)

- [genişlik](../standard-library/ios-base-class.md#width) 0 döndürür.

- [hassas](../standard-library/ios-base-class.md#precision) döner 6.

- [dolgu](#fill) boşluk karakterini döndürür.

- [getloc](../standard-library/ios-base-class.md#getloc) `locale::classic`döner .

- [iword](../standard-library/ios-base-class.md#iword) sıfır döndürür ve [pword](../standard-library/ios-base-class.md#pword) tüm bağımsız değişken değerleri için bir null işaretçisi döndürür.

## <a name="basic_iosint_type"></a><a name="int_type"></a>basic_ios:int_type

Bir eşanlamlı `traits_type::int_type`.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="basic_iosmove"></a><a name="move"></a>basic_ios::hareket et

İşaretçi dışındaki tüm değerleri, parametreden geçerli nesneye akış arabelleğini taşır.

```cpp
void move(basic_ios&& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Değerleri `ios_base` taşıyacak nesne.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi, *sağda* `*this` değişmeden depolanan `stream buffer pointer`ve null işaretçiye *right* ayarlanan depolanan dışında `*this`depolanan tüm değerleri taşır. Depolanan `tie pointer` *sağda*null işaretçi olarak ayarlanır.

## <a name="basic_iosnarrow"></a><a name="narrow"></a>basic_ios::dar

Belirli `char_type`bir eşdeğer char bulur.

```cpp
char narrow(char_type Char, char Default = '\0') const;
```

### <a name="parameters"></a>Parametreler

*Char*\
Dönüştürmek için **char.**

*Varsayılan*\
Eşdeğeri bulunamazsa döndürülen istediğiniz **char.**

### <a name="return-value"></a>Dönüş Değeri

Belirli `char_type`bir eşdeğer **char** .

### <a name="remarks"></a>Açıklamalar

Üye işlev, e\<use_facet> > [(getloc](../standard-library/ios-base-class.md#getloc)) döndürür. [use_facet](../standard-library/basic-filebuf-class.md#open)\< `narrow`( `Char`, `Default`).

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

## <a name="basic_iosoff_type"></a><a name="off_type"></a>basic_ios::off_type

Bir eşanlamlı `traits_type::off_type`.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="basic_iosoperator-void-"></a><a name="op_void_star"></a>basic_ios::operatör geçersiz *

Akışın hala iyi olup olmadığını gösterir.

```cpp
operator void *() const;
```

### <a name="return-value"></a>Dönüş Değeri

İşleç yalnızca başarısız olursa null işaretçisini [döndürür.](#fail)

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

## <a name="basic_iosoperator"></a><a name="op_not"></a>basic_ios::operatör!

Akış kötü değilse gösterir.

```cpp
bool operator!() const;
```

### <a name="return-value"></a>Dönüş Değeri

İadebaşarısız [oldu.](#fail)

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

## <a name="basic_iosoperator-bool"></a><a name="op_bool"></a>basic_ios::operatör bool

Bir `basic_ios` nesnenin **bool**olarak kullanılmasını sağlar. Sık karşılaşılan istenmeyen yan etkileri önlemek için otomatik tür dönüştürme devre dışı bırakılır.

```cpp
explicit operator bool() const;
```

### <a name="remarks"></a>Açıklamalar

İşletici, yalnızca . **false** `fail()` İade türü sadece **bool**dönüştürülebilir , `void *` değil veya diğer bilinen skaler türü.

## <a name="basic_iospos_type"></a><a name="pos_type"></a>basic_ios::pos_type

Bir eşanlamlı `traits_type::pos_type`.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="basic_iosrdbuf"></a><a name="rdbuf"></a>basic_ios::rdbuf

Yolları akışı belirtilen arabelleğe aktarın.

```cpp
basic_streambuf<Elem, Traits> *rdbuf() const;
basic_streambuf<Elem, Traits> *rdbuf(
basic_streambuf<Elem, Traits>* _Sb);
```

### <a name="parameters"></a>Parametreler

*_Sb*\
Bir dere.

### <a name="remarks"></a>Açıklamalar

İlk üye işlev depolanan akış arabellek işaretçisini döndürür.

İkinci üye işlev depolanan akış arabellek işaretçisinde *_Sb* depolar ve daha önce depolanan değeri döndürür.

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

## <a name="basic_iosrdstate"></a><a name="rdstate"></a>basic_ios::rdstate

Bayraklar için bit durumunu okur.

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

## <a name="basic_iossetstate"></a><a name="setstate"></a>basic_ios::setstate

Ek bayraklar ayarlar.

```cpp
void setstate(iostate _State);
```

### <a name="parameters"></a>Parametreler

*_state*\
Ayarlanan ek bayraklar.

### <a name="remarks"></a>Açıklamalar

Üye işlev etkin [bir](#clear)şekilde açık çağırır (_ *Durum* &#124; [rdstate).](#rdstate)

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

## <a name="basic_iosset_rdbuf"></a><a name="set_rdbuf"></a>basic_ios:set_rdbuf

Bu akış nesnesi için okuma arabelleği olması için bir akış arabelleği atar.

```cpp
void set_rdbuf(
basic_streambuf<Elem, Tr>* strbuf)
```

### <a name="parameters"></a>Parametreler

*strbuf*\
Okundu arabelleği olmak için akış arabelleği.

### <a name="remarks"></a>Açıklamalar

Korunan üye işlevi *strbuf'u* . `stream buffer pointer` Öyle demiyor. `clear`

## <a name="basic_iostie"></a><a name="tie"></a>basic_ios::tie

Bir akışın başka bir akışdan önce işlenmesini sağlar.

```cpp
basic_ostream<Elem, Traits> *tie() const;
basic_ostream<Elem, Traits> *tie(
basic_ostream<Elem, Traits>* str);
```

### <a name="parameters"></a>Parametreler

*Str*\
Bir dere.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlev depolanan kravat işaretçisini döndürür. İkinci üye işlev, kravat işaretçisinde *sabitlenir* ve önceki depolanan değerini döndürür.

### <a name="remarks"></a>Açıklamalar

`tie`diğer akıştaki işlemler tamamlandıktan sonra bir akıştaki işlemlerin oluşması gibi iki akış eşitlenmesine neden olur.

### <a name="example"></a>Örnek

Bu örnekte, cin'i cout'a bağlayarak, "Bir sayı girin:" dizesi cin'den numara ayıklamadan önce konsola gider. Bu, "Bir sayı girin:" dizesinin sayı okunduğunda arabellekte hala oturma olasılığını ortadan kaldırır, böylece kullanıcının gerçekten yanıt vermek için bazı istemi olduğundan emin olacağız. Varsayılan olarak, cin ve cout bağlanır.

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

## <a name="basic_iostraits_type"></a><a name="traits_type"></a>basic_ios:traits_type

Şablon parametresi `Traits`için eşanlamlı.

```cpp
typedef Traits traits_type;
```

## <a name="basic_ioswiden"></a><a name="widen"></a>basic_ios::genişlet

Belirli bir `char_type` **char**eşdeğerini bulur.

```cpp
char_type widen(char Char) const;
```

### <a name="parameters"></a>Parametreler

*Char*\
Dönüştürülecek karakter.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir `char_type` **char**eşdeğerini bulur.

### <a name="remarks"></a>Açıklamalar

Üye işlev, [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype** \< **E**> >(getloc) use_facet döndürür. [getloc](../standard-library/ios-base-class.md#getloc) `widen`( `Char`).

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

## <a name="basic_iosswap"></a><a name="swap"></a>basic_ios::takas

Bu `basic_ios` nesnedeki değerleri başka bir `basic_ios` nesnenin değerleriyle değiştirir. Ancak, akış arabelleklerine işaretçiler takas edilmez.

```cpp
void swap(basic_ios&& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Değer `basic_ios` alışverişi için kullanılan nesne.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi, depolanan `*this` lar dışında `stream buffer pointer` *sağa* depolanan tüm değerleri değiştirir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
