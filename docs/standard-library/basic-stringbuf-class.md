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
ms.openlocfilehash: 0445c2f8868fc9f2863ad4a2a12cc00261546c75
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447838"
---
# <a name="basicstringbuf-class"></a>basic_stringbuf Sınıfı

Karakter nitelikleri, bir dizi nesnesinde depolanan öğelerin dizisine ve türüne göre `Elem` `Tr`belirlenen, türü öğelerin aktarımını denetleyen bir akış arabelleğini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>,
    class Alloc = allocator<Elem>>
class basic_stringbuf : public basic_streambuf<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Tahsis*\
Ayırıcı sınıf.

*Elem*\
Dizenin temel öğe öğesi türü.

*Tr*\
Dizenin temel öğesi üzerinde özelleştirilmiş karakter nitelikleri.

## <a name="remarks"></a>Açıklamalar

Nesne, dizideki değişikliklere uyum sağlamak için gereken şekilde ayrılır, genişletilir ve serbest bırakılır.

Basic_stringbuf `Elem`< `ios_base::` `stringbuf`  [](../standard-library/ios-base-class.md#openmode) sınıfının bir nesnesi, >birOpenModebağımsızdeğişkenininbirkopyasınıkendimodmoduolarakoluşturucudandepolar:`Alloc` `Tr`

- Sıfır `mode & ios_base::in` değilse, giriş arabelleğine erişilebilir. Daha fazla bilgi için bkz. [Basic_streambuf Class](../standard-library/basic-streambuf-class.md).

- Sıfır `mode & ios_base::out` değilse, çıkış arabelleği erişilebilir olur.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_stringbuf](#basic_stringbuf)|Türünde `basic_stringbuf`bir nesne oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Tür, bir şablon parametresi *ayırma*için bir eş anlamlı.|
|[char_type](#char_type)|Bir tür adını Elemtemplate  parametresiyle ilişkilendirir.|
|[int_type](#int_type)|Bu türün kapsam içinde `basic_filebuf`, *tr* kapsamındaki aynı ada sahip türüne eşit olmasını sağlar.|
|[off_type](#off_type)|Bu türün kapsam içinde `basic_filebuf`, *tr* kapsamındaki aynı ada sahip türüne eşit olmasını sağlar.|
|[pos_type](#pos_type)|Bu türün kapsam içinde `basic_filebuf`, *tr* kapsamındaki aynı ada sahip türüne eşit olmasını sağlar.|
|[traits_type](#traits_type)|Bir tür adını *tr* şablon parametresiyle ilişkilendirir.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[taşma](#overflow)|Tam arabelleğe yeni bir karakter eklendiğinde çağrılabilen, korunan, sanal bir işlev.|
|[pbackfail](#pbackfail)|Korumalı sanal üye işlevi, giriş arabelleğine bir öğe geri döndürmeye çalışır, ardından bunu geçerli öğe yapar (sonraki işaretçinin gösterdiği).|
|[seekoff](#seekoff)|Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışır.|
|[seekpos](#seekpos)|Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışır.|
|[üstbilgisine](#str)|Yazma konumunu değiştirmeden bir dize arabelleğindeki metni ayarlar veya alır.|
|swap||
|[öğe](#underflow)|Giriş akışından geçerli öğeyi ayıklamak için korunan sanal üye işlevi.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<sstream >

**Ad alanı:** std

## <a name="allocator_type"></a>basic_stringbuf::allocator_type

Tür, bir şablon parametresi *ayırma*için bir eş anlamlı.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringbuf"></a>basic_stringbuf::basic_stringbuf

Türünde `basic_stringbuf`bir nesne oluşturur.

```cpp
basic_stringbuf(
    ios_base::openmode _Mode = ios_base::in | ios_base::out);

basic_stringbuf(
    const basic_string<Elem, Tr, Alloc>& str,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Mod*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*üstbilgisine*\
[Basic_string](../standard-library/basic-string-class.md)türünde bir nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, giriş arabelleğini ve çıkış arabelleğini denetleyen tüm işaretçilerde boş bir işaretçi depolar. Daha fazla bilgi için [Basic_streambuf sınıfının](../standard-library/basic-streambuf-class.md)açıklamalar bölümüne bakın. Ayrıca, *_Mode* öğesini stringarabelleğe modu olarak depolar. Daha fazla bilgi için [basic_stringbuf sınıfının](../standard-library/basic-stringbuf-class.md)açıklamalar bölümüne bakın.

İkinci Oluşturucu dize nesnesi *Str*tarafından denetlenen sıranın bir kopyasını ayırır. Sıfır `_Mode & ios_base::in` değilse, sıranın başlangıcında okumaya başlamak için giriş arabelleğini ayarlar. Sıfır `_Mode & ios_base::out` değilse, sıranın başlangıcında yazmaya başlamak için çıkış arabelleğini ayarlar. Ayrıca, *_Mode* öğesini stringarabelleğe modu olarak depolar. Daha fazla bilgi için [basic_stringbuf sınıfının](../standard-library/basic-stringbuf-class.md)açıklamalar bölümüne bakın.

## <a name="char_type"></a>basic_stringbuf::char_type

Bir tür adını Elemtemplate  parametresiyle ilişkilendirir.

```cpp
typedef Elem char_type;
```

## <a name="int_type"></a>basic_stringbuf::int_type

Bu türü, basic_filebuf's Scope içinde, `Tr` kapsamdaki aynı ada sahip türe eşit hale getirir.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="off_type"></a>basic_stringbuf::off_type

Bu türü, basic_filebuf's Scope içinde, `Tr` kapsamdaki aynı ada sahip türe eşit hale getirir.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="overflow"></a>basic_stringbuf:: overflow

Tam arabelleğe yeni bir karakter eklendiğinde çağrılabilen, korunan bir sanal işlev.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `traits_type::eof`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olmazsa, döndürür `traits_type::eof`. Aksi takdirde, **traits_type::** [Not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *meta*) döndürür.

### <a name="remarks"></a>Açıklamalar

Eğer  *\_meta* şuna eşit **traits_type::** [EOF](../standard-library/char-traits-struct.md#eof)olarak karşılaştırmadığı takdirde, korumalı sanal üye işlevi, **traits_type::** [to_char_type](../standard-library/char-traits-struct.md#to_char_type)( *\_meta*) öğesini öğesine eklemeyi dener çıkış arabelleği. Bunu çeşitli yollarla yapabilirsiniz:

- Bir yazma konumu varsa, öğeyi yazma konumuna kaydedebilir ve çıkış arabelleği için sonraki işaretçiyi artırabilirsiniz.

- Çıktı arabelleği için yeni veya ek depolama alanı ayırarak bir yazma konumu kullanılabilir hale getirir. Çıkış arabelleğini bu şekilde genişletmek, ilişkili giriş arabelleğini de genişletir.

## <a name="pbackfail"></a>basic_stringbuf::p backfail

Korumalı sanal üye işlevi, giriş arabelleğine bir öğe geri döndürmeye çalışır ve sonra geçerli öğe (sonraki işaretçinin gösterdiği) yapar.

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `traits_type::eof`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olmazsa, döndürür `traits_type::eof`. Aksi takdirde, **traits_type::** [Not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *meta*) döndürür.

### <a name="remarks"></a>Açıklamalar

*_Meta* şuna eşit **traits_type::** [EOF](../standard-library/char-traits-struct.md#eof)olarak karşılaştırırsa, geri gönderme öğesi geçerli öğeden önceki akışta etkin bir şekilde olur. Aksi takdirde, bu öğe **byte** = **traits_type::** [to_char_type](../standard-library/char-traits-struct.md#to_char_type)(_ *meta*) ile değiştirilmiştir. İşlevi bir öğeyi çeşitli yollarla geri alabilir:

- Bir Putback konumu varsa ve depolanan öğe bayt ile eşit olarak karşılaştırıyorsa, giriş arabelleği için bir sonraki işaretçiyi azaledebilir.

- Bir Putback konumu varsa ve StringBuffer modu sıranın değiştirilmesini izin veriyorsa ( **mode & ios_base:: Out** sıfır değilse), bayt putback konumuna saklayabilir ve giriş arabelleği için bir sonraki işaretçiyi azaltır.

## <a name="pos_type"></a>basic_stringbuf::p os_type

Bu türü, basic_filebuf's Scope içinde, `Tr` kapsamdaki aynı ada sahip türe eşit hale getirir.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="seekoff"></a>basic_stringbuf:: seekoff

Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışır.

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Kapatma*\
*_Yönteme*göre arama yapılacak konum. Daha fazla bilgi için bkz. [basic_stringbuf:: off_type](#off_type).

*_Yol*\
Dengeleme işlemleri için başlangıç noktası. Olası değerler için bkz. [ios_base:: seekdir](../standard-library/ios-base-class.md#seekdir) .

*_Mod*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin verir. Daha fazla bilgi için bkz. [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode).

### <a name="return-value"></a>Dönüş Değeri

Yeni konumu veya geçersiz akış konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Sınıfının `basic_stringbuf<Elem, Tr, Alloc>`bir nesnesi için bir akış konumu yalnızca bir akış sapmasını içerir. Sıfır değeri, denetlenen dizinin ilk öğesini belirler.

Yeni konum aşağıdaki gibi belirlenir:

- İse `_Way` , == Yenikonum akışın başıdır ve *_kapalıdır.* `ios_base::beg`

- İse `_Way` , == Yenikonum geçerli akış konumudur ve *_Off olur.* `ios_base::cur`

- İse `_Way` , == Yenikonum akışın sonu ve *_Off olur.* `ios_base::end`

Sıfır `_Mode & ios_base::in` değilse, işlev giriş arabelleğindeki bir sonraki konumu oku olarak değiştirir. Sıfır `_Mode & ios_base::out` değilse, işlev çıkış arabelleğine yazmak için bir sonraki konumu değiştirir. Bir akışın etkilenmesi için arabelleğinin mevcut olması gerekir. Konumlandırma işleminin başarılı olması için, elde edilen akış konumu denetimli sıra içinde olmalıdır. İşlev her iki akış konumunu da etkiliyorsa, *_Way* `ios_base::beg` ya da `ios_base::end` ya da her iki akış aynı öğeye konumlandırılmış olmalıdır. Aksi takdirde (veya hiçbir konum etkilenmezse), konumlandırma işlemi başarısız olur.

İşlev, akış konumlarından birini ya da her ikisini de değiştirmek için başarılı olursa, sonuç akış konumunu döndürür. Aksi takdirde, başarısız olur ve geçersiz bir akış konumu döndürür.

## <a name="seekpos"></a>basic_stringbuf:: seekpos

Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışır.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*\
Arama yapılacak konum.

*_Mod*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin verir.

### <a name="return-value"></a>Dönüş Değeri

İşlev, akış konumlarından birini ya da her ikisini de değiştirmek için başarılı olursa, sonuç akış konumunu döndürür. Aksi takdirde, başarısız olur ve geçersiz bir akış konumu döndürür. Akış konumunun geçersiz olup olmadığını anlamak için dönüş değerini ile `pos_type(off_type(-1))`karşılaştırın.

### <a name="remarks"></a>Açıklamalar

Basic_stringbuf < **eled**, `Alloc` **tr**> sınıfının bir nesnesi için bir akış konumu yalnızca bir akış sapmasını içerir. Sıfır değeri, denetlenen dizinin ilk öğesini belirler. Yeni konum _ *SP*tarafından belirlenir.

Eğer **mode & ios_base:: ın** değeri sıfır değilse, işlev giriş arabelleğindeki bir sonraki konumu oku olarak değiştirir. Eğer **mode & ios_base:: Out** değeri sıfır değilse, işlev çıkış arabelleğine yazmak için bir sonraki konumu değiştirir. Bir akışın etkilenmesi için arabelleğinin mevcut olması gerekir. Konumlandırma işleminin başarılı olması için, elde edilen akış konumu denetimli sıra içinde olmalıdır. Aksi takdirde (veya hiçbir konum etkilenmezse), konumlandırma işlemi başarısız olur.

## <a name="str"></a>basic_stringbuf:: Str

Yazma konumunu değiştirmeden bir dize arabelleğindeki metni ayarlar veya alır.

```cpp
basic_string<Elem, Tr, Alloc> str() const;
void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Parametreler

*_Newstr*\
Yeni dize.

### <a name="return-value"></a>Dönüş Değeri

Denetlenen\< sırası **Bu tarafından\*** denetlenen sıranın bir kopyası olan [basic_string](../standard-library/basic-string-class.md) **eled**, **tr**, ayırma **>** sınıfının bir nesnesini döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, denetlenen sırası  **\*bu**tarafından denetlenen sıranın bir kopyası olan basic_string < **eled**, `Alloc` **tr**> sınıfının bir nesnesini döndürür. Kopyalanmış sıra depolanan dize arabelleği moduna bağlıdır:

- **Mod & ios_base:: Out** değeri sıfır değilse ve bir çıkış arabelleği varsa, sıra çıkış arabelleğinin tamamı (ile `pbase`başlayan [epptr](../standard-library/basic-streambuf-class.md#epptr) - [pbase](../standard-library/basic-streambuf-class.md#pbase) öğeleri).

- Eğer **Mode & ios_base:: ın** değeri sıfır değilse ve bir giriş arabelleği varsa, dizi tüm giriş arabelleğinin `eback`(ile başlayan [egptr](../standard-library/basic-streambuf-class.md#egptr) - [eback](../standard-library/basic-streambuf-class.md#eback) öğelerinden) oluşur.

- Aksi takdirde, kopyalanmış dizi boştur.

İkinci üye işlevi, şu anda  **\*bu**tarafından denetlenen herhangi bir sırayı kaldırır. Daha sonra *_Newstr*tarafından denetlenen sıranın bir kopyasını ayırır. **Mode & ios_base:: ın** değeri sıfır değilse, sıranın başlangıcında okumayı başlatmak için giriş arabelleğini ayarlar. **Mod & ios_base:: Out** değeri sıfır değilse, çıkış arabelleğini sıranın başlangıcında yazmaya başlamak için ayarlar.

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

## <a name="traits_type"></a>basic_stringbuf::traits_type

Bir tür adını *tr* şablon parametresiyle ilişkilendirir.

```cpp
typedef Tr traits_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, *tr*şablon parametresi için bir eş anlamlı.

## <a name="underflow"></a>basic_stringbuf:: yetersiz

Geçerli öğeyi giriş akışından ayıklamak için korumalı, sanal işlev.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olmazsa, **traits_type::** [EOF](../standard-library/char-traits-struct.md#eof)döndürür. Aksi takdirde, dönüştürülmüş giriş akışındaki geçerli öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi `byte` , geçerli öğeyi giriş arabelleğinden çıkarmaya çalışır, geçerli akış konumunu ilerletin ve öğeyi **traits_type::** [to_int_type](../standard-library/char-traits-struct.md#to_int_type)( **byte**) olarak döndürür. Bunu tek bir şekilde yapabilirsiniz: Bir okuma konumu varsa, okuma konumunda depolanan öğesi `byte` olarak alır ve giriş arabelleği için sonraki işaretçiyi ilerletir.

## <a name="swap"></a>basic_streambuf:: swap

Bu dize arabelleğinin içeriğini başka bir dize arabelleği ile değiştirir.

```cpp
void basic_stringbuf<T>::swap(basic_stringbuf& other)
```

### <a name="parameters"></a>Parametreler

*farklı*\
İçeriği bu basic_stringbuf ile takas edilecek basic_stringbuf.

### <a name="remarks"></a>Açıklamalar

## <a name="op_eq"></a>basic_stringbuf:: operator =

Basic_stringbuf içeriğini işlecin sağ tarafına, sol taraftaki basic_stringbuf 'e atar.

```cpp
basic_stringbuf& basic_stringbuf:: operator=(const basic_stringbuf& other)
```

### <a name="parameters"></a>Parametreler

*farklı*\
Yerel ayar nitelikleri de dahil olmak üzere, içeriği işlecinin sol tarafındaki dize arabelleğe atanacak bir basic_stringbuf.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
