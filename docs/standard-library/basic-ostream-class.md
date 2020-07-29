---
title: basic_ostream Sınıfı
ms.date: 03/27/2019
f1_keywords:
- ostream/std::basic_ostream
- ostream/std::basic_ostream::flush
- ostream/std::basic_ostream::put
- ostream/std::basic_ostream::seekp
- ostream/std::basic_ostream::sentry
- ostream/std::basic_ostream::swap
- ostream/std::basic_ostream::tellp
- ostream/std::basic_ostream::write
helpviewer_keywords:
- std::basic_ostream [C++]
- std::basic_ostream [C++], flush
- std::basic_ostream [C++], put
- std::basic_ostream [C++], seekp
- std::basic_ostream [C++], sentry
- std::basic_ostream [C++], swap
- std::basic_ostream [C++], tellp
- std::basic_ostream [C++], write
ms.assetid: 5baadc65-b662-4fab-8c9f-94457c58cda1
ms.openlocfilehash: 972c21feec805e4c1032f0ebad1e3ac0d7daa7dc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219241"
---
# <a name="basic_ostream-class"></a>basic_ostream Sınıfı

Bu sınıf şablonu, öğe ve kodlanmış nesnelerin `Elem` , [char_type](../standard-library/basic-ios-class.md#char_type)olarak da bilinen, karakter nitelikleri `Tr` [traits_type](../standard-library/basic-ios-class.md#traits_type)olarak da bilinen sınıf tarafından belirlendiği şekilde bir akış arabelleğine eklenmesini denetleyen bir nesne tanımlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ostream : virtual public basic_ios<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Elem*\
Bir `char_type`.

*Tr*\
Karakter `traits_type` .

## <a name="remarks"></a>Açıklamalar

Çok sayıda üye işlevi aşırı yükleme [işleci<<](#basic_ostream_operator_lt_lt) , çıkış işlevleridir. Bunlar, şu kalıbı izler:

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (ok)
{try
{<convert and insert elements
    accumulate flags in state> }
    catch (...)
{try
{setstate(badbit);

}
    catch (...)
{}
    if ((exceptions()& badbit) != 0)
    throw; }}
width(0);
// Except for operator<<(Elem)
setstate(state);

return (*this);
```

Diğer iki üye işlevi biçimlendirilmemiş çıkış işlevleridir. Bunlar, şu kalıbı izler:

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (!ok)
    state |= badbit;
else
{try
{<obtain and insert elements
    accumulate flags in state> }
    catch (...)
{try
{setstate(badbit);

}
    catch (...)
{}
    if ((exceptions()& badbit) != 0)
    throw; }}
setstate(state);

return (*this);
```

Her iki işlev grubu, öğe eklenirken bir hatayla karşılaştıklarında [SetState](../standard-library/basic-ios-class.md#setstate)(**badbit**) çağrısı çağırır.

Basic_istream sınıfının bir nesnesi \< **Elem**, **Tr**> , yalnızca basic_ios sınıfının bir sanal ortak taban nesnesini depolar [basic_ios](../standard-library/basic-ios-class.md) **\<Elem**, **Tr>** .

## <a name="example"></a>Örnek

Çıkış akışları hakkında daha fazla bilgi edinmek için [Basic_ofstream sınıfının](../standard-library/basic-ofstream-class.md) örneğine bakın.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_ostream](#basic_ostream)|Bir `basic_ostream` nesnesi oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[flush](#flush)|Arabelleği boşaltır.|
|[konur](#put)|Bir akışa bir karakter koyar.|
|[seekp](#seekp)|Çıkış akışındaki konumu sıfırlar.|
|[Nöbetçisi](#sentry)|İç içe yerleştirilmiş sınıf, bildirim yapılarını biçimlendirilen çıkış işlevlerini ve biçimlendirilmemiş çıkış işlevlerini içeren bir nesneyi tanımlar.|
|[Kur](#swap)|Bu nesnenin değerlerini, `basic_ostream` belirtilen nesnenin değerleri için değiş tokuş eder `basic_ostream` .|
|[tellp](#tellp)|Çıkış akışında rapor konumu.|
|[yazarken](#write)|Bir akışa karakter koyar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|`basic_ostream`Bu nesneye, belirtilen nesne parametresinin değerini atar.|
|[işleç<<](#basic_ostream_operator_lt_lt)|Akışa yazar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<ostream>

**Ad alanı:** std

## <a name="basic_ostreambasic_ostream"></a><a name="basic_ostream"></a>basic_ostream:: basic_ostream

Bir `basic_ostream` nesnesi oluşturur.

```cpp
explicit basic_ostream(
    basic_streambuf<Elem, Tr>* strbuf,
    bool _Isstd = false);

basic_ostream(basic_ostream&& right);
```

### <a name="parameters"></a>Parametreler

*strarabelleğe*\
[Basic_streambuf](../standard-library/basic-streambuf-class.md)türünde bir nesne.

*_Isstd*\
**`true`** Bu bir standart akışdır; Aksi takdirde, **`false`** .

*Right*\
Türündeki bir nesneye rvalue başvurusu `basic_ostream` .

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, [init](../standard-library/basic-ios-class.md#init)() öğesini çağırarak temel sınıfı başlatır `strbuf` . İkinci Oluşturucu, [basic_ios:: Move](../standard-library/basic-ios-class.md#move)çağırarak temel sınıfı başlatır `(right)` .

### <a name="example"></a>Örnek

Çıkış akışları hakkında daha fazla bilgi edinmek için [basic_ofstream:: basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) örneğe bakın.

## <a name="basic_ostreamflush"></a><a name="flush"></a>basic_ostream:: Flush

Arabelleği boşaltır.

```cpp
basic_ostream<Elem, Tr>& flush();
```

### <a name="return-value"></a>Dönüş Değeri

Basic_ostream nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

[Rdarabelleğe](../standard-library/basic-ios-class.md#rdbuf) boş bir işaretçi değilse, işlev **rdarabelleğe->** [pubsync](../standard-library/basic-streambuf-class.md#pubsync)öğesini çağırır. Bu değer-1 döndürürse, işlev [SetState](../standard-library/basic-ios-class.md#setstate)(**badbit**) öğesini çağırır. ** \* Bunu döndürür.**

### <a name="example"></a>Örnek

```cpp
// basic_ostream_flush.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "test";
   cout.flush();
}
```

```Output
test
```

## <a name="basic_ostreamoperatorltlt"></a><a name="basic_ostream_operator_lt_lt"></a>basic_ostream:: işleci&lt;&lt;

Akışa yazar.

```cpp
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& (* Pfn)(basic_ostream<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(
    ios_base& (* Pfn)(ios_base&));

basic_ostream<Elem, Tr>& operator<<(
    basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
basic_ostream<Elem, Tr>& operator<<(bool val);
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int __w64  val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long __w64  val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```

### <a name="parameters"></a>Parametreler

*PFN*\
Bir işlev işaretçisi.

*strarabelleğe*\
Bir `stream_buf` nesne işaretçisi.

*Acil*\
Akışa yazılacak bir öğe.

### <a name="return-value"></a>Dönüş Değeri

Basic_ostream nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

\<ostream>Üst bilgi ayrıca birçok genel ekleme işlecini tanımlar. Daha fazla bilgi için bkz. [operatör<<](../standard-library/ostream-operators.md#op_lt_lt).

İlk üye işlevi, formun bir ifadesinin `ostr << endl` [endl](../standard-library/ostream-functions.md#endl)**(OSTR)** çağırmasını sağlar ve ** \* bunu**döndürür. İkinci ve üçüncü işlevleri, [onaltılık](../standard-library/ios-functions.md#hex)gibi diğer işleicilere benzer şekilde davrandığından emin olmanızı sağlamaktır. Kalan işlevler tüm biçimli çıkış işlevleridir.

İşlevi

```cpp
basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
```

*strarabelleğe* bir null işaretçi değilse ve bunları eklediğinde öğeleri *strarabelleğe*ayıklar. Dosya sonunda ayıklama durduruluyor veya bir ayıklama bir özel durum oluşturursa (yeniden oluşturulur). Ayrıca, bir ekleme başarısız olursa, söz konusu öğeyi ayıklamadan da duraklar. İşlev hiçbir öğe eklediğinde veya bir ayıklama bir özel durum oluşturursa, işlev [SetState](../standard-library/basic-ios-class.md#setstate)(**failbit**) yöntemini çağırır. Herhangi bir durumda, işlev ** \* bunu**döndürür.

İşlevi

```cpp
basic_ostream<Elem, Tr>& operator<<(bool val);
```

`_Val`Boole alanına dönüştürür ve [use_facet](../standard-library/basic-filebuf-class.md#open) ** \<Elem, OutIt><num_put** `(` [getloc](../standard-library/ios-base-class.md#getloc)) çağırarak ekler. [PUT](#put)(**rdtıt**)[rdbuf](../standard-library/basic-ios-class.md#rdbuf), ** \* this**, `getloc` , **Val**). Burada `OutIt` [ostreambuf_iterator](../standard-library/ostreambuf-iterator-class.md)olarak tanımlanmıştır **\<Elem, Tr>** . İşlevi ** \* bunu**döndürür.

İşlevler

```cpp
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```

her dönüştürme bir sayısal alana *değer* girin ve **use_facet<num_put \<Elem, OutIt> **() çağırarak ekleyin `getloc` . **PUT**(**outit**( `rdbuf` ), ** \* Bu**, `getloc` , **Val**). Burada, **Utit** **ostreambuf_iterator \<Elem, Tr> **olarak tanımlanmıştır. İşlevi ** \* bunu**döndürür.

İşlevler

```cpp
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
```

her dönüştürme bir sayısal alana *değer* girin ve **use_facet<num_put \<Elem, OutIt> **( `getloc` )**. Put**(**OutIt**( `rdbuf` ), ** \* this**, `getloc` , **Val**) çağırarak ekleyin. Burada, **Utit** **ostreambuf_iterator \<Elem, Tr> **olarak tanımlanmıştır. İşlevi ** \* bunu**döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_ostream_op_write.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;

ios_base& hex2( ios_base& ib )
{
   ib.unsetf( ios_base::dec );
   ib.setf( ios_base::hex );
   return ib;
}

basic_ostream<char, char_traits<char> >& somefunc(basic_ostream<char, char_traits<char> > &i)
{
    if (i == cout)
    {
        i << "i is cout" << endl;
    }
    return i;
}

class CTxtStreambuf : public basic_streambuf< char, char_traits< char > >
{
public:
    CTxtStreambuf(char *_pszText)
    {
        pszText = _pszText;
        setg(pszText, pszText, pszText + strlen(pszText));
    };
    char *pszText;
};

int main()
{
    cout << somefunc;
    cout << 21 << endl;

    hex2(cout);
    cout << 21 << endl;

    CTxtStreambuf f("text in streambuf");
    cout << &f << endl;
}
```

## <a name="basic_ostreamoperator"></a><a name="op_eq"></a>basic_ostream:: operator =

Bu nesneye, belirtilen nesne parametresi için değerler atar `basic_ostream` .

```cpp
basic_ostream& operator=(basic_ostream&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`rvalue`Bir `basic_ostream` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Member işleci Swap öğesini çağırır `(right)` .

## <a name="basic_ostreamput"></a><a name="put"></a>basic_ostream::p UT

Bir akışa bir karakter koyar.

```cpp
basic_ostream<Elem, Tr>& put(char_type _Ch);
```

### <a name="parameters"></a>Parametreler

*_Ch*\
Bir karakter.

### <a name="return-value"></a>Dönüş Değeri

Basic_ostream nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş output işlevi *_Ch*öğesi ekler. ** \* Bunu döndürür.**

### <a name="example"></a>Örnek

```cpp
// basic_ostream_put.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout.put( 'v' );
   cout << endl;
   wcout.put( L'l' );
}
```

```Output
v
l
```

## <a name="basic_ostreamseekp"></a><a name="seekp"></a>basic_ostream:: seekp

Çıkış akışındaki konumu sıfırlayın.

```cpp
basic_ostream<Elem, Tr>& seekp(pos_type _Pos);

basic_ostream<Elem, Tr>& seekp(off_type _Off, ios_base::seekdir _Way);
```

### <a name="parameters"></a>Parametreler

*_Pos*\
Akıştaki konum.

*_Off*\
*_Way*göreli konum.

*_Way*\
[İos_base:: seekdir](../standard-library/ios-base-class.md#seekdir) Numaralandırmalardan biri.

### <a name="return-value"></a>Dönüş Değeri

Basic_ostream nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

[Başarısız](../standard-library/basic-ios-class.md#fail) olursa **`false`** , ilk üye işlevi bazı geçici nesneler için **newpos =** [rdarabelleğe](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)(*_Pos*) öğesini çağırır `pos_type` `newpos` . `fail`Yanlışsa, ikinci işlev **newpos = rdarabelleğe->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(*_Off, _Way*) yöntemini çağırır. Her iki durumda da ( `off_type` )**newpos = =** ( `off_type` ) (-1) (konumlandırma işlemi başarısız olursa), işlev **istr çağırır.** [SetState](../standard-library/basic-ios-class.md#setstate)(**failbit**). Her iki işlev de ** \* bunu**döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_ostream_seekp.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main()
{
    using namespace std;
    ofstream x("basic_ostream_seekp.txt");
    streamoff i = x.tellp();
    cout << i << endl;
    x << "testing";
    i = x.tellp();
    cout << i << endl;
    x.seekp(2);   // Put char in third char position in file
    x << " ";

    x.seekp(2, ios::end);   // Put char two after end of file
    x << "z";
}
```

```Output
0
7
```

## <a name="basic_ostreamsentry"></a><a name="sentry"></a>basic_ostream:: Sentry

İç içe yerleştirilmiş sınıf, bildirim yapılarını biçimlendirilen çıkış işlevlerini ve biçimlendirilmemiş çıkış işlevlerini içeren bir nesneyi tanımlar.

sınıf Sentry {public: açık Sentry (basic_ostream \<Elem, Tr>& _Ostr); operator bool () const; ~ Sentry ();};

### <a name="remarks"></a>Açıklamalar

İç içe yerleştirilmiş sınıf, bildirim yapılarını biçimlendirilen çıkış işlevlerini ve biçimlendirilmemiş çıkış işlevlerini içeren bir nesneyi tanımlar. Eğer **OSTR.** [iyi](../standard-library/basic-ios-class.md#good) **`true`** ve **OSTR.** bağlama null bir [işaretçi değil,](../standard-library/basic-ios-class.md#tie) Oluşturucu **OSTR. bağlama->** [Temizleme](#flush)işlemi çağırır. Sonra Oluşturucu, içinde tarafından döndürülen değeri depolar `ostr.good` `status` . Daha sonraki bir çağrı, `operator bool` Bu depolanmış değeri teslim eder.

`uncaught_exception`Döndürüyor **`false`** ve [Flags](../standard-library/ios-base-class.md#flags) **&** [unitarabelleğe](../standard-library/ios-functions.md#unitbuf) sıfır değilse, yıkıcı [Temizleme](#flush)çağırır.

## <a name="basic_ostreamswap"></a><a name="swap"></a>basic_ostream:: swap

Bu nesnenin değerlerini, `basic_ostream` belirtilen değerleri için değiş tokuş eder `basic_ostream` .

```cpp
void swap(basic_ostream& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir `basic_ostream` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, [basic_ios::swap](../standard-library/basic-ios-class.md#swap) `(right)` *sağ*içerikleri için bu nesnenin içeriğini değiş tokuş etmek üzere basic_ios:: Swap öğesini çağırır.

## <a name="basic_ostreamtellp"></a><a name="tellp"></a>basic_ostream:: tellp

Çıkış akışında rapor konumu.

```cpp
pos_type tellp();
```

### <a name="return-value"></a>Dönüş Değeri

Çıkış akışındaki konum.

### <a name="remarks"></a>Açıklamalar

[Başarısız](../standard-library/basic-ios-class.md#fail) olursa **`false`** , üye işlevi [rdarabelleğe](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(0, `cur` **içinde**) döndürür. Aksi takdirde, `pos_type` (-1) döndürür.

### <a name="example"></a>Örnek

Örneği için bkz. [seekp](#seekp) `tellp` .

## <a name="basic_ostreamwrite"></a><a name="write"></a>basic_ostream:: Write

Bir akışa karakter koyun.

```cpp
basic_ostream<Elem, Tr>& write(const char_type* str, streamsize count);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Akışa yerleştirilecek karakter sayısı.

*üstbilgisine*\
Akışa yerleştirilecek karakterler.

### <a name="return-value"></a>Dönüş Değeri

Basic_ostream nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

[Biçimlendirilmemiş output işlevi](../standard-library/basic-ostream-class.md) , *Str* *'dan başlayan Count* öğelerinin dizisini ekler.

### <a name="example"></a>Örnek

Kullanarak bir örnek için bkz. [streamsize](../standard-library/ios-typedefs.md#streamsize) `write` .

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
