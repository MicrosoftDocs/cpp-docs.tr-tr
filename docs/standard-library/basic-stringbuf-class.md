---
title: basic_stringbuf Sınıfı
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_stringbuf
- sstream/std::basic_stringbuf::allocator_type
- sstream/std::basic_stringbuf::char_type
- sstream/std::basic_stringbuf::int_type
- sstream/std::basic_stringbuf::off_type
- sstream/std::basic_stringbuf::pos_type
- sstream/std::basic_stringbuf::traits_type
- sstream/std::basic_stringbuf::overflow
- sstream/std::basic_stringbuf::pbackfail
- sstream/std::basic_stringbuf::seekoff
- sstream/std::basic_stringbuf::seekpos
- sstream/std::basic_stringbuf::str
- sstream/std::basic_stringbuf::underflow
helpviewer_keywords:
- std::basic_stringbuf [C++]
- std::basic_stringbuf [C++], allocator_type
- std::basic_stringbuf [C++], char_type
- std::basic_stringbuf [C++], int_type
- std::basic_stringbuf [C++], off_type
- std::basic_stringbuf [C++], pos_type
- std::basic_stringbuf [C++], traits_type
- std::basic_stringbuf [C++], overflow
- std::basic_stringbuf [C++], pbackfail
- std::basic_stringbuf [C++], seekoff
- std::basic_stringbuf [C++], seekpos
- std::basic_stringbuf [C++], str
- std::basic_stringbuf [C++], underflow
ms.assetid: 40c85f9e-42a5-4a65-af5c-23c8e3bf8113
ms.openlocfilehash: 578d0e31e08f3e077a908c4344f77da5495df40d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364881"
---
# <a name="basic_stringbuf-class"></a>basic_stringbuf Sınıfı

Karakter özellikleri sınıf `Elem` `Tr`tarafından belirlenen tür öğelerinin iletimini denetleyen bir akış arabelleği, bir dizi nesnesinde depolanan öğeler dizisine ve bu tür öğelerin iletimini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>,
    class Alloc = allocator<Elem>>
class basic_stringbuf : public basic_streambuf<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Ayırma*\
Ayırıcı sınıf.

*Elem*\
Dize temel öğenin türü.

*Tr*\
Karakter özellikleri dize temel öğesi üzerinde uzmanlaşmıştır.

## <a name="remarks"></a>Açıklamalar

Nesne, dizideki değişiklikleri karşılamak için gerektiğinde ayrılır, genişletilir ve serbest bırakılır.

