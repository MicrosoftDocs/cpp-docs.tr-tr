---
title: basic_istream Sınıfı
ms.date: 11/04/2016
f1_keywords:
- istream/std::basic_istream
- istream/std::basic_istream::gcount
- istream/std::basic_istream::get
- istream/std::basic_istream::getline
- 'istream/std::basic_istream::'
- istream/std::basic_istream::peek
- istream/std::basic_istream::putback
- istream/std::basic_istream::read
- istream/std::basic_istream::readsome
- istream/std::basic_istream::seekg
- istream/std::basic_istream::sentry
- istream/std::basic_istream::swap
- istream/std::basic_istream::sync
- istream/std::basic_istream::tellg
- istream/std::basic_istream::unget
helpviewer_keywords:
- std::basic_istream [C++]
- std::basic_istream [C++], gcount
- std::basic_istream [C++], get
- std::basic_istream [C++], getline
- std::basic_istream [C++], OVERWRITE
- std::basic_istream [C++], peek
- std::basic_istream [C++], putback
- std::basic_istream [C++], read
- std::basic_istream [C++], readsome
- std::basic_istream [C++], seekg
- std::basic_istream [C++], sentry
- std::basic_istream [C++], swap
- std::basic_istream [C++], sync
- std::basic_istream [C++], tellg
- std::basic_istream [C++], unget
ms.assetid: c7c27111-de6d-42b4-95a3-a7e65259bf17
ms.openlocfilehash: 03a6e3a65d6dc8c2fa896949855bd23a01578e5a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376835"
---
# <a name="basic_istream-class"></a>basic_istream Sınıfı

