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
ms.openlocfilehash: 8715ae4816be9c8f1453b243d1c8d3574d8c97cf
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457861"
---
# <a name="basicostream-class"></a>basic_ostream Sınıfı

Bu şablon sınıfı, öğelerin ve kodlanmış nesnelerin, karakter nitelikleri sınıf `Elem` `Tr`tarafından belirlendiği şekilde, [char_type](../standard-library/basic-ios-class.md#char_type)olarak da bilinen öğe ve kodlanmış nesneleri bir akış arabelleğine ekleme [traits_type](../standard-library/basic-ios-class.md#traits_type)olarak bilinir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ostream : virtual public basic_ios<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Elem*\
A `char_type`.

*Tr*\
Karakter `traits_type`.

## <a name="remarks"></a>Açıklamalar

Üye işlevlerinin çoğu [< <](#basic_ostream_operator_lt_lt) aşırı yükleme, çıktı işlevleri olarak biçimlendirilir. Bunlar, şu kalıbı izler:

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

Basic_istream\< **eled**, **tr**> sınıfının bir nesnesi yalnızca [basic_ios](../standard-library/basic-ios-class.md) **\<eled**, **tr >** sınıfının bir sanal ortak taban nesnesini depolar.

## <a name="example"></a>Örnek

Çıkış akışları hakkında daha fazla bilgi için bkz. [Basic_ofstream Class](../standard-library/basic-ofstream-class.md) örneği.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_ostream](#basic_ostream)|Bir `basic_ostream` nesnesi oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[temizlenemiyor](#flush)|Arabelleği boşaltır.|
|[konur](#put)|Bir akışa bir karakter koyar.|
|[seekp](#seekp)|Çıkış akışındaki konumu sıfırlar.|
|[Nöbetçisi](#sentry)|İç içe yerleştirilmiş sınıf, bildirim yapılarını biçimlendirilen çıkış işlevlerini ve biçimlendirilmemiş çıkış işlevlerini içeren bir nesneyi tanımlar.|
|[Kur](#swap)|Bu `basic_ostream` nesnenin değerlerini, belirtilen `basic_ostream` nesnenin değerleri için değiş tokuş eder.|
|[tellp](#tellp)|Çıkış akışında rapor konumu.|
|[write](#write)|Bir akışa karakter koyar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Bu nesneye, belirtilen `basic_ostream` nesne parametresinin değerini atar.|
|[işleç < <](#basic_ostream_operator_lt_lt)|Akışa yazar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<ostream >

**Ad alanı:** std

## <a name="basic_ostream"></a>basic_ostream::basic_ostream

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
bu standart bir akıştır; Aksi takdirde, **false**.

*Right*\
Türündeki `basic_ostream`bir nesneye rvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, [init](../standard-library/basic-ios-class.md#init)(`strbuf`) öğesini çağırarak temel sınıfı başlatır. İkinci Oluşturucu, [basic_ios:: Move](../standard-library/basic-ios-class.md#move)`(right)`öğesini çağırarak temel sınıfı başlatır.

### <a name="example"></a>Örnek

Çıkış akışları hakkında daha fazla bilgi edinmek için [basic_ofstream:: basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) örneğine bakın.

## <a name="flush"></a>basic_ostream:: Flush

Arabelleği boşaltır.

```cpp
basic_ostream<Elem, Tr>& flush();
```

### <a name="return-value"></a>Dönüş Değeri

Basic_ostream nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

[Rdarabelleğe](../standard-library/basic-ios-class.md#rdbuf) boş bir işaretçi değilse, işlev **rdarabelleğe->** [pubsync](../standard-library/basic-streambuf-class.md#pubsync)öğesini çağırır. Bu değer-1 döndürürse, işlev [SetState](../standard-library/basic-ios-class.md#setstate)(**badbit**) öğesini çağırır. Bunu döndürür  **\*.**

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

## <a name="basic_ostream_operator_lt_lt"></a>basic_ostream:: işleci&lt;&lt;

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

\<Ostream > üst bilgisi birçok genel ekleme işlecini de tanımlar. Daha fazla bilgi için bkz. [operator < <](../standard-library/ostream-operators.md#op_lt_lt).

İlk üye işlevi `ostr << endl` , formun bir ifadesinin [endl](../standard-library/ostream-functions.md#endl) **(OSTR)** çağırmasını sağlar ve  **\*bunu**döndürür. İkinci ve üçüncü işlevleri, [onaltılık](../standard-library/ios-functions.md#hex)gibi diğer işleicilere benzer şekilde davrandığından emin olmanızı sağlamaktır. Kalan işlevler tüm biçimli çıkış işlevleridir.

İşlevi

```cpp
basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
```

*strarabelleğe* bir null işaretçi değilse ve bunları eklediğinde öğeleri *strarabelleğe*ayıklar. Dosya sonunda ayıklama durduruluyor veya bir ayıklama bir özel durum oluşturursa (yeniden oluşturulur). Ayrıca, bir ekleme başarısız olursa, söz konusu öğeyi ayıklamadan da duraklar. İşlev hiçbir öğe eklediğinde veya bir ayıklama bir özel durum oluşturursa, işlev [SetState](../standard-library/basic-ios-class.md#setstate)(**failbit**) yöntemini çağırır. Herhangi bir durumda, işlev  **\*bunu**döndürür.

İşlevi

```cpp
basic_ostream<Elem, Tr>& operator<<(bool val);
```

bir `_Val` Boole alanına dönüştürür ve [use_facet](../standard-library/basic-filebuf-class.md#open) **\<< num_put eled, outit >** `(`[getloc](../standard-library/ios-base-class.md#getloc)) çağırarak ekler. [Yerleştir](#put) (**Rdtıt**([rdarabelleğe](../standard-library/basic-ios-class.md#rdbuf)),  **\*Bu**, `getloc`, **Val**). Burada, `OutIt` [ostreambuf_iterator](../standard-library/ostreambuf-iterator-class.md)**eled,tr>olaraktanımlanmıştır.\<** İşlevi  **\*bunu**döndürür.

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

her dönüştürme bir sayısal alana *değer* girin ve **\<use_facet < num_put eled, outit >** (`getloc`) çağırarak ekleyin. **Yerleştir** (**Outit**(`rdbuf`  **\*), bu**,  ,Val`getloc`). Burada, **outit** **, ostreambuf_iterator\<eled, tr >** olarak tanımlanmıştır. İşlevi  **\*bunu**döndürür.

İşlevler

```cpp
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
```

her dönüştürme bir sayısal alana *değer* girin ve **use_facet < num_put\<eled, outit >** (`getloc`) **. Put**(**outit**(`rdbuf`),  **\*bu**, `getloc`, **Val**). Burada, **outit** **, ostreambuf_iterator\<eled, tr >** olarak tanımlanmıştır. İşlevi  **\*bunu**döndürür.

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

## <a name="op_eq"></a>basic_ostream:: operator =

Bu nesneye, belirtilen `basic_ostream` nesne parametresi için değerler atar.

```cpp
basic_ostream& operator=(basic_ostream&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`rvalue` Bir`basic_ostream` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Member işleci Swap `(right)`öğesini çağırır.

## <a name="put"></a>basic_ostream::p UT

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

Biçimlendirilmemiş output işlevi, *_Ch*öğesini ekler. Bunu döndürür  **\*.**

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

## <a name="seekp"></a>basic_ostream:: seekp

Çıkış akışındaki konumu sıfırlayın.

```cpp
basic_ostream<Elem, Tr>& seekp(pos_type _Pos);

basic_ostream<Elem, Tr>& seekp(off_type _Off, ios_base::seekdir _Way);
```

### <a name="parameters"></a>Parametreler

*_Pos*\
Akıştaki konum.

*_Kapatma*\
*_Yönteme*göre göreli konum.

*_Yol*\
[İos_base:: seekdir](../standard-library/ios-base-class.md#seekdir) Numaralandırmalardan biri.

### <a name="return-value"></a>Dönüş Değeri

Basic_ostream nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

[Başarısız](../standard-library/basic-ios-class.md#fail) **olursa, ilk**üye işlevi bazı **->** [](../standard-library/basic-ios-class.md#rdbuf)   Geçici`pos_type` nesneler içinnewpos=rdarabelleğe`newpos` [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)(_Pos) öğesini çağırır. Yanlış ise ikinci işlev **newpos = rdarabelleğe->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)( *_Off, _Way*) yöntemini çağırır. `fail` Her iki durumda da`off_type`()**newpos = =** (`off_type`) (-1) (konumlandırma işlemi başarısız olursa), işlev **istr çağırır.** [SetState](../standard-library/basic-ios-class.md#setstate) (**failbit**). Her iki işlev de  **\*bunu**döndürür.

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

## <a name="sentry"></a>basic_ostream:: Sentry

İç içe yerleştirilmiş sınıf, bildirim yapılarını biçimlendirilen çıkış işlevlerini ve biçimlendirilmemiş çıkış işlevlerini içeren bir nesneyi tanımlar.

sınıf Sentry {public: Explicit Sentry (basic_ostream\<eled, tr > & _Ostr); operator bool () const; ~ Sentry ();};

### <a name="remarks"></a>Açıklamalar

İç içe yerleştirilmiş sınıf, bildirim yapılarını biçimlendirilen çıkış işlevlerini ve biçimlendirilmemiş çıkış işlevlerini içeren bir nesneyi tanımlar. Eğer **OSTR.** [iyi](../standard-library/basic-ios-class.md#good) ve **OSTR** **doğru** . bağlama null bir işaretçi değil, Oluşturucu **OSTR. bağlama->** [Temizleme](#flush) [işlemi çağırır](../standard-library/basic-ios-class.md#tie) . Sonra Oluşturucu, içinde `ostr.good` `status`tarafından döndürülen değeri depolar. Daha sonraki bir çağrı `operator bool` , bu depolanmış değeri teslim eder.

[](../standard-library/ios-base-class.md#flags) **&** [](../standard-library/ios-functions.md#unitbuf) [](#flush)  False döndürürse ve unitarabelleğe bayrakları sıfır değilse, yıkıcı Temizleme çağırır. `uncaught_exception`

## <a name="swap"></a>basic_ostream:: swap

Bu `basic_ostream` nesnenin değerlerini, belirtilen `basic_ostream`değerleri için değiş tokuş eder.

```cpp
void swap(basic_ostream& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir `basic_ostream` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, *sağ*içerikleri için bu nesnenin içeriğini değiş tokuş etmek üzere [basic_ios:: Swap](../standard-library/basic-ios-class.md#swap) `(right)` öğesini çağırır.

## <a name="tellp"></a>basic_ostream:: tellp

Çıkış akışında rapor konumu.

```cpp
pos_type tellp();
```

### <a name="return-value"></a>Dönüş Değeri

Çıkış akışındaki konum.

### <a name="remarks"></a>Açıklamalar

[Başarısız](../standard-library/basic-ios-class.md#fail) **olursa, üye**işlevi [rdarabelleğe](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(0, `cur` **içinde**) döndürür. Aksi takdirde, ( `pos_type`-1) döndürür.

### <a name="example"></a>Örnek

Örneği`tellp`için bkz. [seekp](#seekp) .

## <a name="write"></a>basic_ostream:: Write

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

Kullanarak`write`bir örnek için bkz. [streamsize](../standard-library/ios-typedefs.md#streamsize) .

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
