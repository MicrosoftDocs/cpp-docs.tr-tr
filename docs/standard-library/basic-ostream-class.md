---
title: basic_ostream Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: dce4911bd4b7abe6c73551d6a0b178d9b2700dbb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543643"
---
# <a name="basicostream-class"></a>basic_ostream Sınıfı

Bu şablon sınıfının bir akış arabelleğine türünde öğeler ile öğe ekleme denetleyen bir nesne ve kodlanmış nesneleri açıklar `Elem`olarak da bilinen [char_type](../standard-library/basic-ios-class.md#char_type), olan karakter nitelikleri sınıfı tarafından belirlenir `Tr`olarak da bilinen [traits_type](../standard-library/basic-ios-class.md#traits_type).

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ostream : virtual public basic_ios<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Elem*<br/>
A `char_type`.

*tr*<br/>
Karakter `traits_type`.

## <a name="remarks"></a>Açıklamalar

Birçok üye işlevleri aşırı yükleyen [işleci <<](#op_lt_lt) biçimlendirilmiş çıktı işlevlerdir. Bunlar desenini izler:

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

Diğer iki üye işlevleri biçimlendirilmemiş çıkış işlevlerdir. Bunlar desenini izler:

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

İşlev çağrısının her ikisinde [setstate](../standard-library/basic-ios-class.md#setstate)(**badbit**) öğeleri eklenirken bir hata karşılaşmaları durumunda.

Basic_istream sınıfı bir nesnenin\< **Elem**, **Tr**> yalnızca sanal genel taban sınıfından bir nesne depolar [basic_ios](../standard-library/basic-ios-class.md)  **\<Elem**, **Tr >**.

## <a name="example"></a>Örnek

Örneğin bakın [basic_ofstream sınıfı](../standard-library/basic-ofstream-class.md) çıkış akışları hakkında daha fazla bilgi edinmek için.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_ostream](#basic_ostream)|Oluşturur bir `basic_ostream` nesne.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Temizleme](#flush)|Arabelleği temizler.|
|[yerleştirme](#put)|Bir akışa bir karakter koyar.|
|[seekp](#seekp)|Çıkış akışına konuma sıfırlar.|
|[sentry](#sentry)|İç içe geçmiş sınıf, biçimlendirilmiş çıkış işlevleri ve biçimlendirilmemiş çıkış işlevleri, bildirimi yapıları bir nesneyi tanımlar.|
|[değiştirme](#op_eq)|Bu değeri birbiriyle değiştirir `basic_ostream` sağlanan olanlar için nesne `basic_ostream` nesne.|
|[tellp](#tellp)|Çıkış akışına raporları konumu.|
|[write](#write)|Karakter, bir akışa koyar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#basic_ostream_operator_eq)|Sağlanan değeri atar `basic_ostream` parametresi bu nesne için nesne.|
|[işleç <<](#basic_ostream_operator_lt_lt)|Akışa yazar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ostream >

**Namespace:** std

## <a name="basic_ostream"></a>  basic_ostream::basic_ostream

Oluşturur bir `basic_ostream` nesne.

```cpp
explicit basic_ostream(
    basic_streambuf<Elem, Tr>* strbuf,
    bool _Isstd = false);

basic_ostream(basic_ostream&& right);
```

### <a name="parameters"></a>Parametreler

*strbuf*<br/>
Bir nesne türü [basic_streambuf](../standard-library/basic-streambuf-class.md).

*_Isstd*<br/>
**doğru** bir standart akışa; bu ise, aksi takdirde, **false**.

*sağ*<br/>
Türü bir nesneye bir rvalue başvurusuna `basic_ostream`.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu çağırarak temel sınıfı başlatır [init](../standard-library/basic-ios-class.md#init)(`strbuf`). İkinci oluşturucu çağırarak temel sınıfı başlatır [basic_ios::move](../standard-library/basic-ios-class.md#move)`(right)`.

### <a name="example"></a>Örnek

Örneğin bakın [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) çıkış akışları hakkında daha fazla bilgi edinmek için.

## <a name="flush"></a>  basic_ostream::flush

Arabelleği temizler.

```cpp
basic_ostream<Elem, Tr>& flush();
```

### <a name="return-value"></a>Dönüş Değeri

Basic_ostream nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsa [rdbuf](../standard-library/basic-ios-class.md#rdbuf) null işaretçisiyse, işlev çağrıları değil **rdbuf ->**[pubsync](../standard-library/basic-streambuf-class.md#pubsync). -1 döndürür, işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)(**badbit**). Döndürür  **\*bu**.

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

## <a name="basic_ostream_operator_lt_lt"></a>  basic_ostream::operator&lt;&lt;

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

*pfn*<br/>
Bir işlev işaretçisi.

*strbuf*<br/>
Bir işaretçi bir `stream_buf` nesne.

*VAL*<br/>
Akışa yazmak için bir öğe.

### <a name="return-value"></a>Dönüş Değeri

Basic_ostream nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

\<Ostream > Üstbilgi ayrıca çeşitli genel ekleme işleçlerini tanımlar. Daha fazla bilgi için [işleci <<](../standard-library/ostream-operators.md#op_lt_lt).

İlk üye işlevi bir ifade biçiminde sağlar `ostr << endl` çağrıları [endl](../standard-library/ostream-functions.md#endl)**(ostr)** ve sonra  **\*bu**. İkinci ve üçüncü oluşturucular gibi diğer manipülatörleri olun [onaltılık](../standard-library/ios-functions.md#hex), benzer şekilde davranır. Kalan tüm biçimlendirilmiş çıkış işlevleri işlevlerdir.

İşlevi

```cpp
basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
```

öğeleri ayıklar *strbuf*, *strbuf* null bir işaretçi değil ve bunları ekler. Ayıklama dosya, durdurur veya bir ayıklama (hangi fırlatılan) bir özel durum oluşturursa. Bu ayrıca, bir ekleme başarısız olursa, söz konusu öğeyi ayıklamadan durdurur. İşlev hiçbir öğe ekler veya bir ayıklama bir özel durum oluşturursa, işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). Herhangi bir durumda, işlev döndürür  **\*bu**.

İşlevi

```cpp
basic_ostream<Elem, Tr>& operator<<(bool val);
```

dönüştürür `_Val` çağırarak ekler ve bir Boole değeri alan [use_facet](../standard-library/basic-filebuf-class.md#open)**< num_put\<Elem, OutIt >**`(`[getloc](../standard-library/ios-base-class.md#getloc)). [PUT](#put)(**OutIt**([rdbuf](../standard-library/basic-ios-class.md#rdbuf)),  **\*bu**, `getloc`, **val**). Burada, `OutIt` olarak tanımlanan [ostreambuf_iterator](../standard-library/ostreambuf-iterator-class.md)**\<Elem, Tr >**. İşlev döndürür  **\*bu**.

İşlevleri

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

Her dönüştürme *val* bir sayısal alan ve çağırarak Ekle **use_facet < num_put\<Elem, OutIt >**(`getloc`). **PUT**(**OutIt**(`rdbuf`),  **\*bu**, `getloc`, **val**). Burada, **OutIt** olarak tanımlanan **ostreambuf_iterator\<Elem, Tr >**. İşlev döndürür  **\*bu**.

İşlevleri

```cpp
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
```

Her dönüştürme *val* bir sayısal alan ve çağırarak Ekle **use_facet < num_put\<Elem, OutIt >**(`getloc`)**. yerleştirme**(**OutIt**(`rdbuf`),  **\*bu**, `getloc`, **val**). Burada, **OutIt** olarak tanımlanan **ostreambuf_iterator\<Elem, Tr >**. İşlev döndürür  **\*bu**.

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

## <a name="op_eq"></a>  basic_ostream::operator =

Sağlanan değerleri atar `basic_ostream` parametresi bu nesne için nesne.

```cpp
basic_ostream& operator=(basic_ostream&& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bir `rvalue` başvurusu bir `basic_ostream` nesne.

### <a name="remarks"></a>Açıklamalar

Üye işleci çağırır takas `(right)`.

## <a name="put"></a>  basic_ostream::Put

Bir akışa bir karakter koyar.

```cpp
basic_ostream<Elem, Tr>& put(char_type _Ch);
```

### <a name="parameters"></a>Parametreler

*_Ch*<br/>
Bir karakter.

### <a name="return-value"></a>Dönüş Değeri

Basic_ostream nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Öğe biçimlendirilmemiş çıkış işlevi ekler *_Ch*. Döndürür  **\*bu**.

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

## <a name="seekp"></a>  basic_ostream::seekp

Çıkış akışına bir konumda sıfırlayın.

```cpp
basic_ostream<Elem, Tr>& seekp(pos_type _Pos);

basic_ostream<Elem, Tr>& seekp(off_type _Off, ios_base::seekdir _Way);
```

### <a name="parameters"></a>Parametreler

*_Pos*<br/>
Akışta konumu.

*_Off*<br/>
Göreli uzaklık *_Way*.

*_Way*<br/>
Aşağıdakilerden birini [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir) numaralandırma.

### <a name="return-value"></a>Dönüş Değeri

Basic_ostream nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsa [başarısız](../standard-library/basic-ios-class.md#fail) olduğu **false**, ilk üye işlev çağrıları **newpos =** [rdbuf](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)(*_Pos*), bazı `pos_type` geçici nesne `newpos`. Varsa `fail` yanlışsa, ikinci işlev çağrıları **newpos rdbuf-= >** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(*_Off, _Way*). Her iki durumda da, (`off_type`)**newpos ==** (`off_type`)(-1) (yerleştirme işlemi başarısız oldu) ve ardından işlev çağrıları **istr.** [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). Her iki işlev dönüş  **\*bu**.

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

## <a name="sentry"></a>  basic_ostream::sentry

İç içe geçmiş sınıf, biçimlendirilmiş çıkış işlevleri ve biçimlendirilmemiş çıkış işlevleri, bildirimi yapıları bir nesneyi tanımlar.

sınıf sentry {public: açık sentry (basic_ostream\<Elem, Tr > & _Ostr); operator bool() const; ~ sentry();};

### <a name="remarks"></a>Açıklamalar

İç içe geçmiş sınıf, biçimlendirilmiş çıkış işlevleri ve biçimlendirilmemiş çıkış işlevleri, bildirimi yapıları bir nesneyi tanımlar. Varsa **ostr.** [iyi](../standard-library/basic-ios-class.md#good) olduğu **true** ve **ostr.** [tie](../standard-library/basic-ios-class.md#tie) bir null işaretçiyse, oluşturucu çağrıları değil **ostr.tie ->**[Temizleme](#flush). Oluşturucu tarafından döndürülen değeri, ardından depolar `ostr.good` içinde `status`. Bir sonraki çağrı `operator bool` bu depolanan değer sunar.

Varsa `uncaught_exception` döndürür **false** ve [bayrakları](../standard-library/ios-base-class.md#flags) **&** [unitbuf](../standard-library/ios-functions.md#unitbuf) sıfır değilse, yıkıcı çağrıları [Temizleme](#flush).

## <a name="swap"></a>  basic_ostream::Swap

Bu değeri birbiriyle değiştirir `basic_ostream` değerlerinin sağlanan nesnenin `basic_ostream`.

```cpp
void swap(basic_ostream& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bir başvuru bir `basic_ostream` nesne.

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrıları [basic_ios::swap](../standard-library/basic-ios-class.md#swap) `(right)` içeriğini bu nesnenin içeriğini alışverişi *doğru*.

## <a name="tellp"></a>  basic_ostream::tellp

Çıkış akışına rapor konumu.

```cpp
pos_type tellp();
```

### <a name="return-value"></a>Dönüş Değeri

Çıkış akışına konumu.

### <a name="remarks"></a>Açıklamalar

Varsa [başarısız](../standard-library/basic-ios-class.md#fail) olduğu **false**, üye işlevinin döndürdüğü [rdbuf](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) (0, `cur`, **içinde**). Aksi halde `pos_type`(-1).

### <a name="example"></a>Örnek

Bkz: [seekp](#seekp) bir örnek için `tellp`.

## <a name="write"></a>  basic_ostream::Write

Karakter, bir akışa yerleştirin.

```cpp
basic_ostream<Elem, Tr>& write(const char_type* str, streamsize count);
```

### <a name="parameters"></a>Parametreler

*Sayısı*<br/>
Akışa koymak karakter sayısı.

*str*<br/>
Akışa koymak için karakter.

### <a name="return-value"></a>Dönüş Değeri

Basic_ostream nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

[Biçimlendirilmemiş çıkış işlevi](../standard-library/basic-ostream-class.md) dizisini ekler *sayısı* konumunda başlayan öğeleri *str*.

### <a name="example"></a>Örnek

Bkz: [streamsize](../standard-library/ios-typedefs.md#streamsize) bir örnek için `write`.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