Karakter özellikleri *Tr*sınıfı tarafından belirlenen , [traits_type](../standard-library/basic-ios-class.md#traits_type)olarak da bilinen, `Char_T` [char_type](../standard-library/basic-ios-class.md#char_type)olarak da bilinen , bir akış arabellesinden öğelerin ve kodlanmış nesnelerin ayıklamalarını kontrol eden bir nesneyi açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Char_T, class Tr = char_traits<Char_T>>
class basic_istream : virtual public basic_ios<Char_T, Tr>
```

## <a name="remarks"></a>Açıklamalar

[İşletici>>](#op_gt_gt) aşırı yükleyen üye işlevlerin çoğu biçimlendirilmiş giriş işlevleridir. Onlar desen izleyin:

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (ok)
{
    try
    {
        /*extract elements and convert
            accumulate flags in state.
            store a successful conversion*/
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);

return (*this);
```

Diğer birçok üye işlev, biçimlendirilmemiş giriş işlevleridir. Onlar desen izleyin:

```cpp
iostate state = goodbit;
count = 0;    // the value returned by gcount
const sentry ok(*this, true);

if (ok)
{
    try
    {
        /* extract elements and deliver
            count extracted elements in count
            accumulate flags in state */
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);
```

Her iki işlev [`setstate`](../standard-library/basic-ios-class.md#setstate) `(eofbit)` grubu da öğeleri ayıklarken dosyasonuyla karşılaştıklarında çağrı da rarar.

Sınıf `basic_istream<Char_T, Tr>` depolarının bir nesnesi:

- Sınıfın [`basic_ios`](../standard-library/basic-ios-class.md) `<Char_T, Tr>`sanal ortak taban nesnesi.

- Son biçimlendirilmemiş giriş işlemi (önceki `count` kodda adlandırılır) için bir çıkarma sayısı.

## <a name="example"></a>Örnek

Giriş akışları hakkında daha fazla bilgi edinmek için [basic_ifstream Sınıfı](../standard-library/basic-ifstream-class.md) örneğine bakın.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Basic_istream](#basic_istream)|Türünde `basic_istream`bir nesne oluşturuyor.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[gcount](#gcount)|Son biçimlendirilmemiş giriş sırasında okunan karakter sayısını verir.|
|[get](#get)|Giriş akışından bir veya daha fazla karakter okur.|
|[getline](#getline)|Giriş akışından bir satır okur.|
|[Yoksay](#ignore)|Geçerli okuma konumundan birkaç öğenin atlanınmasını neden olur.|
|[Peek](#peek)|Okunacak sonraki karakteri döndürür.|
|[putback](#putback)|Akışa belirli bir karakter koyar.|
|[Okuma](#read)|Akıştan belirli sayıda karakter okur ve bunları bir dizide saklar.|
|[readsome](#readsome)|Yalnızca arabellekten okuyun.|
|[seekg](#seekg)|Bir akışta okuma konumunu taşır.|
|[Nöbetçi](#sentry)|İç içe sınıf, bildirge biçimlendirilmiş giriş işlevlerini ve biçimlendirilmemiş giriş işlevlerini yapılaştıran bir nesneyi açıklar.|
|[Takas](#swap)|Bu `basic_istream` nesneyi sağlanan `basic_istream` nesne parametresi için değiştirir.|
|[Eşitleme](#sync)|Akış ilişkili giriş aygıtını akış arabelleğiyle eşitler.|
|[tellg](#tellg)|Akıştaki geçerli okuma konumunu bildirir.|
|[unget](#unget)|En son okunan karakteri akışına geri koyar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operatör>>](#op_gt_gt)|Giriş akışındaki bir işlevi çağırır veya giriş akışından biçimlendirilmiş verileri okur.|
|[işleç=](#op_eq)|Bu nesneye işlecinin sağ tarafında atar. `basic_istream` Bir kopyasını geride bırakmayan `rvalue` bir başvuruiçeren bir taşıma ataması.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<istream>

**Ad alanı:** std

## <a name="basic_istreambasic_istream"></a><a name="basic_istream"></a>basic_istream:basic_istream

Türünde `basic_istream`bir nesne oluşturuyor.

```cpp
explicit basic_istream(
    basic_streambuf<Char_T, Tr>* strbuf,
    bool _Isstd = false);

basic_istream(basic_istream&& right);
```

### <a name="parameters"></a>Parametreler

*strbuf*\
basic_streambuf türünde [bir](../standard-library/basic-streambuf-class.md)nesne.

*_Isstd*\
standart bir akış ise **doğrudur;** aksi takdirde, **yanlış**.

*Doğru*\
Kopyalanması gereken bir `basic_istream` nesne.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu çağırarak [`init`](../standard-library/basic-ios-class.md#init) `(strbuf)`taban sınıfı başharfe ait hale Ayrıca çıkarma sayısında sıfır depolar. Bu çıkarma sayısı hakkında daha fazla bilgi için [basic_istream Sınıfı](../standard-library/basic-istream-class.md) genel bakış Açıklamaları bölümüne bakın.

İkinci oluşturucu çağırarak `move(right)`taban sınıfı başharfe ait hale Ayrıca çıkarma `right.gcount()` sayısı nda depolar ve *sağ**' için ekstraksiyon sayısında sıfır depolar.

### <a name="example"></a>Örnek

Giriş akışları hakkında daha fazla bilgi edinmek için [basic_ifstream::basic_ifstream](../standard-library/basic-ifstream-class.md#basic_ifstream) için örneğe bakın.

## <a name="basic_istreamgcount"></a><a name="gcount"></a>basic_istream::gcount

Son biçimlendirilmemiş giriş sırasında okunan karakter sayısını verir.

```cpp
streamsize gcount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıkarma sayısı.

### <a name="remarks"></a>Açıklamalar

basic_istream kullanın::biçimlendirilmemiş karakterleri okumaya [geçin.](#get)

### <a name="example"></a>Örnek

```cpp
// basic_istream_gcount.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   cout << "Type the letter 'a': ";

   ws( cin );
   char c[10];

   cin.get( &c[0],9 );
   cout << c << endl;

   cout << cin.gcount( ) << endl;
}
```

```Input
a
```

```Output
Type the letter 'a': a
1
```

## <a name="basic_istreamget"></a><a name="get"></a>basic_istream::get

Giriş akışından bir veya daha fazla karakter okur.

```cpp
int_type get();

basic_istream<Char_T, Tr>& get(Char_T& Ch);
basic_istream<Char_T, Tr>& get(Char_T* str, streamsize count);
basic_istream<Char_T, Tr>& get(Char_T* str, streamsize count, Char_T delimiter);

basic_istream<Char_T, Tr>& get(basic_streambuf<Char_T, Tr>& strbuf);
basic_istream<Char_T, Tr>& get(basic_streambuf<Char_T, Tr>& strbuf, Char_T delimiter);
```

### <a name="parameters"></a>Parametreler

*Sayısı*\
*Strbuf'tan*okunacak karakter sayısı.

*Sınırlayıcı*\
*Sayımdan*önce karşılaşılırsa okumayı sonlandırması gereken karakter.

*Str*\
Yazılması gereken bir dize.

*Caner*\
Elde edilebis bir karakter.

*strbuf*\
Yazılması gereken bir arabellek.

### <a name="return-value"></a>Dönüş Değeri

Parametresiz get biçimi, dosyanın sonu veya sonu olarak okunan öğeyi döndürür. Kalan formlar akışı döndür (* `this`).

### <a name="remarks"></a>Açıklamalar

İlk biçimlendirilmemiş giriş işlevi, mümkünse, döndürülerek `rdbuf->sbumpc`bir öğe ayıklar. Aksi takdirde, `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof)döner. İşlev hiçbir öğeyi ayıklarsa, çağırır. [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`

İkinci [işlev, int_type](../standard-library/basic-ios-class.md#int_type) öğeyi `meta` aynı şekilde ayıklar. Eğer `meta` eşit karşılaştırırsa `traits_type::eof` `setstate(failbit)`, işlev çağırır. Aksi takdirde, `traits_type::` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) `(meta)` *Ch*depolar . İşlev __*bu__döndürür.

Üçüncü işlev `get(str, count, widen('\n'))`döndürür.

Dördüncü işlev `count - 1` öğeleri ayıklar ve *str*başında başlayan dizi onları depolar. Her zaman `char_type` depolanan herhangi bir çıkarılan elemanları sonra depolar. Test sırasına göre, çıkarma durur:

- Dosyanın sonunda.

- Fonksiyon *delimiter*eşit bir öğe ayıklar sonra . Bu durumda, öğe denetlenmeye nisken sırasına geri konur.

- Fonksiyon öğeleri ayıklar `count - 1` sonra.

İşlev hiçbir öğe yitirmezse, çağırır. `setstate(failbit)` Her durumda, __*bu__döndürür.

Beşinci işlev `get(strbuf, widen('\n'))`döndürür.

Altıncı işlev öğeleri ayıklar ve *strbuf*ekler. Ayıklama, dosya sonu veya ayıklanmayan *sınırlandırıcıile*eşit karşılaştırılan bir öğeüzerinde durur. Ayrıca, söz konusu öğeyi ayıklamadan durur, bir ekleme başarısız olursa veya bir özel durum atarsa (yakalanır ama yeniden atılmaz). İşlev hiçbir öğe yitirmezse, çağırır. `setstate(failbit)` Her durumda, işlev __*bu__döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_istream_get.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10];

   c[0] = cin.get( );
   cin.get( c[1] );
   cin.get( &c[2],3 );
   cin.get( &c[4], 4, '7' );

   cout << c << endl;
}
```

```Output
1111
```

## <a name="basic_istreamgetline"></a><a name="getline"></a>basic_istream::getline

Giriş akışından bir satır alır.

```cpp
basic_istream<Char_T, Tr>& getline(
    char_type* str,
    streamsize count);

basic_istream<Char_T, Tr>& getline(
    char_type* str,
    streamsize count,
    char_type delimiter);
```

### <a name="parameters"></a>Parametreler

*Sayısı*\
*Strbuf'tan*okunacak karakter sayısı.

*Sınırlayıcı*\
*Sayımdan*önce karşılaşılırsa okumayı sonlandırması gereken karakter.

*Str*\
Yazılması gereken bir dize.

### <a name="return-value"></a>Dönüş Değeri

Akış (__*bu__).

### <a name="remarks"></a>Açıklamalar

Bu biçimlendirilmemiş giriş işlevlerinden `getline(str, count, widen('\n'))`ilki döndürür.

İkinci işlev `count - 1` öğeleri ayıklar ve *str*başında dizi onları depolar. Her zaman depolar herhangi bir ayıklanmış öğeleri sonra dize sonlandırma karakteri depolar. Test sırasına göre, çıkarma durur:

- Dosyanın sonunda.

- Fonksiyon *delimiter*eşit bir öğe ayıklar sonra . Bu durumda, öğe geri konmadı ve denetlenen sıraya eklenmiyor.

- Fonksiyon öğeleri ayıklar `count - 1` sonra.

İşlev hiçbir öğe veya `count - 1` öğe ayıklanırsa, çağırır. [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)` Her durumda, __*bu__döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_istream_getline.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10];

   cin.getline( &c[0], 5, '2' );
   cout << c << endl;
}
```

```Output
121
```

## <a name="basic_istreamignore"></a><a name="ignore"></a>basic_istream::yoksay

Geçerli okuma konumundan birkaç öğenin atlanınmasını neden olur.

```cpp
basic_istream<Char_T, Tr>& ignore(
    streamsize count = 1,
    int_type delimiter = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*Sayısı*\
Geçerli okuma konumundan atlayacak öğe sayısı.

*Sınırlayıcı*\
Sayımdan önce karşılaşılan öğe, `ignore` *delimiter'dan* sonraki tüm öğelerin döndürülmesine ve okunmasına izin verilmesine neden olur.

### <a name="return-value"></a>Dönüş Değeri

Akış (__*bu__).

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş giriş işlevi öğeleri *saymak* için ayıklar ve bunları atar. *Ancak,* sayım `numeric_limits<int>::max`eşitse, rasgele büyük olarak alınır. Ayıklama, dosyanın sonunda veya `Ch` `traits_type::` [`to_int_type`](../standard-library/char-traits-struct.md#to_int_type) `(Ch)` *delimiter* ile eşit (aynı zamanda ayıklanır) ile karşılaştırılan bir öğeüzerinde durur. İşlev __*bu__döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_istream_ignore.cpp
// compile with: /EHsc
#include <iostream>
int main( )
{
   using namespace std;
   char chararray[10];
   cout << "Type 'abcdef': ";
   cin.ignore( 5, 'c' );
   cin >> chararray;
   cout << chararray;
}
```

```Output
Type 'abcdef': abcdef
def
```

## <a name="basic_istreamoperator"></a><a name="op_gt_gt"></a>temel\_istream::operatör>>

Giriş akışındaki bir işlevi çağırır veya giriş akışından biçimlendirilmiş verileri okur.

```cpp
basic_istream& operator>>(basic_istream& (* Pfn)(basic_istream&));
basic_istream& operator>>(ios_base& (* Pfn)(ios_base&));
basic_istream& operator>>(basic_ios<Char_T, Tr>& (* Pfn)(basic_ios<Char_T, Tr>&));
basic_istream& operator>>(basic_streambuf<Char_T, Tr>* strbuf);
basic_istream& operator>>(bool& val);
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val);
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val);
basic_istream& operator>>(void *& val);
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```

### <a name="parameters"></a>Parametreler

*Pfn*\
Bir işlev işaretçisi.

*strbuf*\
`stream_buf` türünün bir nesnesi.

*Val*\
Akıştan okunacak değer.

### <a name="return-value"></a>Dönüş Değeri

Akış (__*bu__).

### <a name="remarks"></a>Açıklamalar

\<istream> üstbilgi de birkaç global çıkarma işleci tanımlar. Daha fazla bilgi için [operatör>> \<(istream>)](../standard-library/istream-operators.md#op_gt_gt)bakın.

İlk üye işlev, `istr >> ws` formun bir ifadesinin çağrılmasını [`ws`](../standard-library/istream-functions.md#ws) `(istr)`ve sonra __*bu'yu__döndürmesini sağlar. İkinci ve üçüncü işlevler, diğer [`hex`](../standard-library/ios-functions.md#hex)manipülatörlerin de benzer şekilde çalışmasını sağlar. Kalan işlevler biçimlendirilmiş giriş işlevleridir.

İşlev:

```cpp
basic_istream& operator>>(
    basic_streambuf<Char_T, Tr>* strbuf);
```

*strbuf* null işaretçi değilse öğeleri ayıklar ve *strbuf*ekler. Ayıklama dosyanın sonunda durur. Ayrıca, bir ekleme başarısız olursa veya bir özel durum atar (yakalanır ama yeniden atılmaz) söz konusu öğeyi ayıklamadan durur. İşlev hiçbir öğe yitirmezse, çağırır. [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)` Her durumda, işlev __*bu__döndürür.

İşlev:

```cpp
basic_istream& operator>>(bool& val);
```

bir [`use_facet`](../standard-library/basic-filebuf-class.md#open) `< num_get<Char_T, InIt>(` [`getloc`](../standard-library/ios-base-class.md#getloc) `).` [`get`](../standard-library/ios-base-class.md#getloc) `( InIt(` [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf)alanı ayıklar ve arayarak `), Init(0), *this, getloc, val)`boolean değerine dönüştürür. Burada, `InIt` olarak [`istreambuf_iterator`](../standard-library/istreambuf-iterator-class.md) `<Char_T, Tr>`tanımlanır. İşlev __*bu__döndürür.

Fonksiyonların her biri:

```cpp
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val);
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val);
basic_istream& operator>>(void *& val);
```

bir alanı ayıklayın ve arayarak `use_facet<num_get<Char_T, InIt>(getloc).` [`get`](#get) `(InIt(rdbuf), Init(0), *this, getloc, val)`sayısal bir değere dönüştürün. Burada, `InIt` olarak `istreambuf_iterator<Char_T, Tr>`tanımlanır , ve *val* türü **uzun,** **imzasız uzun**, ya da gerektiğinde **geçersiz.** <strong>\*</strong>

Dönüştürülen değer *val*türü olarak temsil edilenemezse, [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`işlev çağırır. Her durumda, işlev __*bu__döndürür.

Fonksiyonların her biri:

```cpp
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```

bir alanı ayıklayın ve arayarak `use_facet<num_get<Char_T, InIt>(getloc).get(InIt(rdbuf), Init(0), *this, getloc, val)`sayısal bir değere dönüştürün. Burada, `InIt` `istreambuf_iterator<Char_T, Tr>`olarak tanımlanır , ve *val* türü **çift** veya **uzun çift** gerektiği gibi vardır.

Dönüştürülen değer *val*türü olarak temsil edilenemezse, `setstate(failbit)`işlev çağırır. Her durumda, __*bu__döndürür.

### <a name="example"></a>Örnek

```cpp
// istream_basic_istream_op_is.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

ios_base& hex2( ios_base& ib )
{
   ib.unsetf( ios_base::dec );
   ib.setf( ios_base::hex );
   return ib;
}

basic_istream<char, char_traits<char> >& somefunc(basic_istream<char, char_traits<char> > &i)
{
   if ( i == cin )
   {
      cerr << "i is cin" << endl;
   }
   return i;
}

int main( )
{
   int i = 0;
   cin >> somefunc;
   cin >> i;
   cout << i << endl;
   cin >> hex2;
   cin >> i;
   cout << i << endl;
}
```

## <a name="basic_istreamoperator"></a><a name="op_eq"></a>basic_istream::operator=

Bu nesneye işlecinin sağ tarafında atar. `basic_istream` Bir kopyasını geride bırakmayan `rvalue` bir başvuruiçeren bir taşıma ataması.

```cpp
basic_istream& operator=(basic_istream&& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bir `rvalue` `basic_ifstream` nesneye başvuru.

### <a name="return-value"></a>Dönüş Değeri

*Bu' nun __iadesi.__

### <a name="remarks"></a>Açıklamalar

Üye operatör `swap(right)`çağırır.

## <a name="basic_istreampeek"></a><a name="peek"></a>basic_istream::peek

Okunacak sonraki karakteri döndürür.

```cpp
int_type peek();
```

### <a name="return-value"></a>Dönüş Değeri

Okunacak bir sonraki karakter.

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş giriş işlevi, mümkünse bir öğeyi döndürerek ayıklar. `rdbuf->` [`sgetc`](../standard-library/basic-streambuf-class.md#sgetc) Aksi takdirde, `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof)döner.

### <a name="example"></a>Örnek

```cpp
// basic_istream_peek.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2;
   cout << "Type 'abcde': ";

   c2 = cin.peek( );
   cin.getline( &c[0], 9 );

   cout << c2 << " " << c << endl;
}
```

```Input
abcde
```

```Output
Type 'abcde': abcde
a abcde
```

## <a name="basic_istreamputback"></a><a name="putback"></a>basic_istream::putback

Akışa belirli bir karakter koyar.

```cpp
basic_istream<Char_T, Tr>& putback(
    char_type Ch);
```

### <a name="parameters"></a>Parametreler

*Caner*\
Akışına geri koymak için bir karakter.

### <a name="return-value"></a>Dönüş Değeri

Akış (__*bu__).

### <a name="remarks"></a>Açıklamalar

[Biçimlendirilmemiş giriş işlevi](../standard-library/basic-istream-class.md) *ch*geri koyar , mümkünse, sanki arayarak [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) `->` [`sputbackc`](../standard-library/basic-streambuf-class.md#sputbackc). Null `rdbuf` işaretçisi ise veya `sputbackc` çağrı `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof)dönerse, [`setstate`](../standard-library/basic-ios-class.md#setstate) `(badbit)`işlev çağırır. Her durumda, __*bu__döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_istream_putback.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2, c3;

   c2 = cin.get( );
   c3 = cin.get( );
   cin.putback( c2 );
   cin.getline( &c[0], 9 );
   cout << c << endl;
}
```

```Output
qwq
```

## <a name="basic_istreamread"></a><a name="read"></a>basic_istream::oku

Akıştan belirli sayıda karakter okur ve bunları bir dizide saklar.

Geçirilen değerlerin doğru olup olmadığını denetlemek için arayana güvendiğiiçin, bu yöntem güvenli olmayabilir.

```cpp
basic_istream<Char_T, Tr>& read(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*Str*\
Karakterleri okumak için dizi.

*Sayısı*\
Okunacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Akarsu ( `*this`).

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş giriş işlevi öğeleri *saymak* için ayıklar ve *str*başında başlayan dizi depolar. Ayıklama dosyanın sonunda erken durur, bu [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`durumda işlev çağırır. Her durumda, __*bu__döndürür.

### <a name="example"></a>Örnek

```cpp
// basic_istream_read.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main()
{
    char c[10];
    int count = 5;

    cout << "Type 'abcde': ";

    // Note: cin::read is potentially unsafe, consider
    // using cin::_Read_s instead.
    cin.read(&c[0], count);
    c[count] = 0;

    cout << c << endl;
}
```

```Input
abcde
```

```Output
Type 'abcde': abcde
abcde
```

## <a name="basic_istreamreadsome"></a><a name="readsome"></a>basic_istream::readsome

Belirtilen karakter değerlerini okur.

Geçirilen değerlerin doğru olup olmadığını denetlemek için arayana güvendiğiiçin, bu yöntem güvenli olmayabilir.

```cpp
streamsize readsome(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*Str*\
Okuduğu karakterleri `readsome` depolayan dizi.

*Sayısı*\
Okunacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Karakterlerin sayısı gerçekten okumak, [`gcount`](#gcount).

### <a name="remarks"></a>Açıklamalar

Bu biçimlendirilmemiş giriş işlevi, giriş akışındaki öğeleri *saymak* için ayıklar ve bunları dizi *str'de*depolar.

Bu işlev giriş için beklemez. Mevcut verileri okur.

### <a name="example"></a>Örnek

```cpp
// basic_istream_readsome.cpp
// compile with: /EHsc /W3
#include <iostream>
using namespace std;

int main( )
{
   char c[10];
   int count = 5;

   cout << "Type 'abcdefgh': ";

   // cin.read blocks until user types input.
   // Note: cin::read is potentially unsafe, consider
   // using cin::_Read_s instead.
   cin.read(&c[0], 2);

   // Note: cin::readsome is potentially unsafe, consider
   // using cin::_Readsome_s instead.
   int n = cin.readsome(&c[0], count);  // C4996
   c[n] = 0;
   cout << n << " characters read" << endl;
   cout << c << endl;
}
```

## <a name="basic_istreamseekg"></a><a name="seekg"></a>basic_istream::seekg

Bir akışta okuma konumunu taşır.

```cpp
basic_istream<Char_T, Tr>& seekg(pos_type pos);

basic_istream<Char_T, Tr>& seekg(off_type off, ios_base::seekdir way);
```

### <a name="parameters"></a>Parametreler

*Pos*\
Okuma işaretçisini hareket ettirecek mutlak konum.

*kapalı*\
Okuma işaretçisini *göreli şekilde*taşımak için bir ofset .

*Yol*\
Bir [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir) sayısallaştırmalar.

### <a name="return-value"></a>Dönüş Değeri

Akış (__*bu__).

### <a name="remarks"></a>Açıklamalar

İlk üye işlev mutlak bir arama gerçekleştirir, ikinci üye işlev göreli bir arama gerçekleştirir.

> [!NOTE]
> Standart C++ metin dosyalarındaki göreli arayı desteklemediği için metin dosyalarıyla ikinci üye işlevini kullanmayın.

Yanlışsa, [`fail`](../standard-library/basic-ios-class.md#fail) ilk üye `newpos =` [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) `->` [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos) `(pos)`işlev bazı `pos_type` geçici `newpos`nesne için çağırır. Yanlışsa, `fail` ikinci işlev `newpos = rdbuf->` [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) `( off, way)`çağırır. Her iki durumda `(off_type)newpos == (off_type)(-1)` da, (konumlandırma işlemi başarısız `istr.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`olursa), işlev çağırır. Her iki işlev __de *this'i__döndürer.

Doğruysa, [`fail`](../standard-library/basic-ios-class.md#fail) üye işlevler hiçbir şey yapmaz.

### <a name="example"></a>Örnek

```cpp
// basic_istream_seekg.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
   using namespace std;
   ifstream file;
   char c, c1;

   file.open( "basic_istream_seekg.txt" );
   file.seekg(2);   // seek to position 2
   file >> c;
   cout << c << endl;
}
```

## <a name="basic_istreamsentry"></a><a name="sentry"></a>basic_istream::nöbetçi

İç içe sınıf, bildirge biçimlendirilmiş ve biçimlendirilmemiş giriş işlevlerini yapılaştıran bir nesneyi açıklar.

```cpp
class sentry {
   public:
   explicit sentry(
      basic_istream<Char_T, Tr>& _Istr,
      bool _Noskip = false);
   operator bool() const;
   };
```

### <a name="remarks"></a>Açıklamalar

Doğruysa, `_Istr.` [`good`](../standard-library/basic-ios-class.md#good) yapıcı:

- Null `_Istr.` [`tie`](../standard-library/basic-ios-class.md#tie) `->` [`flush`](../standard-library/basic-ostream-class.md#flush) `_Istr.tie` işaretçi değilse aramalar.

- Sıfır değilse [`ws`](../standard-library/istream-functions.md#ws) `(_Istr)` `_Istr.` [`flags`](../standard-library/ios-base-class.md#flags) `&` [`skipws`](../standard-library/ios-functions.md#skipws) etkili bir şekilde çağırır.

Böyle bir hazırlıktan `_Istr.good` sonra, yanlış ise, yapıcı çağırır `_Istr.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`. Her durumda, oluşturucu tarafından `_Istr.good` döndürülen `status`değeri depolar. Bu depolanan `operator bool` değeri teslim etmek için daha sonra bir arama.

## <a name="basic_istreamswap"></a><a name="swap"></a>basic_istream::takas

İki `basic_istream` nesnenin içeriğini değiştirir.

```cpp
void swap(basic_istream& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bir `basic_istream` nesneye bir lvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

Üye işlev [`basic_ios::swap`](../standard-library/basic-ios-class.md#swap) `(right)`çağırır. Ayrıca, çıkarma sayısını *sağ*için çıkarma sayısıyla değiştirir.

## <a name="basic_istreamsync"></a><a name="sync"></a>basic_istream::senkronize

Akış ilişkili giriş aygıtını akış arabelleğiyle eşitler.

```cpp
int sync();
```

### <a name="return-value"></a>Dönüş Değeri

Null [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) işaretçiise, işlev -1 döndürür. Aksi takdirde, `rdbuf->` [`pubsync`](../standard-library/basic-streambuf-class.md#pubsync)çağırır . Bu çağrı -1 döndürürse, işlev çağırır [`setstate`](../standard-library/basic-ios-class.md#setstate) `(badbit)` ve -1 döndürür. Aksi takdirde, işlev sıfır döndürür.

## <a name="basic_istreamtellg"></a><a name="tellg"></a>basic_istream::tellg

Akıştaki geçerli okuma konumunu bildirir.

```cpp
pos_type tellg();
```

### <a name="return-value"></a>Dönüş Değeri

Akıştaki geçerli konum.

### <a name="remarks"></a>Açıklamalar

Yanlışsa, [`fail`](../standard-library/basic-ios-class.md#fail) üye işlev [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) `->` [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) `(0, cur, in)`döndürür. Aksi takdirde, `pos_type(-1)`döner.

### <a name="example"></a>Örnek

```cpp
// basic_istream_tellg.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main()
{
    using namespace std;
    ifstream file;
    char c;
    streamoff i;

    file.open("basic_istream_tellg.txt");
    i = file.tellg();
    file >> c;
    cout << c << " " << i << endl;

    i = file.tellg();
    file >> c;
    cout << c << " " << i << endl;
}
```

## <a name="basic_istreamunget"></a><a name="unget"></a>basic_istream::unget

En son okunan karakteri akışına geri koyar.

```cpp
basic_istream<Char_T, Tr>& unget();
```

### <a name="return-value"></a>Dönüş Değeri

Akış (__*bu__).

### <a name="remarks"></a>Açıklamalar

[Biçimlendirilmemiş giriş işlevi,](../standard-library/basic-istream-class.md) mümkünse, akışın önceki öğesini `rdbuf->` [`sungetc`](../standard-library/basic-streambuf-class.md#sungetc)arayarak geri koyar. Null [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) işaretçisi ise veya `sungetc` çağrı `traits_type::` [`eof`](../standard-library/basic-ios-class.md#eof)dönerse, [`setstate`](../standard-library/basic-ios-class.md#setstate) `(badbit)`işlev çağırır. Her durumda, __*bu__döndürür.

Nasıl `unget` başarısız olabileceği hakkında [`basic_streambuf::sungetc`](../standard-library/basic-streambuf-class.md#sungetc)bilgi için bkz.

### <a name="example"></a>Örnek

```cpp
// basic_istream_unget.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2;

   cout << "Type 'abc': ";
   c2 = cin.get( );
   cin.unget( );
   cin.getline( &c[0], 9 );
   cout << c << endl;
}
```

```Input
abc
```

```Output
Type 'abc': abc
abc
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
