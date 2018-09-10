---
title: basic_ios sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3abc3c08b46577f7d59b2831a68ded812a5da60a
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110024"
---
# <a name="basicios-class"></a>basic_ios Sınıfı

Şablon sınıfı için her iki giriş akışları genel depolama ve üye işlevleri tanımlar (şablon sınıfının [basic_istream](../standard-library/basic-istream-class.md)) ve çıkış akışlarına (şablon sınıfının [basic_ostream](../standard-library/basic-ostream-class.md)) bağlı olduğu Şablon parametreleri. (Sınıfı [ios_base](../standard-library/ios-base-class.md) ortak ve şablon parametreleri bağımlı yenilikler açıklanmaktadır.) Sınıfın bir nesnesi **basic_ios\<Elem sınıfı, nitelikler sınıfı >** yardımcı denetim türünde öğelere sahip bir akış `Elem`, olan karakter nitelikleri sınıfı tarafından belirlenen `Traits`.

## <a name="syntax"></a>Sözdizimi

```cpp

template <class Elem, class Traits>
class basic_ios : public ios_base
```

### <a name="parameters"></a>Parametreler

*Elem*<br/>
Bir tür.

*Nitelikler*<br/>
Türünde bir değişken `char_traits`.

## <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi **basic_ios\<Elem sınıfı, nitelikler sınıfı >** depolar:

- Tie işaretçisi türünde bir nesne [basic_istream](../standard-library/basic-istream-class.md)**\<Elem, nitelikler >**.

- Akış Arabellek işaretçisi türünde bir nesne [basic_streambuf](../standard-library/basic-streambuf-class.md)**\<Elem, nitelikler >**.

- [Biçimlendirme bilgilerini](../standard-library/ios-base-class.md).

- [Stream durum bilgilerini](../standard-library/ios-base-class.md) temel bir nesne türünün içinde [ios_base](../standard-library/ios-base-class.md).

