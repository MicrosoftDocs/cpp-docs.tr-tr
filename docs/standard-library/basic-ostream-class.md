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
ms.openlocfilehash: 9025d595e79eed9f81aff77b931a2585359a8c3a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78874855"
---
# <a name="basic_ostream-class"></a>basic_ostream Sınıfı

Bu sınıf şablonu, öğe ve kodlanmış nesnelerin, [traits_type](../standard-library/basic-ios-class.md#traits_type)olarak da bilinen sınıf `Tr`tarafından belirlendiği şekilde, [char_type](../standard-library/basic-ios-class.md#char_type)olarak da bilinen `Elem`türündeki öğelerle bir akış arabelleğine eklenmesini denetleyen bir nesne tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ostream : virtual public basic_ios<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Eled*\
Bir `char_type`.

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

Basic_istream\< **Eled**, **tr**> sınıfının bir nesnesi yalnızca [basic_ios](../standard-library/basic-ios-class.md) **\<eled**, **tr >** sınıfının bir sanal ortak taban nesnesini depolar.

## <a name="example"></a>Örnek

Çıkış akışları hakkında daha fazla bilgi edinmek için [Basic_ofstream sınıfının](../standard-library/basic-ofstream-class.md) örneğine bakın.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_ostream](#basic_ostream)|`basic_ostream` nesnesi oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[temizlenemiyor](#flush)|Arabelleği boşaltır.|
|[konur](#put)|Bir akışa bir karakter koyar.|
|[seekp](#seekp)|Çıkış akışındaki konumu sıfırlar.|
|[Nöbetçisi](#sentry)|İç içe yerleştirilmiş sınıf, bildirim yapılarını biçimlendirilen çıkış işlevlerini ve biçimlendirilmemiş çıkış işlevlerini içeren bir nesneyi tanımlar.|
|[Kur](#swap)|Bu `basic_ostream` nesnenin değerlerini, belirtilen `basic_ostream` nesnesinin değerleri için değiştirir.|
|[tellp](#tellp)|Çıkış akışında rapor konumu.|
|[write](#write)|Bir akışa karakter koyar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|Bu nesneye, belirtilen `basic_ostream` Object parametresinin değerini atar.|
|[işleç < <](#basic_ostream_operator_lt_lt)|Akışa yazar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<ostream >

**Ad alanı:** std

## <a name="basic_ostream"></a>basic_ostream:: basic_ostream

`basic_ostream` nesnesi oluşturur.

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

*sağ*\
`basic_ostream`türündeki bir nesneye rvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu [init](../standard-library/basic-ios-class.md#init)(`strbuf`) öğesini çağırarak temel sınıfı başlatır. İkinci Oluşturucu, [basic_ios:: move](../standard-library/basic-ios-class.md#move)`(right)`çağırarak temel sınıfı başlatır.

### <a name="example"></a>Örnek

Çıkış akışları hakkında daha fazla bilgi edinmek için [basic_ofstream:: basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) örneğe bakın.

## <a name="flush"></a>basic_ostream:: Flush

Arabelleği boşaltır.

```cpp
basic_ostream<Elem, Tr>& flush();
```

### <a name="return-value"></a>Dönüş Değeri

Basic_ostream nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

[Rdarabelleğe](../standard-library/basic-ios-class.md#rdbuf) boş bir işaretçi değilse, işlev **rdarabelleğe->** [pubsync](../standard-library/basic-streambuf-class.md#pubsync)öğesini çağırır. Bu değer-1 döndürürse, işlev [SetState](../standard-library/basic-ios-class.md#setstate)(**badbit**) öğesini çağırır. **\*** döndürür.

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

## <a name="basic_ostream_operator_lt_lt"></a>basic_ostream:: operator&lt;&lt;

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
`stream_buf` nesnesine yönelik bir işaretçi.

*val*\
Akışa yazılacak bir öğe.

### <a name="return-value"></a>Dönüş Değeri

Basic_ostream nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

\<ostream > üst bilgisi birçok genel ekleme işlecini de tanımlar. Daha fazla bilgi için bkz. [operator < <](../standard-library/ostream-operators.md#op_lt_lt).

İlk üye işlevi, form ifadesinin [endl](../standard-library/ostream-functions.md#endl) **(ostr)** `ostr << endl` ve ardından **\*** döndürmesini sağlar. İkinci ve üçüncü işlevleri, [onaltılık](../standard-library/ios-functions.md#hex)gibi diğer işleicilere benzer şekilde davrandığından emin olmanızı sağlamaktır. Kalan işlevler tüm biçimli çıkış işlevleridir.

İşlevi

```cpp
basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
```

*strarabelleğe* bir null işaretçi değilse ve bunları eklediğinde öğeleri *strarabelleğe*ayıklar. Dosya sonunda ayıklama durduruluyor veya bir ayıklama bir özel durum oluşturursa (yeniden oluşturulur). Ayrıca, bir ekleme başarısız olursa, söz konusu öğeyi ayıklamadan da duraklar. İşlev hiçbir öğe eklediğinde veya bir ayıklama bir özel durum oluşturursa, işlev [SetState](../standard-library/basic-ios-class.md#setstate)(**failbit**) yöntemini çağırır. Herhangi bir durumda, işlev **\*** döndürür.

İşlevi

```cpp
basic_ostream<Elem, Tr>& operator<<(bool val);
```

`_Val` Boole alanına dönüştürür ve [use_facet](../standard-library/basic-filebuf-class.md#open) **< Num_put\<Eled, outit >** `(`[getloc](../standard-library/ios-base-class.md#getloc)) çağırarak ekler. [PUT](#put)(**rdtıt**)[](../standard-library/basic-ios-class.md#rdbuf), **\*this**, `getloc`, **Val**). Burada `OutIt` [ostreambuf_iterator](../standard-library/ostreambuf-iterator-class.md) **\<Eled, tr >** olarak tanımlanmıştır. İşlev **\*** döndürür.

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

her dönüştürme bir sayısal alana *değer* girin ve **use_facet < Num_put\<elek, outit >** (`getloc`) çağırarak ekleyin. **PUT**( **`rdbuf`** ), **\*** , `getloc`, **Val**). Burada, **Outit** **ostreambuf_iterator\<Eled, tr >** olarak tanımlanmıştır. İşlev **\*** döndürür.

İşlevler

```cpp
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
```

her dönüştürme bir sayısal alana *değer* girin ve **use_facet < Num_put\<elek, outit >** (`getloc`) **. Put**(**outit**(`rdbuf`), **\*** , `getloc`, **Val**) çağırır. Burada, **Outit** **ostreambuf_iterator\<Eled, tr >** olarak tanımlanmıştır. İşlev **\*** döndürür.

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

*sağ*\
Bir `basic_ostream` nesnesine `rvalue` başvurusu.

### <a name="remarks"></a>Açıklamalar

Üye işleci takas `(right)`çağırır.

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

Biçimlendirilmemiş output işlevi *_Ch*öğesi ekler. **\*** döndürür.

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

*_Off*\
*_Way*göreli konum.

*_Way*\
[İos_base:: seekdir](../standard-library/ios-base-class.md#seekdir) Numaralandırmalardan biri.

### <a name="return-value"></a>Dönüş Değeri

Basic_ostream nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

[Başarısız](../standard-library/basic-ios-class.md#fail) **olursa, ilk üye işlevi, bazı**`pos_type` geçici nesne `newpos`için **newpos =** [rdarabelleğe](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)( *_Pos*) yöntemini çağırır. `fail` false ise, ikinci işlev **newpos = rdarabelleğe->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)( *_Off, _Way*) öğesini çağırır. Her iki durumda da (`off_type`)**newpos = =** (`off_type`) (-1) (konumlandırma işlemi başarısız olursa), işlev **istr** ' ı çağırır. [SetState](../standard-library/basic-ios-class.md#setstate)(**failbit**). Her iki işlev de **\*** döndürür.

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

sınıf Sentry {public: açık Sentry (basic_ostream\<Eled, tr > & _Ostr); operator bool () const; ~ Sentry ();};

### <a name="remarks"></a>Açıklamalar

İç içe yerleştirilmiş sınıf, bildirim yapılarını biçimlendirilen çıkış işlevlerini ve biçimlendirilmemiş çıkış işlevlerini içeren bir nesneyi tanımlar. Eğer **OSTR.** [iyi](../standard-library/basic-ios-class.md#good) ve **OSTR** **doğru** . bağlama null bir [işaretçi değil,](../standard-library/basic-ios-class.md#tie) Oluşturucu **OSTR. bağlama->** [Temizleme](#flush)işlemi çağırır. Sonra Oluşturucu, `status``ostr.good` tarafından döndürülen değeri depolar. Daha sonraki bir `operator bool` çağrısı, bu depolanmış değeri sağlar.

`uncaught_exception` **false** [döndürürse ve](../standard-library/ios-base-class.md#flags) **&** [unitarabelleğe](../standard-library/ios-functions.md#unitbuf) sıfır değilse, yıkıcı [Temizleme](#flush)çağırır.

## <a name="swap"></a>basic_ostream:: swap

Bu `basic_ostream` nesnesinin değerlerini, belirtilen `basic_ostream`değerleri için değiştirir.

```cpp
void swap(basic_ostream& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
`basic_ostream` nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, *sağ*içerikleri için bu nesnenin içeriğini değiş tokuş etmek üzere [basic_ios:: Swap](../standard-library/basic-ios-class.md#swap)`(right)` çağırır.

## <a name="tellp"></a>basic_ostream:: tellp

Çıkış akışında rapor konumu.

```cpp
pos_type tellp();
```

### <a name="return-value"></a>Dönüş Değeri

Çıkış akışındaki konum.

### <a name="remarks"></a>Açıklamalar

[Başarısız](../standard-library/basic-ios-class.md#fail) **olursa, üye**işlevi [rdarabelleğe](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(0, `cur`, **içinde**) döndürür. Aksi takdirde, `pos_type`(-1) döndürür.

### <a name="example"></a>Örnek

`tellp`kullanarak bir örnek için bkz. [seekp](#seekp) .

## <a name="write"></a>basic_ostream:: Write

Bir akışa karakter koyun.

```cpp
basic_ostream<Elem, Tr>& write(const char_type* str, streamsize count);
```

### <a name="parameters"></a>Parametreler

*sayı*\
Akışa yerleştirilecek karakter sayısı.

*str*\
Akışa yerleştirilecek karakterler.

### <a name="return-value"></a>Dönüş Değeri

Basic_ostream nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

[Biçimlendirilmemiş output işlevi](../standard-library/basic-ostream-class.md) , *Str* *'dan başlayan Count* öğelerinin dizisini ekler.

### <a name="example"></a>Örnek

`write`kullanarak bir örnek için [streamsize](../standard-library/ios-typedefs.md#streamsize) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Standart kitaplıkta Iş parçacığı güvenliği\ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