`Elem`Sınıf basic_stringbuf< bir `Tr` `Alloc` nesne , , `ios_base::`> `stringbuf` kendi mod **modu**olarak kendi oluşturucudan [openmode](../standard-library/ios-base-class.md#openmode) bağımsız değişkeninin bir kopyasını depolar:

- `mode & ios_base::in` Sıfır değilse, giriş arabelleği erişilebilir. Daha fazla bilgi için [basic_streambuf Sınıfı'na](../standard-library/basic-streambuf-class.md)bakın.

- `mode & ios_base::out` Sıfır değilse, çıktı arabelleği erişilebilir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_stringbuf](#basic_stringbuf)|Türünde `basic_stringbuf`bir nesne oluşturuyor.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Allocator_type](#allocator_type)|Tür, şablon parametresi *Alloc*ile eş anlamlıdır.|
|[Char_type](#char_type)|Bir tür adını *Elem* şablon parametresi ile ilişkilendirer.|
|[Int_type](#int_type)|Bu türü `basic_filebuf`Tr *kapsamındaki* aynı adın türüne eşdeğer 'kapsamda yapar.|
|[off_type](#off_type)|Bu türü `basic_filebuf`Tr *kapsamındaki* aynı adın türüne eşdeğer 'kapsamda yapar.|
|[pos_type](#pos_type)|Bu türü `basic_filebuf`Tr *kapsamındaki* aynı adın türüne eşdeğer 'kapsamda yapar.|
|[traits_type](#traits_type)|Bir tür adını *Tr* şablon parametresi ile ilişkilendirer.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Taşma](#overflow)|Tam bir arabelleğe yeni bir karakter eklendiğinde çağrılabilen korumalı, sanal bir işlev.|
|[pbackfail](#pbackfail)|Korumalı sanal üye işlev, bir öğeyi giriş arabelleğine geri koymaya çalışır, sonra onu geçerli öğe (bir sonraki işaretçitarafından işaret eder) yapar.|
|[seekoff](#seekoff)|Korumalı sanal üye işlevi, denetitilen akışlar için geçerli konumları değiştirmeye çalışır.|
|[seekpos](#seekpos)|Korumalı sanal üye işlevi, denetitilen akışlar için geçerli konumları değiştirmeye çalışır.|
|[Str](#str)|Yazma konumunu değiştirmeden metni bir dize arabelleği içinde ayarlar veya alır.|
|swap||
|[akış altı](#underflow)|Geçerli öğeyi giriş akışından ayıklamak için korunan sanal üye işlevi.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<sstream>

**Ad alanı:** std

## <a name="basic_stringbufallocator_type"></a><a name="allocator_type"></a>basic_stringbuf:allocator_type

Tür, şablon parametresi *Alloc*ile eş anlamlıdır.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringbufbasic_stringbuf"></a><a name="basic_stringbuf"></a>basic_stringbuf:basic_stringbuf

Türünde `basic_stringbuf`bir nesne oluşturuyor.

```cpp
basic_stringbuf(
    ios_base::openmode _Mode = ios_base::in | ios_base::out);

basic_stringbuf(
    const basic_string<Elem, Tr, Alloc>& str,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Mode*\
ios_base'daki sayısallaştırmalardan [biri::openmode](../standard-library/ios-base-class.md#openmode).

*Str*\
Basic_string türünde [bir](../standard-library/basic-string-class.md)nesne.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, giriş arabelleği ve çıktı arabelleği denetleyen tüm işaretçilerde bir null işaretçisi depolar. Daha fazla bilgi için basic_streambuf [Sınıfının](../standard-library/basic-streambuf-class.md)Açıklamalar bölümüne bakın. Ayrıca stringbuf modu olarak *_Mode* depolar. Daha fazla bilgi için basic_stringbuf [Sınıfının](../standard-library/basic-stringbuf-class.md)Açıklamalar bölümüne bakın.

İkinci oluşturucu dize *nesnesi str*tarafından denetlenir dizi bir kopyasını ayırır. `_Mode & ios_base::in` Sıfır değilse, giriş arabelleği sıranın başında okumaya başlamak için ayarlar. `_Mode & ios_base::out` Sıfır değilse, çıkış arabelleği sıranın başında yazmaya başlamak için ayarlar. Ayrıca stringbuf modu olarak *_Mode* depolar. Daha fazla bilgi için basic_stringbuf [Sınıfının](../standard-library/basic-stringbuf-class.md)Açıklamalar bölümüne bakın.

## <a name="basic_stringbufchar_type"></a><a name="char_type"></a>basic_stringbuf:char_type

Bir tür adını *Elem* şablon parametresi ile ilişkilendirer.

```cpp
typedef Elem char_type;
```

## <a name="basic_stringbufint_type"></a><a name="int_type"></a>basic_stringbuf::int_type

Bu türü, basic_filebuf kapsamında, `Tr` kapsamdaki aynı adın türüne eşdeğer hale getirir.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="basic_stringbufoff_type"></a><a name="off_type"></a>basic_stringbuf:off_type

Bu türü, basic_filebuf kapsamında, `Tr` kapsamdaki aynı adın türüne eşdeğer hale getirir.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="basic_stringbufoverflow"></a><a name="overflow"></a>basic_stringbuf::taşma

Tam bir arabelleğe yeni bir karakter eklendiğinde çağrılabilen korumalı sanal işlev.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `traits_type::eof`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olamazsa, döndürür. `traits_type::eof` Aksi takdirde, traits_type döndürür:: **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta).*

### <a name="remarks"></a>Açıklamalar

*\_*[to_char_type](../standard-library/char-traits-struct.md#to_char_type)[eof](../standard-library/char-traits-struct.md#eof) **traits_type::** * \_Meta* traits_type eşit karşılaştırmak değilse:: eof , korumalı sanal üye işlevi traits_type öğesi eklemek için **çalışır::** to_char_type ( Meta ) çıkış arabelleği içine. Bunu çeşitli şekillerde yapabilirsiniz:

- Bir yazma konumu varsa, öğeyi yazma konumuna depolayabilir ve çıktı arabelleği için bir sonraki işaretçiyi artım.

- Çıktı arabelleği için yeni veya ek depolama alanı ayırarak yazma konumunu kullanılabilir hale getirebilir. Çıktı arabelleği bu şekilde genişletilmesi de ilişkili giriş arabellek genişletir.

## <a name="basic_stringbufpbackfail"></a><a name="pbackfail"></a>basic_stringbuf::pbackfail

Korumalı sanal üye işlev, bir öğeyi giriş arabellesine geri koymaya ve sonra onu geçerli öğe (bir sonraki işaretçiye işaret eden) yapmaya çalışır.

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `traits_type::eof`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olamazsa, döndürür. `traits_type::eof` Aksi takdirde, traits_type döndürür:: **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta).*

### <a name="remarks"></a>Açıklamalar

*_Meta* traits_type eşit karşılaştırırsa:: **traits_type::**[eof](../standard-library/char-traits-struct.md#eof), geri itmek için öğe etkili bir geçerli öğe önce akışı zaten biridir. Aksi takdirde, bu öğe **bayt** = traits_type ile**değiştirilir::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(_ *Meta).* İşlev çeşitli şekillerde bir öğegeri koyabilirsiniz:

- Bir geri alma konumu varsa ve orada depolanan öğe bayt ile karşılaştırırsa, giriş arabelleği için bir sonraki işaretçiyi atabilir.

- Bir geri alma konumu varsa ve stringbuf modu dizinin değiştirilmesine izin verirse **(mod & ios_base::out** sıfır değildir), byte'yi putback konumuna depolayabilir ve giriş arabelleği için bir sonraki işaretçiyi bozabilir.

## <a name="basic_stringbufpos_type"></a><a name="pos_type"></a>basic_stringbuf::pos_type

Bu türü, basic_filebuf kapsamında, `Tr` kapsamdaki aynı adın türüne eşdeğer hale getirir.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="basic_stringbufseekoff"></a><a name="seekoff"></a>basic_stringbuf::seekoff

Korumalı sanal üye işlevi, denetitilen akışlar için geçerli konumları değiştirmeye çalışır.

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_off*\
*_Way*göreli aramak için pozisyon . Daha fazla bilgi için [bkz: basic_stringbuf::off_type](#off_type).

*_way*\
Ofset işlemleri için başlangıç noktası. Bkz. [ios_base::olası](../standard-library/ios-base-class.md#seekdir) değerler için seekdir.

*_Mode*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin vermektir. Daha fazla bilgi için [bkz: ios_base::openmode](../standard-library/ios-base-class.md#openmode).

### <a name="return-value"></a>Dönüş Değeri

Yeni konumu veya geçersiz akış konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi için `basic_stringbuf<Elem, Tr, Alloc>`akış konumu tamamen bir akış ofsetinden oluşur. Ofset sıfır, denetlenir dizinin ilk öğesini belirtir.

Yeni pozisyon aşağıdaki gibi belirlenir:

- `_Way`  == Eğer `ios_base::beg`, yeni pozisyon akışın başlangıcı artı *_Off.*

- `_Way`  == Eğer `ios_base::cur`, yeni konum geçerli akış konumu artı *_Off*.

- `_Way`  == Eğer `ios_base::end`, yeni pozisyon akışı artı *_Off*sonudur.

Sıfır `_Mode & ios_base::in` değilse, işlev giriş arabelleği okumak için bir sonraki konumu değiştirir. Sıfır `_Mode & ios_base::out` değilse, işlev çıktı arabelleği yazmak için bir sonraki konumu değiştirir. Bir akışın etkilenmesi için arabelleği bulunması gerekir. Bir konumlandırma işleminin başarılı olabilmesi için, elde edilen akış konumunun denetlenme sırası içinde olması gerekir. İşlev her iki akış konumunu `ios_base::beg` da `ios_base::end` etkiliyorsa, *_Way* olması gerekir veya her iki akış da aynı öğede konumlandırılmış olmalıdır. Aksi takdirde (veya her iki konum etkilenmez), konumlandırma işlemi başarısız olur.

İşlev akış konumlarından birini veya her ikisini değiştirmeyi başarırsa, ortaya çıkan akış konumunu döndürür. Aksi takdirde, başarısız olur ve geçersiz bir akış konumunu döndürür.

## <a name="basic_stringbufseekpos"></a><a name="seekpos"></a>basic_stringbuf::seekpos

Korumalı sanal üye işlevi, denetitilen akışlar için geçerli konumları değiştirmeye çalışır.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*\
Aranacak pozisyon.

*_Mode*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

İşlev akış konumlarından birini veya her ikisini değiştirmeyi başarırsa, ortaya çıkan akış konumunu döndürür. Aksi takdirde, başarısız olur ve geçersiz bir akış konumunu döndürür. Akış konumunun geçersiz olup olmadığını belirlemek için, `pos_type(off_type(-1))`iade değerini .

### <a name="remarks"></a>Açıklamalar

Sınıf basic_stringbuf< **Elem**, **Tr**Tr `Alloc` ,> bir akış konumu tamamen bir akış ofset oluşur bir nesne için. Ofset sıfır, denetlenir dizinin ilk öğesini belirtir. Yeni pozisyon _ *Sp*tarafından belirlenir.

**Mod & ios_base::in** sıfır değilse, işlev giriş arabelleğinde okunacak bir sonraki konumu değiştirir. **Mod & ios_base::out** sıfır değilse, işlev çıktı arabellesine yazmak için bir sonraki konumu değiştirir. Bir akışın etkilenmesi için arabelleği bulunması gerekir. Bir konumlandırma işleminin başarılı olabilmesi için, elde edilen akış konumunun denetlenme sırası içinde olması gerekir. Aksi takdirde (veya her iki konum etkilenmez), konumlandırma işlemi başarısız olur.

## <a name="basic_stringbufstr"></a><a name="str"></a>basic_stringbuf::str

Yazma konumunu değiştirmeden metni bir dize arabelleği içinde ayarlar veya alır.

```cpp
basic_string<Elem, Tr, Alloc> str() const;
void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Parametreler

*_Newstr*\
Yeni dize.

### <a name="return-value"></a>Dönüş Değeri

**Elem**, **Tr**, Alloc **>,** kontrollü dizi ** \*bu**tarafından kontrol edilen sıranın bir kopyası olan sınıf [basic_string](../standard-library/basic-string-class.md) \< bir nesne döndürür .

### <a name="remarks"></a>Açıklamalar

İlk üye işlev, kontrol edilen dizi ** \*bu**tarafından `Alloc` kontrol edilen dizinin bir kopyası olan **Elem**, **Tr**,>< sınıf basic_string bir nesne döndürür. Kopyalanan sıra, depolanan stringbuf moduna bağlıdır:

- **Mod & ios_base::out** sıfır değildir ve bir çıktı arabelleği varsa, dizi tüm çıkış arabelleğidir ( [epptr](../standard-library/basic-streambuf-class.md#epptr) - [pbase](../standard-library/basic-streambuf-class.md#pbase) elemanları ile `pbase`başlayan).

- **Mod & ios_base::in** sıfır değildir ve bir giriş arabelleği varsa, dizi tüm giriş arabelleğidir `eback`( [egptr](../standard-library/basic-streambuf-class.md#egptr) - [eback](../standard-library/basic-streambuf-class.md#eback) elemanları ile başlayan).

- Aksi takdirde, kopyalanan sıra boştur.

İkinci üye işlev şu anda ** \*bu**tarafından kontrol edilen herhangi bir dizi yer alır. Daha sonra *_Newstr*tarafından denetlenir dizi bir kopyasını ayırır. **mod & ios_base::in** sıfır değilse, giriş arabelleği sıranın başında okumaya başlamak için ayarlar. **mod & ios_base::out** sıfır değilse, çıkış arabellesini dizinin başında yazmaya başlamak üzere ayarlar.

### <a name="example"></a>Örnek

```cpp
// basic_stringbuf_str.cpp
// compile with: /EHsc
#include <iostream>
#include <sstream>

using namespace std;

int main( )
{
   basic_string<char> i( "test" );
   stringstream ss;

   ss.rdbuf( )->str( i );
   cout << ss.str( ) << endl;

   ss << "z";
   cout << ss.str( ) << endl;

   ss.rdbuf( )->str( "be" );
   cout << ss.str( ) << endl;
}
```

```Output
test
zest
be
```

## <a name="basic_stringbuftraits_type"></a><a name="traits_type"></a>basic_stringbuf:traits_type

Bir tür adını *Tr* şablon parametresi ile ilişkilendirer.

```cpp
typedef Tr traits_type;
```

### <a name="remarks"></a>Açıklamalar

Türü şablon parametresi *Tr*için eşanlamlıdır.

## <a name="basic_stringbufunderflow"></a><a name="underflow"></a>basic_stringbuf::underflow

Geçerli öğeyi giriş akışından ayıklamak için korumalı, sanal işlev.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Dönüş Değeri

Fonksiyon başarılı **olamazsa, traits_type döndürür::**[eof](../standard-library/char-traits-struct.md#eof). Aksi takdirde, dönüştürülür giriş akışı, geçerli öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlev, giriş `byte` arabelleğinden geçerli öğeyi ayıklamaya, geçerli akış konumunu ilerletmeye ve öğeyi traits_type olarak döndürmeye **çalışır:**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( **bayt).** Bunu tek bir şekilde yapabilir: Okuma konumu varsa, `byte` okuma konumunda depolanan öğe olarak alır ve giriş arabelleği için bir sonraki işaretçiyi ilerler.

## <a name="basic_streambufswap"></a><a name="swap"></a>basic_streambuf::takas

Bu dize arabelleği içeriğini başka bir dize arabelleği ile değiştirir.

```cpp
void basic_stringbuf<T>::swap(basic_stringbuf& other)
```

### <a name="parameters"></a>Parametreler

*Diğer*\
İçeriği bu basic_stringbuf takas edilecek basic_stringbuf.

### <a name="remarks"></a>Açıklamalar

## <a name="basic_stringbufoperator"></a><a name="op_eq"></a>basic_stringbuf::operator=

İşleticinin sağ tarafındaki basic_stringbuf içeriğini sol taraftaki basic_stringbuf atar.

```cpp
basic_stringbuf& basic_stringbuf:: operator=(const basic_stringbuf& other)
```

### <a name="parameters"></a>Parametreler

*Diğer*\
Yerel özellikler de dahil olmak üzere içeriği olan bir basic_stringbuf, işlecinin sol tarafındaki stringbuf'a atanır.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