- Türünde bir nesne bir dolgu karakter `char_type`.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_ios](#basic_ios)|Yapıları `basic_ios` sınıfı.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Şablon parametresi için bir eşanlamlı `Elem`.|
|[int_type](#int_type)|İçin bir eşanlamlı `Traits::int_type`.|
|[off_type](#off_type)|İçin bir eşanlamlı `Traits::off_type`.|
|[pos_type](#pos_type)|İçin bir eşanlamlı `Traits::pos_type`.|
|[traits_type](#traits_type)|Şablon parametresi için bir eşanlamlı `Traits`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[hatalı](#bad)|Akış arabelleğinin bütünlüğünü kaybı gösterir.|
|[Temizle](#clear)|Tüm hata bayrakları siler.|
|[copyfmt](#copyfmt)|Bir akıştan bayrakları diğerine kopyalar.|
|[eof](#eof)|Bir akışın sonuna ulaşılıp ulaşılmadığını gösterir.|
|[Özel durumlar](#exceptions)|Akış tarafından özel hangi durumlar gösterir.|
|[Başarısız](#fail)|Geçerli bir alan bir akışından ayıklanacak başarısız olduğunu gösterir.|
|[Dolgu](#fill)|Belirtir veya metin akış kadar geniş olmadığı durumlarda kullanılacak olan karakteri döndürür.|
|[iyi](#good)|Akış iyi durumda olduğunu gösterir.|
|[imbue](#imbue)|Yerel ayar değiştirir.|
|[init](#init)|Çağıran `basic_ios` oluşturucular.|
|[Taşıma](#move)|Akış arabelleği için parametre geçerli nesneye işaretçi dışında tüm değerlerini taşır.|
|[daraltma](#narrow)|Eşdeğer char bulur bir verilen `char_type`.|
|[rdbuf](#rdbuf)|Belirtilen arabellek akışına yollar.|
|[rdstate](#rdstate)|Bit bayrakları için durumunu okur.|
|[set_rdbuf](#set_rdbuf)|Bir akış arabelleğinin Okuma arabelleği için bu akış nesnesi olarak atar.|
|[setstate](#setstate)|Ek bir bayrak ayarlar.|
|[değiştirme](#swap)|Bu değeri birbiriyle değiştirir `basic_ios` olanlar başka bir nesne `basic_ios` nesne. Akış arabellekleri işaretçileri takas değil.|
|[tie](#tie)|Önce başka bir akış, bir akışı işlenir sağlar.|
|[genişletmek](#widen)|Eşdeğer bulur `char_type` için belirli bir karakter.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[Açık işleç bool değeri](#op_bool)|Kullanılmasına bir `basic_ios` nesnesinin bir **bool**. Otomatik tür dönüştürme ortak, istenmeyen yan etkileri önlemek için devre dışı bırakıldı.|
|[işleç hükümsüz *](#op_void_star)|Akış iyi olup olmadığını gösterir.|
|[işleci!](#op_not)|Akış bozuk değilse gösterir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ios >

**Namespace:** std

## <a name="bad"></a>  basic_ios::bad

Akış arabelleğinin bütünlüğünü kaybı gösterir

```cpp
bool bad() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `rdstate & badbit` sıfır; Aksi takdirde **false**.

Daha fazla bilgi için `badbit`, bkz: [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

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

## <a name="basic_ios"></a>  basic_ios::basic_ios

Basic_ios sınıfı oluşturur.

```cpp
explicit basic_ios(basic_streambuf<Elem,  Traits>* sb);
basic_ios();
```

### <a name="parameters"></a>Parametreler

*sb*<br/>
Giriş veya çıkış öğelerini depolamak için standart bir arabellek.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu çağırarak üye nesnelerini başlatır [init](#init)(_ *Sb*). (Korumalı) ikinci oluşturucu, üye başlatılmamış nesneler bırakır. Bir sonraki çağrı `init` güvenli bir şekilde edilebilir önce nesneyi başlatmak gerekir.

## <a name="char_type"></a>  basic_ios::char_type

Şablon parametresi için bir eşanlamlı `Elem`.

```cpp
typedef Elem char_type;
```

## <a name="clear"></a>  basic_ios::Clear

Tüm hata bayrakları siler.

```cpp
void clear(iostate state = goodbit, bool reraise = false);
void clear(io_state state);
```

### <a name="parameters"></a>Parametreler

*Durum* (isteğe bağlı) tüm bayraklar temizledikten sonra ayarlamak istediğiniz bayrakları. Varsayılan olarak `goodbit`.

*reraise* (isteğe bağlı) belirtir olup, özel durum yeniden yükseltilmiş olmalıdır. Varsayılan olarak **false** (özel durum yeniden oluşturmaz).

### <a name="remarks"></a>Açıklamalar

Bayraklar `goodbit`, `failbit`, `eofbit`, ve `badbit`. Test ile bu bayrakları için [iyi](#good), [hatalı](#bad), [eof](#eof), ve [başarısız](#fail)

Üye işlevi, depolanan stream durum bilgileri ile değiştirir:

`state` &#124;`(` [rdbuf](#rdbuf) ! = 0 **goodbit** : **badbit**)

Varsa `state` **&** [özel durumları](#exceptions) olan sıfır olmayan, ardından sınıfın bir nesnesi atar [hatası](../standard-library/ios-base-class.md#failure).

### <a name="example"></a>Örnek

Bkz: [rdstate](#rdstate) ve [getline](../standard-library/string-functions.md#getline) kullanan örnekler için `clear`.

## <a name="copyfmt"></a>  basic_ios::copyfmt

Bir akıştan bayrakları diğerine kopyalar.

```cpp
basic_ios<Elem, Traits>& copyfmt(
const basic_ios<Elem, Traits>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bayrakları kopyalamak istediğiniz akış.

### <a name="return-value"></a>Dönüş Değeri

**Bu** bayrakları Kopyalamakta akış için nesne.

### <a name="remarks"></a>Açıklamalar

Üye işlev geri çağırma olay raporları **silme\_olay**. Bunun ardından kopyalar *doğru* içine  **\*bu** doldurma karakteri KRAVAT işaretçi ve biçimlendirme bilgileri. Özel Durum maskesi değiştirmeden önce geri çağırma olay raporları `copyfmt_event`. Kopyalama tamamlandıktan sonra ise **durumu &**[özel durumları](#exceptions) olan sıfır değilse, işlev etkili bir şekilde çağıran [temizleyin](#clear) bağımsız değişkeniyle [rdstate](#rdstate). Döndürür  **\*bu**.

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

## <a name="eof"></a>  basic_ios::EOF

Bir akışın sonuna ulaşılıp ulaşılmadığını gösterir.

```cpp
bool eof() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** akışın sonuna ulaşıldı, **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü **true** varsa [rdstate](#rdstate) `& eofbit` sıfır değil. Daha fazla bilgi için `eofbit`, bkz: [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

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

## <a name="exceptions"></a>  basic_ios::Exceptions

Akış tarafından özel hangi durumlar gösterir.

```cpp
iostate exceptions() const;
void exceptions(iostate Newexcept);
void exceptions(io_state Newexcept);
```

### <a name="parameters"></a>Parametreler

*Newexcept*<br/>
Özel durum istediğiniz bayrakları.

### <a name="return-value"></a>Dönüş Değeri

Şu anda akış için bir özel durum için belirtilir bayrakları.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, depolanan özel durum maskesini döndürür. İkinci üye işlevi depoları *_Except* özel durum maskesini döndürür, önceki değeri depolanır. Yeni bir özel durum maskesini depolama çağrı gibi bir özel durum oluşturabilecek Not [Temizle](#clear)( [rdstate](#rdstate) ).

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

## <a name="fail"></a>  basic_ios::Fail

Geçerli bir alan bir akışından ayıklanacak başarısız olduğunu gösterir.

```cpp
bool fail() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa [rdstate](#rdstate) `& (badbit|failbit)` Aksi halde sıfır olmayan, olan **false**.

Daha fazla bilgi için `failbit`, bkz: [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

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

## <a name="fill"></a>  basic_ios::Fill

Belirtir veya metin akış kadar geniş olmadığı durumlarda kullanılacak olan karakteri döndürür.

```cpp
char_type fill() const;
char_type fill(char_type Char);
```

### <a name="parameters"></a>Parametreler

*Char*<br/>
Doldurma karakteri olarak istediğiniz karakteri.

### <a name="return-value"></a>Dönüş Değeri

Geçerli doldurma karakteri.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, depolanan doldurma karakteri döndürür. İkinci üye işlevi depoları *Char* doldurma karakteri döndürür, önceki değeri depolanır.

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

## <a name="good"></a>  basic_ios::good

Akış iyi durumda olduğunu gösterir.

```cpp
bool good() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa [rdstate](#rdstate) `== goodbit` (yok durumu bayrakları ayarlanmış), aksi takdirde, **false**.

Daha fazla bilgi için `goodbit`, bkz: [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

### <a name="example"></a>Örnek

Bkz: [basic_ios::bad](#bad) kullanma örneği için `good`.

## <a name="imbue"></a>  basic_ios::imbue

Yerel ayar değiştirir.

```cpp
locale imbue(const locale& Loc);
```

### <a name="parameters"></a>Parametreler

*LOC*<br/>
Bir yerel ayar dizesi.

### <a name="return-value"></a>Dönüş Değeri

Önceki yerel ayar.

### <a name="remarks"></a>Açıklamalar

Varsa [rdbuf](#rdbuf) null işaretçisi değil, üye işlev çağrılarıdır

`rdbuf`-> [pubimbue](../standard-library/basic-streambuf-class.md#pubimbue)(_ *Loc*)

Her durumda döndürür [ios_base::imbue](../standard-library/ios-base-class.md#imbue)(_ *Loc*).

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

## <a name="init"></a>  basic_ios::init

Basic_ios oluşturucular tarafından çağrılır.

```cpp
void init(basic_streambuf<Elem,Traits>* _Sb, bool _Isstd = false);
```

### <a name="parameters"></a>Parametreler

*_Sb*<br/>
Giriş veya çıkış öğelerini depolamak için standart bir arabellek.

*_Isstd*<br/>
Bir standart akışa olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, tüm üye nesneleri değerlerini depolar için:

- [rdbuf](#rdbuf) döndürür *_Sb.*

- [tie](#tie) null bir işaretçi döndürür.

- [rdstate](#rdstate) döndürür [goodbit](../standard-library/ios-base-class.md#iostate) varsa *_Sb* döndürür sıfır olmayan, tersi durumda [badbit](../standard-library/ios-base-class.md#iostate).

- [özel durumlar](#exceptions) döndürür `goodbit`.

- [bayrakları](../standard-library/ios-base-class.md#flags) döndürür [skipws](../standard-library/ios-base-class.md#fmtflags) &#124; [Ara](../standard-library/ios-base-class.md#fmtflags).

- [Genişlik](../standard-library/ios-base-class.md#width) 0 döndürür.

- [Duyarlık](../standard-library/ios-base-class.md#precision) 6 döndürür.

- [Dolgu](#fill) boşluk karakteri döndürür.

- [getloc](../standard-library/ios-base-class.md#getloc) döndürür `locale::classic`.

- [iword](../standard-library/ios-base-class.md#iword) sıfır döndürür ve [pword](../standard-library/ios-base-class.md#pword) tüm bağımsız değişken değerleri null bir işaretçi döndürür.

## <a name="int_type"></a>  basic_ios::int_type

İçin bir eşanlamlı `traits_type::int_type`.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="move"></a>  basic_ios::Move

Akış arabelleği için parametre geçerli nesneye işaretçi dışında tüm değerlerini taşır.

```cpp
void move(basic_ios&& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
`ios_base` Değerlerinden taşımak için nesne.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi, depolanan tüm değerleri taşır *doğru* için `*this` dışındaki saklı `stream buffer pointer`, içinde değiştirilmemiş *doğru* ve null bir işaretçi olarak `*this`. Depolanan `tie pointer` null bir işaretçi olarak ayarlanmış *doğru*.

## <a name="narrow"></a>  basic_ios::Narrow

Eşdeğer char bulur bir verilen `char_type`.

```cpp
char narrow(char_type Char, char Default = '\0') const;
```

### <a name="parameters"></a>Parametreler

*Char*<br/>
**Char** dönüştürülecek.

*Default*<br/>
**Char** eşdeğeri bulunursa döndürülmesini istediğiniz.

### <a name="return-value"></a>Dönüş Değeri

Eşdeğer **char** için bir verilen `char_type`.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [use_facet](../standard-library/basic-filebuf-class.md#open)\<ctype\<E >> ( [getloc](../standard-library/ios-base-class.md#getloc)()).`narrow` ( `Char`, `Default`).

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

## <a name="off_type"></a>  basic_ios::off_type

İçin bir eşanlamlı `traits_type::off_type`.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="op_void_star"></a>  basic_ios::operator void *

Akış iyi olup olmadığını gösterir.

```cpp
operator void *() const;
```

### <a name="return-value"></a>Dönüş Değeri

İşlecini bir null işaretçi yalnızca şu durumlarda döndürür [başarısız](#fail).

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

## <a name="op_not"></a>  basic_ios::operator!

Akış bozuk değilse gösterir.

```cpp
bool operator!() const;
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür [başarısız](#fail).

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

## <a name="op_bool"></a>  basic_ios::operator bool

Kullanılmasına bir `basic_ios` nesnesinin bir **bool**. Otomatik tür dönüştürme ortak, istenmeyen yan etkileri önlemek için devre dışı bırakıldı.

```cpp
explicit operator bool() const;
```

### <a name="remarks"></a>Açıklamalar

İşleci için bir değer dönüştürülebilir döndürür **false** yalnızca `fail()`. Dönüş türüne dönüştürülebilir yalnızca **bool**değil, `void *` veya bilinen diğer skaler türü.

## <a name="pos_type"></a>  basic_ios::pos_type

İçin bir eşanlamlı `traits_type::pos_type`.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="rdbuf"></a>  basic_ios::rdbuf

Belirtilen arabellek akışına yollar.

```cpp
basic_streambuf<Elem, Traits> *rdbuf() const;
basic_streambuf<Elem, Traits> *rdbuf(
basic_streambuf<Elem, Traits>* _Sb);
```

### <a name="parameters"></a>Parametreler

*_Sb*<br/>
Bir akış.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, depolanan Akış Arabellek işaretçisini döndürür.

İkinci üye işlevi depoları *_Sb* saklı akış arabelleğin işaretçisini içinde ve daha önce depolanan değeri döndürür.

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

## <a name="rdstate"></a>  basic_ios::rdstate

Bit bayrakları için durumunu okur.

```cpp
iostate rdstate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Depolanan akış durumunu bilgiler.

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

## <a name="setstate"></a>  basic_ios::setstate

Ek bir bayrak ayarlar.

```cpp
void setstate(iostate _State);
```

### <a name="parameters"></a>Parametreler

*Duru_m*<br/>
Ayarlamak için ek bayraklar.

### <a name="remarks"></a>Açıklamalar

Üye işlevi etkili bir şekilde çağıran [Temizle](#clear)(_ *durumu* &#124; [rdstate](#rdstate)).

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

## <a name="set_rdbuf"></a>  basic_ios::set_rdbuf

Bir akış arabelleğinin Okuma arabelleği için bu akış nesnesi olarak atar.

```cpp
void set_rdbuf(
basic_streambuf<Elem, Tr>* strbuf)
```

### <a name="parameters"></a>Parametreler

*strbuf*<br/>
Okuma arabelleği olacak akış arabelleği.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi depoları *strbuf* içinde `stream buffer pointer`. Çağrılmayan `clear`.

## <a name="tie"></a>  basic_ios::tie

Önce başka bir akış, bir akışı işlenir sağlar.

```cpp
basic_ostream<Elem, Traits> *tie() const;
basic_ostream<Elem, Traits> *tie(
basic_ostream<Elem, Traits>* str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Bir akış.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi, depolanan KRAVAT işaretçiyi döndürür. İkinci üye işlevi depoları *str* KRAVAT işaretçi döndürür, önceki değeri depolanır.

### <a name="remarks"></a>Açıklamalar

`tie` diğer akış işlemleri tamamlandıktan sonra bir akış üzerinde işlemler meydana şekilde eşitlenmesi gereken iki akışları neden olur.

### <a name="example"></a>Örnek

Bu örnekte, cout için cin bağlamadan tarafından da, garanti "bir sayı girin:" dize gider sayı önce konsola kendisini cin ayıklanır. Bu olanağına ortadan kaldırır, "bir sayı girin:" sayı okunduğunda dize arabellek hala oturan, emin ediyoruz, böylece kullanıcının gerçekten yanıt vermek için bazı istemi sahip. Varsayılan olarak, cin ve cout bağlıdır.

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

## <a name="traits_type"></a>  basic_ios::traits_type

Şablon parametresi için bir eşanlamlı `Traits`.

```cpp
typedef Traits traits_type;
```

## <a name="widen"></a>  basic_ios::widen

Eşdeğer bulur `char_type` için bir verilen **char**.

```cpp
char_type widen(char Char) const;
```

### <a name="parameters"></a>Parametreler

*Char*<br/>
Dönüştürülecek karakter.

### <a name="return-value"></a>Dönüş Değeri

Eşdeğer bulur `char_type` için bir verilen **char**.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype** \< **E**>> ( [getloc](../standard-library/ios-base-class.md#getloc)). `widen`( `Char`).

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

## <a name="swap"></a>  basic_ios::Swap

Bu değeri birbiriyle değiştirir `basic_ios` olanlar başka bir nesne `basic_ios` nesne. Ancak, akış arabellekleri işaretçileri takas değil.

```cpp
void swap(basic_ios&& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
`basic_ios` Değerleri değişimi için kullanılan nesne.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi, depolanan tüm değerleri değiştirir *doğru* ile `*this` dışındaki saklı `stream buffer pointer`.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
