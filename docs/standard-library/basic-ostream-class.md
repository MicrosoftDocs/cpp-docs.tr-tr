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
ms.openlocfilehash: e074eb30d31c316411dd43f9a7a019defb64e9fe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376760"
---
# <a name="basic_ostream-class"></a>basic_ostream Sınıfı

Bu sınıf şablonu, öğelerin ve kodlanmış nesnelerin eklemeyi denetleyen bir nesneyi `Elem`açıklar, char_type [olarak](../standard-library/basic-ios-class.md#char_type)da bilinir , karakter `Tr`özellikleri sınıf tarafından da bilinir , [traits_type](../standard-library/basic-ios-class.md#traits_type)olarak da bilinir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ostream : virtual public basic_ios<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Elem*\
Bir `char_type`.

*Tr*\
Karakter `traits_type`.

## <a name="remarks"></a>Açıklamalar

[İşletici<<](#basic_ostream_operator_lt_lt) aşırı yükleyen üye işlevlerin çoğu biçimlendirilmiş çıkış işlevleridir. Onlar desen izleyin:

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

Diğer iki üye işlev biçimlendirilmemiş çıkış işlevleridir. Onlar desen izleyin:

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

Her iki işlev grubu da öğeleri eklerken bir hatayla karşılaşırsa [setstate](../standard-library/basic-ios-class.md#setstate)**(badbit)** çağırır.

Sınıfın bir nesne\< basic_istream **Elem**, **Tr**> basic_ios [sınıfın](../standard-library/basic-ios-class.md)sadece sanal bir kamu taban nesnesi depolar**\<Elem**, **Tr>**.

## <a name="example"></a>Örnek

Çıktı akışları hakkında daha fazla bilgi edinmek için [basic_ofstream Sınıfı](../standard-library/basic-ofstream-class.md) örneğine bakın.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Basic_ostream](#basic_ostream)|Bir `basic_ostream` nesne inşa eder.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[flush](#flush)|Arabelleği temizler.|
|[Koymak](#put)|Bir karakteri akışa koyar.|
|[seekp](#seekp)|Çıkış akışındaki konumu sıfırlar.|
|[Nöbetçi](#sentry)|İç içe sınıf, bildirge biçimlendirilmiş çıktı işlevlerini ve biçimlendirilmemiş çıktı işlevlerini yapılaştıran bir nesneyi açıklar.|
|[Takas](#swap)|Bu `basic_ostream` nesnenin değerlerini sağlanan `basic_ostream` nesnenin değerleriyle değiştirir.|
|[tellp](#tellp)|Çıkış akışındaki konumu bildirir.|
|[Yazmak](#write)|Karakterleri bir akışa koyar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç=](#op_eq)|Sağlanan `basic_ostream` nesne parametresinin değerini bu nesneye atar.|
|[operatör<<](#basic_ostream_operator_lt_lt)|Dereye yazar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ostream>

**Ad alanı:** std

## <a name="basic_ostreambasic_ostream"></a><a name="basic_ostream"></a>basic_ostream::basic_ostream

Bir `basic_ostream` nesne inşa eder.

```cpp
explicit basic_ostream(
    basic_streambuf<Elem, Tr>* strbuf,
    bool _Isstd = false);

basic_ostream(basic_ostream&& right);
```

### <a name="parameters"></a>Parametreler

*strbuf*\
basic_streambuf türünde [bir](../standard-library/basic-streambuf-class.md)nesne.

*_Isstd*\
bu standart bir akış ise **doğrudur;** aksi takdirde, **yanlış**.

*Doğru*\
Türdeki `basic_ostream`bir nesneye rvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu [init](../standard-library/basic-ios-class.md#init)() çağırarak taban`strbuf`sınıfı başlatifleştirir. İkinci oluşturucu basic_ios çağırarak taban sınıfı başharfe [taşır::move](../standard-library/basic-ios-class.md#move)`(right)`.

### <a name="example"></a>Örnek

Çıktı akışları hakkında daha fazla bilgi edinmek için [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) örneğine bakın.

## <a name="basic_ostreamflush"></a><a name="flush"></a>basic_ostream::floş

Arabelleği temizler.

```cpp
basic_ostream<Elem, Tr>& flush();
```

### <a name="return-value"></a>Dönüş Değeri

basic_ostream nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

[Rdbuf](../standard-library/basic-ios-class.md#rdbuf) null işaretçi değilse, işlev **rdbuf->** [pubsync](../standard-library/basic-streambuf-class.md#pubsync)çağırır. Bu -1 döndürürse, işlev [setstate](../standard-library/basic-ios-class.md#setstate)**(badbit)** çağırır. ** \*Bunu**döndürür.

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

## <a name="basic_ostreamoperatorltlt"></a><a name="basic_ostream_operator_lt_lt"></a>basic_ostream::operatör&lt;&lt;

Dereye yazar.

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

*Pfn*\
Bir işlev işaretçisi.

*strbuf*\
Bir `stream_buf` nesneye işaretçi.

*Val*\
Akışa yazılması gereken bir öğe.

### <a name="return-value"></a>Dönüş Değeri

basic_ostream nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

\<Ostream> üstbilgi de birkaç genel ekleme işleci tanımlar. Daha fazla bilgi için [operatör<<](../standard-library/ostream-operators.md#op_lt_lt)bakın.

İlk üye işlev, `ostr << endl` formun bir ifadesinin [endl](../standard-library/ostream-functions.md#endl)**(ostr)** çağırır ve sonra ** \*bu**döndürür sağlar. İkinci ve üçüncü işlevler, [hex](../standard-library/ios-functions.md#hex)gibi diğer manipülatörlerin de benzer şekilde çalışmasını sağlar. Kalan işlevler biçimlendirilmiş çıkış işlevleridir.

İşlev

```cpp
basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
```

*strbuf* öğeleri *ni*stiştire, null işaretçi değilse ve ekler. Çıkarma, dosyanın sonunda durur veya bir çıkarma özel durum atarsa (yeniden atılır). Ayrıca, söz konusu öğeyi ayıklamadan, ekleme başarısız olursa durur. İşlev hiçbir öğe eklerse veya bir çıkarma özel durum atarsa, işlev [setstate](../standard-library/basic-ios-class.md#setstate)**(failbit)** çağırır. Her durumda, işlev ** \*bu**döndürür.

İşlev

```cpp
basic_ostream<Elem, Tr>& operator<<(bool val);
```

`_Val` boolean `(`alanına dönüştürür ve** elem, OutIt>\< ** [getloc)](../standard-library/ios-base-class.md#getloc)num_put [use_facet](../standard-library/basic-filebuf-class.md#open)<arayarak ekler. [koymak](#put)(**OutIt**( ** \***[rdbuf](../standard-library/basic-ios-class.md#rdbuf)), bu , `getloc` **val**). Burada, `OutIt` [ostreambuf_iterator](../standard-library/ostreambuf-iterator-class.md)**\<Elem, Tr>** olarak tanımlanır. İşlev ** \*bunu**döndürür.

Fonksiyonlar

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

her bir sayısal alana *val* dönüştürmek ve **\<elem, OutIt>**(`getloc`num_put use_facet<arayarak eklemek val . **put**(**OutIt**`rdbuf`( `getloc`), ** \*bu**, **val**). Burada, **OutIt** **ostreambuf_iterator\<Elem, Tr>** olarak tanımlanır. İşlev ** \*bunu**döndürür.

Fonksiyonlar

```cpp
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
```

her bir sayısal alana *val* dönüştürmek ve **elem num_put,\<OutIt>**(**)** use_facet<arayarak eklemek (`getloc` `getloc`**OutIt**(`rdbuf`, ** \*bu**, , val ). **val** Burada, **OutIt** **ostreambuf_iterator\<Elem, Tr>** olarak tanımlanır. İşlev ** \*bunu**döndürür.

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

## <a name="basic_ostreamoperator"></a><a name="op_eq"></a>basic_ostream::operator=

Sağlanan `basic_ostream` nesne parametresi için değerleri bu nesneye atar.

```cpp
basic_ostream& operator=(basic_ostream&& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bir `rvalue` `basic_ostream` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Üye operatör takas `(right)`çağırır.

## <a name="basic_ostreamput"></a><a name="put"></a>basic_ostream::put

Bir karakteri akışa koyar.

```cpp
basic_ostream<Elem, Tr>& put(char_type _Ch);
```

### <a name="parameters"></a>Parametreler

*_Ch*\
Bir karakter.

### <a name="return-value"></a>Dönüş Değeri

basic_ostream nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş çıkış işlevi *öğeyi _Ch*ekler. ** \*Bunu**döndürür.

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

## <a name="basic_ostreamseekp"></a><a name="seekp"></a>basic_ostream::seekp

Çıkış akışındaki konumu sıfırla.

```cpp
basic_ostream<Elem, Tr>& seekp(pos_type _Pos);

basic_ostream<Elem, Tr>& seekp(off_type _Off, ios_base::seekdir _Way);
```

### <a name="parameters"></a>Parametreler

*_Pos*\
Akıştaki konum.

*_off*\
*_Way*göreli ofset .

*_way*\
Bir [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir) sayısallaştırmalar.

### <a name="return-value"></a>Dönüş Değeri

basic_ostream nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

[Fail](../standard-library/basic-ios-class.md#fail) **yanlışsa,** ilk üye işlev bazı `pos_type` geçici nesneler `newpos`için **newpos =** [rdbuf](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)*(_Pos)* çağırır. Yanlış `fail` ise, ikinci işlev **newpos = rdbuf->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)*(_Off, _Way)* çağırır. Her iki durumda`off_type`da , eğer`off_type`( )**newpos ==** ( ((-1) (konumlandırma işlemi başarısız olursa), sonra fonksiyon **istr çağırır.** [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). Her iki işlev de ** \*bunu**döndürer.

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

## <a name="basic_ostreamsentry"></a><a name="sentry"></a>basic_ostream::nöbetçi

İç içe sınıf, bildirge biçimlendirilmiş çıktı işlevlerini ve biçimlendirilmemiş çıktı işlevlerini yapılaştıran bir nesneyi açıklar.

sınıf nöbetçi { kamu: açık\<nöbetçi(basic_ostream Elem, Tr>& _Ostr); operatör bool() const; ~sentry(); };

### <a name="remarks"></a>Açıklamalar

İç içe sınıf, bildirge biçimlendirilmiş çıktı işlevlerini ve biçimlendirilmemiş çıktı işlevlerini yapılaştıran bir nesneyi açıklar. Eğer **ostr.** [iyi](../standard-library/basic-ios-class.md#good) **doğrudur** ve **ostr.** [kravat](../standard-library/basic-ios-class.md#tie) bir null işaretçi değil, yapıcı **ostr.tie->** [floş](#flush)çağırır. Oluşturucu daha sonra döndürülen `ostr.good` `status`değeri . Bu depolanan `operator bool` değeri teslim etmek için daha sonra bir arama.

False `uncaught_exception` **false** döndürür ve [unitbuf](../standard-library/ios-functions.md#unitbuf) [bayrakları](../standard-library/ios-base-class.md#flags) **&** sıfır değilse, yıkıcı [floş](#flush)çağırır.

## <a name="basic_ostreamswap"></a><a name="swap"></a>basic_ostream::takas

Bu `basic_ostream` nesnenin değerlerini sağlanan `basic_ostream`değerlerle değiştirir.

```cpp
void swap(basic_ostream& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bir `basic_ostream` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işlev [basic_ios çağırır::bu](../standard-library/basic-ios-class.md#swap) `(right)` nesnenin içeriğini *sağ*içeriği yle değiştirmek için takas .

## <a name="basic_ostreamtellp"></a><a name="tellp"></a>basic_ostream::tellp

Çıkış akışındaki rapor konumu.

```cpp
pos_type tellp();
```

### <a name="return-value"></a>Dönüş Değeri

Çıkış akışındaki konum.

### <a name="remarks"></a>Açıklamalar

[Fail](../standard-library/basic-ios-class.md#fail) yanlışsa, üye işlev [rdbuf](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(0, `cur` **içinde)** döndürür. **false** Aksi takdirde, `pos_type`(-1) döndürür.

### <a name="example"></a>Örnek

Bkz. bir örnek `tellp`için [seekp](#seekp) kullanarak.

## <a name="basic_ostreamwrite"></a><a name="write"></a>basic_ostream::yaz

Karakterleri bir akışa koyun.

```cpp
basic_ostream<Elem, Tr>& write(const char_type* str, streamsize count);
```

### <a name="parameters"></a>Parametreler

*Sayısı*\
Akışa konur karakter sayısı.

*Str*\
Akışa koymak için karakterler.

### <a name="return-value"></a>Dönüş Değeri

basic_ostream nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

[Biçimlendirilmemiş çıkış işlevi](../standard-library/basic-ostream-class.md) *str'den*başlayan *sayı* elemanlarının sırasını ekler.

### <a name="example"></a>Örnek

Bkz. bir örnek `write`için [akış boyutu.](../standard-library/ios-typedefs.md#streamsize)

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
