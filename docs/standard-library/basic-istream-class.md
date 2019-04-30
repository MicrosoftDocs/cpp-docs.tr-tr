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
ms.openlocfilehash: 5e7f6ae0728a7d28af1992cf4186d533f1a97330
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414171"
---
# <a name="basicistream-class"></a>basic_istream Sınıfı

Öğelerin ayıklama denetleyen bir nesne ve bir Akış Arabellek türü öğeler ile kodlanmış nesnelerden açıklar `Elem`olarak da bilinen [char_type](../standard-library/basic-ios-class.md#char_type), olan karakter nitelikleri sınıfı tarafından belirlenen *Tr* olarak da bilinen [traits_type](../standard-library/basic-ios-class.md#traits_type).

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_istream : virtual public basic_ios<Elem, Tr>
```

## <a name="remarks"></a>Açıklamalar

Birçok üye işlevleri aşırı yükleyen [işleci >>](#op_gt_gt) giriş işlevleri biçimlendirilir. Bunlar desenini izler:

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

Diğer birçok üye işlevleri biçimlendirilmemiş giriş işlevlerdir. Bunlar desenini izler:

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

İşlev çağrısının her ikisinde [setstate](../standard-library/basic-ios-class.md#setstate)(`eofbit`) öğeleri ayıklanırken dosya sonu karşılaşmaları durumunda.

Sınıfın bir nesnesi `basic_istream` <  `Elem`, *Tr*> depolar:

- Sanal genel taban sınıfından bir nesne [basic_ios](../standard-library/basic-ios-class.md)< `Elem`, *Tr*> `.`

- Son biçimlendirilmemiş giriş işlemi için bir çıkarma sayısı (adlı `count` önceki kodda).

## <a name="example"></a>Örnek

Örneğin bakın [basic_ifstream sınıfı](../standard-library/basic-ifstream-class.md) giriş akışları hakkında daha fazla bilgi edinmek için.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_istream](#basic_istream)|Türünde bir nesne oluşturur `basic_istream`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[gcount](#gcount)|Döndürür son biçimlendirilmemiş giriş sırasında okunan karakter sayısı.|
|[get](#get)|Bir veya daha fazla karakter, giriş akışından okur.|
|[getline](#getline)|Bir satır, giriş akışından okur.|
|[Yoksay](#ignore)|Bir dizi okuyun konum geçerli atlanacak öğe neden olur.|
|[göz atma](#peek)|Okunacak sonraki karakteri döndürür.|
|[putback](#putback)|Belirtilen bir karakter akışı halinde yerleştirir.|
|[read](#read)|Belirtilen sayıda karakteri akıştan okur ve bunları bir dizide saklar.|
|[readsome](#readsome)|Yalnızca arabelleğinden okuyun.|
|[seekg](#seekg)|Bir akış okuma konumuna taşır.|
|[sentry](#sentry)|İç içe geçmiş sınıf, biçimlendirilmiş girdi işlevleri ve biçimlendirilmemiş giriş İşlevler, bildirim yapıları bir nesneyi tanımlar.|
|[değiştirme](#swap)|Bu birbiriyle değiştirir `basic_istream` için sağlanan nesne `basic_istream` parametresi nesne.|
|[Eşitleme](#sync)|Akışın arabelleği ile stream ile ilişkili giriş cihazının eşitler.|
|[tellg](#tellg)|Akışta konumu geçerli okuma bildirir.|
|[unget](#unget)|Puts karakter akışı halinde en son okuyun.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[İşleç >>](#op_gt_gt)|Giriş akışında bir işlev çağırır veya biçimlendirilmiş veri giriş akışından okur.|
|[operator=](#op_eq)|Atar `basic_istream` bu nesneye işlecinin sağ tarafında. Bu, bir taşıma ataması ilgili bir `rvalue` kopyasını bırakmaz arkasında başvuru.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<istream >

**Namespace:** std

## <a name="basic_istream"></a>  basic_istream::basic_istream

Türünde bir nesne oluşturur `basic_istream`.

```cpp
explicit basic_istream(
    basic_streambuf<Elem, Tr>* strbuf,
    bool _Isstd = false);

basic_istream(basic_istream&& right);
```

### <a name="parameters"></a>Parametreler

*strbuf*<br/>
Bir nesne türü [basic_streambuf](../standard-library/basic-streambuf-class.md).

*_Isstd*<br/>
**doğru** bir standart akışa; bu ise, aksi takdirde, **false**.

*sağ*<br/>
A `basic_istream` kopyalanacak nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu çağırarak temel sınıfı başlatır [init](../standard-library/basic-ios-class.md#init)(_Yanları `trbuf`). Ayrıca, ayıklama sayısı sıfır depolar. Bu ayıklama sayısı hakkında daha fazla bilgi için bkz. Açıklamalar bölümüne [basic_istream sınıfı](../standard-library/basic-istream-class.md) genel bakış konusu.

İkinci oluşturucu çağırarak temel sınıfı başlatır `move( right)`. Ayrıca _R depolar `ight.gcount()` ayıklama sayısı ve sıfır ayıklama sayısı için depoları _R `ight`.

### <a name="example"></a>Örnek

Örneğin bakın [basic_ifstream::basic_ifstream](../standard-library/basic-ifstream-class.md#basic_ifstream) giriş akışları hakkında daha fazla bilgi edinmek için.

## <a name="gcount"></a>  basic_istream::gcount

Döndürür son biçimlendirilmemiş giriş sırasında okunan karakter sayısı.

```cpp
streamsize gcount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayıklama sayısı.

### <a name="remarks"></a>Açıklamalar

Kullanım [basic_istream::get](#get) biçimlendirilmemiş karakterleri okumak için.

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

## <a name="get"></a>  basic_istream::get

Bir veya daha fazla karakter, giriş akışından okur.

```cpp
int_type get();

basic_istream<Elem, Tr>& get(Elem& Ch);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count, Elem Delim);

basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf);
basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf, Elem Delim);
```

### <a name="parameters"></a>Parametreler

*Sayısı*<br/>
Okunacak karakter sayısını `strbuf`.

*Delim*<br/>
Önce karşılaşılırsa okuma sonlandırması gerektiğini karakter *sayısı*.

*str*<br/>
Yazılacak olan bir dize.

*Ch*<br/>
Alınacak karakter.

*strbuf*<br/>
Yazılacak olan bir arabellek.

### <a name="return-value"></a>Dönüş Değeri

Get parametresiz biçiminde bir tamsayı veya dosya sonu okuma öğeyi döndürür. Akış kalan forms döndürür (* `this`).

### <a name="remarks"></a>Açıklamalar

Bu biçimlendirilmemiş giriş işlevlerin ilk öğenin Mümkünse, sanki olarak döndüren ayıklar `rdbuf` ->  `sbumpc`. Aksi halde **traits_type::**[eof](../standard-library/char-traits-struct.md#eof). Hiçbir öğe işlevi ayıklar, çağrı [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`).

İkinci işlevi ayıklar [int_type](../standard-library/basic-ios-class.md#int_type) öğesi `meta` aynı şekilde. Varsa `meta` karşılaştırır eşit **traits_type::eof**, işlev çağrıları `setstate`( **failbit**). Aksi halde depolar **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)( `meta`) içinde `Ch`. İşlev döndürür  **\*bu**.

Üçüncü işlevi döndürür **alma**(_ *Str*, `count`, `widen`('\ **n**')).

Dördüncü işlevi kadar ayıklar *sayısı* - 1 öğeleri ve _ dizi başında depolar *Str*. Her zaman depolar `char_type` herhangi depoladığı öğeleri ayıklanan sonra. Test sırayla ayıklama durdurur:

- Dosya sonunda.

- İşlev eşit karşılaştıran bir öğe ayıklar sonra *Delim*, bu durumda öğe denetlenen dizi için geri konur.

- İşlev ayıklar sonra *sayısı* - 1 öğeleri.

Hiçbir öğe işlevi ayıklar, çağrı `setstate`( **failbit**). Her durumda döndürür  **\*bu**.

Beşinci işlevi döndürür **alma**( **strbuf**, `widen`('\ **n**')).

Altıncı işlevi öğeleri ayıklar ve bunları ekler `strbuf`. Dosya sonu veya _ eşit karşılaştıran bir öğe ayıklama durdurur *Delim,* hangi değil ayıklanır. Bu ayrıca, bir ekleme başarısız olursa veya (hangi yakalandı ancak işlenemezse değil) bir özel durum oluşturur, söz konusu öğeyi ayıklamadan durdurur. Hiçbir öğe işlevi ayıklar, çağrı `setstate`( **failbit**). Herhangi bir durumda, işlev döndürür  **\*bu**.

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

## <a name="getline"></a>  basic_istream::getline

Girdi akışından bir satır alır.

```cpp
basic_istream<Elem, Tr>& getline(
    char_type* str,
    streamsize count);

basic_istream<Elem, Tr>& getline(
    char_type* str,
    streamsize count,
    char_type Delim);
```

### <a name="parameters"></a>Parametreler

*Sayısı*<br/>
Okunacak karakter sayısını `strbuf`.

*Delim*<br/>
Önce karşılaşılırsa okuma sonlandırması gerektiğini karakter *sayısı*.

*str*<br/>
Yazılacak olan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Akış (  **\*bu**).

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş bunlardan giriş işlevleri döndürür **getline**(_ *Str*, `count`, `widen`(' `\` **n**')).

İkinci işlevi kadar ayıklar *sayısı* - 1 öğeleri ve _ dizi başında depolar *Str*. Her zaman dize sonlandırma karakter depoladığı ayıklanan öğelerini sonra depolar. Test sırayla ayıklama durdurur:

- Dosya sonunda.

- İşlev eşit karşılaştıran bir öğe ayıklar sonra *Delim*, bu durumda öğe geri put ne denetlenen dizi için eklenmiş.

- İşlev ayıklar sonra *sayısı* - 1 öğeleri.

Hiçbir öğe işlevi ayıklar, veya *sayısı* - 1 öğeler, çağrı [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`). Her durumda döndürür  **\*bu**.

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

## <a name="ignore"></a>  basic_istream::ignore

Bir dizi okuyun konum geçerli atlanacak öğe neden olur.

```cpp
basic_istream<Elem, Tr>& ignore(
    streamsize count = 1,
    int_type Delim = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*Sayısı*<br/>
Geçerli okuma konumundan geçilecek öğelerin sayısı.

*Delim*<br/>
Sayısı önce karşılaştıysanız neden olan öğe `ignore` dönün ve sonra tüm öğeleri *Delim* okumak için.

### <a name="return-value"></a>Dönüş Değeri

Akış (  **\*bu**).

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş Giriş işlevi kadar ayıklar *sayısı* öğeleri ve bunları atar. Varsa *sayısı* eşittir **numeric_limits\<int >:: max**, ancak bu kadar büyük alınır. Ayıklama durdurur erken bir öğe veya dosya sonu üzerinde `Ch` şekilde **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( `Ch`) karşılaştırır eşit *Delim* (hangi Ayrıca ayıklanan). İşlev döndürür  **\*bu**.

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

## <a name="op_gt_gt"></a>  temel\_istream::operator >>

Giriş akışında bir işlev çağırır veya biçimlendirilmiş veri giriş akışından okur.

```cpp
basic_istream& operator>>(basic_istream& (* Pfn)(basic_istream&));
basic_istream& operator>>(ios_base& (* Pfn)(ios_base&));
basic_istream& operator>>(basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));
basic_istream& operator>>(basic_streambuf<Elem, Tr>* strbuf);
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

*pfn*<br/>
Bir işlev işaretçisi.

*strbuf*<br/>
Bir nesne türü `stream_buf`.

*VAL*<br/>
Akıştan okunan değer.

### <a name="return-value"></a>Dönüş Değeri

Akış (  **\*bu**).

### <a name="remarks"></a>Açıklamalar

\<İstream > Üstbilgi ayrıca çeşitli genel ayıklama işleçlerini tanımlar. Daha fazla bilgi için [işleci >> (\<istream >)](../standard-library/istream-operators.md#op_gt_gt).

İlk üye işlevi bir ifade biçiminde sağlar **istr**  >>  `ws` çağrıları [ws](../standard-library/istream-functions.md#ws)( **istr**) ve sonra  **\*bu**. İkinci ve üçüncü oluşturucular gibi diğer manipülatörleri olun [onaltılık](../standard-library/ios-functions.md#hex), benzer şekilde davranır. Kalan işlevleri biçimlendirilmiş girdi işlevleri oluşturur.

İşlev:

```cpp
basic_istream& operator>>(
    basic_streambuf<Elem, Tr>* strbuf);
```

öğeleri varsa ayıklar _ *Strbuf* null bir işaretçi değil ve bunları ekler *strbuf*. Ayıklama dosya durdurur. Ayrıca, bir ekleme başarısız olursa veya (hangi yakalandı ancak işlenemezse değil) bir özel durum oluşturur, söz konusu öğeyi ayıklamadan durdurur. Hiçbir öğe işlevi ayıklar, çağrı [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`). Herhangi bir durumda, işlev döndürür  **\*bu**.

İşlev:

```cpp
basic_istream& operator>>(bool& val);
```

bir alana ayıklar ve onu çağırarak bir Boolean değerine dönüştürür [use_facet](../standard-library/basic-filebuf-class.md#open)  <  `num_get` \< **Elem**, **InIt**> ( [getloc](../standard-library/ios-base-class.md#getloc)). [get](../standard-library/ios-base-class.md#getloc)( **InIt**( [rdbuf](../standard-library/basic-ios-class.md#rdbuf)), `Init`(0), **\*this**, `getloc`, `val`). Burada, **InIt** olarak tanımlanan [istreambuf_iterator](../standard-library/istreambuf-iterator-class.md) \< **Elem**, **Tr**>. İşlev döndürür  **\*bu**.

İşlevler:

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

Her bir alanı ayıklayın ve çağırarak bir sayısal değere Dönüştür `use_facet` <  `num_get` \< **Elem**, **InIt**> ( `getloc`). [get](#get)( **InIt**( `rdbuf`), `Init`(0), **\*this**, `getloc`, `val`). Burada, **InIt** olarak tanımlanan `istreambuf_iterator` \< **Elem**, **Tr**>, ve `val` türünde **uzun**, **işaretsiz uzun**, veya **void** <strong>\*</strong> gerektiğinde.

Dönüştürülen değer türü olarak temsil edilemez `val`, işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`). Herhangi bir durumda, işlev döndürür  **\*bu**.

İşlevler:

```cpp
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```

Her bir alanı ayıklayın ve çağırarak bir sayısal değere Dönüştür `use_facet` <  `num_get` \< **Elem**, **InIt**> ( `getloc`). **get**( **InIt**( `rdbuf`), `Init`(0), **\*this**, `getloc`, `val`). Burada, `InIt` olarak tanımlanan `istreambuf_iterator` \< **Elem**, **Tr**>, ve `val` türünde **çift** veya **uzun çift** gerektiğinde.

Dönüştürülen değer türü olarak temsil edilemez `val`, işlev çağrıları `setstate`( **failbit**). Her durumda döndürür  **\*bu**.

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

## <a name="op_eq"></a>  basic_istream::operator =

Atar `basic_istream` bu nesneye işlecinin sağ tarafında. Bu, bir taşıma ataması ilgili bir `rvalue` kopyasını bırakmaz arkasında başvuru.

```cpp
basic_istream& operator=(basic_istream&& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bir `rvalue` başvurusu bir `basic_ifstream` nesne.

### <a name="return-value"></a>Dönüş Değeri

Döndürür * bu.

### <a name="remarks"></a>Açıklamalar

Üye işleci çağırır takas `( right)`.

## <a name="peek"></a>  basic_istream::Peek

Okunacak sonraki karakteri döndürür.

```cpp
int_type peek();
```

### <a name="return-value"></a>Dönüş Değeri

Okunacak sonraki karakteri.

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş Giriş işlevi bir öğe Mümkünse, sanki olarak döndüren ayıklar `rdbuf`  ->  [sgetc](../standard-library/basic-streambuf-class.md#sgetc). Aksi halde **traits_type::**[eof](../standard-library/char-traits-struct.md#eof).

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

## <a name="putback"></a>  basic_istream::putback

Belirtilen bir karakter akışı halinde yerleştirir.

```cpp
basic_istream<Elem, Tr>& putback(
    char_type Ch);
```

### <a name="parameters"></a>Parametreler

*Ch*<br/>
Akışa geri koymak için bir karakter.

### <a name="return-value"></a>Dönüş Değeri

Akış (  **\*bu**).

### <a name="remarks"></a>Açıklamalar

[Biçimlendirilmemiş Giriş işlevi](../standard-library/basic-istream-class.md) geri koyar *Ch*, olası, buf [rdbuf](../standard-library/basic-ios-class.md#rdbuf)`->`[sputbackc](../standard-library/basic-streambuf-class.md#sputbackc). Rdbuf bir null işaretçi ise veya çağrı `sputbackc` döndürür **traits_type::**[eof](../standard-library/char-traits-struct.md#eof), işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)(`badbit`). Her durumda döndürür  **\*bu**.

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

## <a name="read"></a>  basic_istream::Read

Belirtilen sayıda karakteri akıştan okur ve bunları bir dizide saklar.

Geçirilen değerlerin doğru olduğunu kontrol etmek için arayan olmasına olduğundan bu güvensiz olabilecek bir yöntemdir.

```cpp
basic_istream<Elem, Tr>& read(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Dizi içindeki karakterleri okumak.

*Sayısı*<br/>
Okunacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Akış ( `*this`).

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş Giriş işlevi kadar ayıklar *sayısı* öğeleri ve _ dizi başında depolar `Str`. Ayıklama durdurur erken çalışması işlevi çağıran dosya sonu üzerinde [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`). Her durumda döndürür `*this`.

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

## <a name="readsome"></a>  basic_istream::readsome

Belirtilen sayıda karakter değerlerini okur.

Geçirilen değerlerin doğru olduğunu kontrol etmek için arayan olmasına olduğundan bu güvensiz olabilecek bir yöntemdir.

```cpp
streamsize readsome(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Dizide `readsome` okuduğu karakterleri depolar.

*Sayısı*<br/>
Okunacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Aslında okumak, karakter sayısı [gcount](#gcount).

### <a name="remarks"></a>Açıklamalar

Bu biçimlendirilmemiş Giriş işlevi kadar ayıklar *sayısı* giriş öğelerden akışla aktarma ve bunları bir dizide saklar *str*.

Bu işlev, girişini beklemez. Verileri kullanılabilir okur.

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

## <a name="seekg"></a>  basic_istream::seekg

Bir akış okuma konumuna taşır.

```cpp
basic_istream<Elem, Tr>& seekg(pos_type pos);

basic_istream<Elem, Tr>& seekg(off_type off, ios_base::seekdir way);
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Okuma işaretçiyi için mutlak konumu.

*Kapalı*<br/>
Göreli olarak okundu işaretçiyi bir uzaklık *şekilde*.

*yolu*<br/>
Aşağıdakilerden birini [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir) numaralandırma.

### <a name="return-value"></a>Dönüş Değeri

Akış (  **\*bu**).

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi mutlak bir arama gerçekleştirir, ikinci üye işlevi bir göreli arama yapar.

> [!NOTE]
> İkinci üye işlevi metin dosyalarını kullanmayın, standart C++ desteklemediğinden göreli metin dosyalarında çalışmaktadır.

Varsa [başarısız](../standard-library/basic-ios-class.md#fail) false ise ilk üye işlev çağrıları **newpos** = [rdbuf](../standard-library/basic-ios-class.md#rdbuf) -> [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)( `pos`), bazı `pos_type` geçici nesne `newpos`. Varsa `fail` yanlışsa, ikinci işlev çağrıları **newpos** = **rdbuf** -> [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)( `off`, `way`). Her iki durumda da, ( `off_type`) **newpos** == ( `off_type`)(-1) (yerleştirme işlemi başarısız oldu), işlev çağrıları `istr`. [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`). Her iki işlev dönüş  **\*bu**.

Varsa [başarısız](../standard-library/basic-ios-class.md#fail) true, üye işlevleri bir şey yapın.

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

## <a name="sentry"></a>  basic_istream::sentry

İç içe geçmiş sınıf, biçimlendirilmiş ve biçimlendirilmemiş giriş İşlevler, bildirim yapıları bir nesneyi tanımlar.

sınıf sentry {public: açık sentry (basic_istream\<Elem, Tr > & _Istr, bool _Noskip = false); operator bool() const;};

### <a name="remarks"></a>Açıklamalar

Varsa `_Istr.` [iyi](../standard-library/basic-ios-class.md#good) true ise oluşturucu:

- Çağrıları `_Istr`. [tie](../standard-library/basic-ios-class.md#tie) -> [Temizleme](../standard-library/basic-ostream-class.md#flush) varsa `_Istr`. `tie` null bir işaretçi değil

- Etkili bir şekilde çağıran [ws](../standard-library/istream-functions.md#ws)( `_Istr`) varsa `_Istr`. [bayrakları](../standard-library/ios-base-class.md#flags)**&**[skipws](../standard-library/ios-functions.md#skipws) sıfır değil ise

Eğer, böyle herhangi bir hazırlık sonra `_Istr`. `good` false ise oluşturucu çağrıları `_Istr`. [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`). Oluşturucu tarafından döndürülen değer her iki durumda da depolar `_Istr`. `good` içinde `status`. Bir sonraki çağrı `operator bool` bu depolanan değer sunar.

## <a name="swap"></a>  basic_istream::Swap

İki içeriğini birbiriyle değiştirir `basic_istream` nesneleri.

```cpp
void swap(basic_istream& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bir lvalue başvurusuna bir `basic_istream` nesne.

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrıları [basic_ios::swap](../standard-library/basic-ios-class.md#swap)`(right)`. Ayrıca ayıklama sayısı için ayıklama sayısını değiştirir *doğru*.

## <a name="sync"></a>  basic_istream::Sync

Akışın arabelleği ile stream ile ilişkili giriş cihazının eşitler.

```cpp
int sync();
```

### <a name="return-value"></a>Dönüş Değeri

Varsa [rdbuf](../standard-library/basic-ios-class.md#rdbuf) null işaretçisiyse, işlev -1 döndürür. Aksi takdirde, çağrı `rdbuf`  ->  [pubsync](../standard-library/basic-streambuf-class.md#pubsync). -1 döndürür, işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)(`badbit`) ve -1 döndürür. Aksi takdirde, sıfır döndürür.

## <a name="tellg"></a>  basic_istream::tellg

Akışta konumu geçerli okuma bildirir.

```cpp
pos_type tellg();
```

### <a name="return-value"></a>Dönüş Değeri

Akıştaki geçerli konumu.

### <a name="remarks"></a>Açıklamalar

Varsa [başarısız](../standard-library/basic-ios-class.md#fail) üye işlevinin döndürdüğü false ise [rdbuf](../standard-library/basic-ios-class.md#rdbuf) -> [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(0, `cur`, **içinde**). Aksi halde `pos_type`(-1).

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

## <a name="unget"></a>  basic_istream::unget

Puts karakter akışı halinde en son okuyun.

```cpp
basic_istream<Elem, Tr>& unget();
```

### <a name="return-value"></a>Dönüş Değeri

Akış (  **\*bu**).

### <a name="remarks"></a>Açıklamalar

[Biçimlendirilmemiş Giriş işlevi](../standard-library/basic-istream-class.md) geri önceki öğeye stream'de Mümkünse, buf koyar `rdbuf`  ->  [sungetc](../standard-library/basic-streambuf-class.md#sungetc). Varsa [rdbuf](../standard-library/basic-ios-class.md#rdbuf) null bir işaretçiyse veya çağrı `sungetc` döndürür **traits_type::**[eof](../standard-library/basic-ios-class.md#eof), işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)( `badbit`). Her durumda döndürür  **\*bu**.

Hakkında bilgi için `unget` başarısız, bkz: [basic_streambuf::sungetc](../standard-library/basic-streambuf-class.md#sungetc).

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

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
