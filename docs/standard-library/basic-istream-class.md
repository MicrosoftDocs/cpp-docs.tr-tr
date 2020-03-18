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
ms.openlocfilehash: 68c7f7ffa9c32c16654e57c8249348d74cc83a5b
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79416923"
---
# <a name="basic_istream-class"></a>basic_istream Sınıfı

[Char_type](../standard-library/basic-ios-class.md#char_type)olarak da bilinen, karakter nitelikleri, [traits_type](../standard-library/basic-ios-class.md#traits_type)olarak da *bilinen sınıf özellikleri*tarafından belirlendiği şekilde, öğe ve kodlanmış nesnelerin bir akış Arabelle`Char_T`ğinden ayıklanmasını denetleyen bir nesne tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Char_T, class Tr = char_traits<Char_T>>
class basic_istream : virtual public basic_ios<Char_T, Tr>
```

## <a name="remarks"></a>Açıklamalar

Üye işlevlerinin çoğu, [> >](#op_gt_gt) aşırı yüklenmiş giriş işlevleridir. Bunlar, şu kalıbı izler:

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

Diğer birçok üye işlevi biçimlendirilmemiş giriş işlevleridir. Bunlar, şu kalıbı izler:

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

Her iki işlev grubu [`setstate`](../standard-library/basic-ios-class.md#setstate) çağrısı, öğelerin ayıklanması sırasında dosya sonuyla karşılaştıklarında`(eofbit)`.

`basic_istream<Char_T, Tr>` depolayan bir nesne:

- [`basic_ios`](../standard-library/basic-ios-class.md)`<Char_T, Tr>`sınıfının sanal ortak temel nesnesi.

- Son biçimlendirilmemiş giriş işleminin ayıklama sayısı (önceki kodda `count` olarak adlandırılır).

## <a name="example"></a>Örnek

Giriş akışları hakkında daha fazla bilgi edinmek için [Basic_ifstream sınıfının](../standard-library/basic-ifstream-class.md) örneğine bakın.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_istream](#basic_istream)|`basic_istream`türünde bir nesne oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[gcount](#gcount)|Biçimlendirilmemiş son girdi sırasında okunan karakter sayısını döndürür.|
|[get](#get)|Giriş akışından bir veya daha fazla karakteri okur.|
|[getline](#getline)|Giriş akışından bir çizgi okur.|
|[Yoksay](#ignore)|Geçerli okuma konumundan bir dizi öğenin atlanmasına neden olur.|
|[özelliğini](#peek)|Okunacak sonraki karakteri döndürür.|
|[Putback](#putback)|Belirtilen bir karakteri akışa koyar.|
|[read](#read)|Akıştan belirtilen sayıda karakteri okur ve bunları bir dizide depolar.|
|[readsome](#readsome)|Yalnızca arabellekten oku.|
|[seekg](#seekg)|Bir akıştaki okuma konumunu gider.|
|[Nöbetçisi](#sentry)|İç içe yerleştirilmiş sınıf, bildirim yapılarını biçimli giriş işlevlerini ve biçimlendirilmemiş giriş işlevlerini içeren bir nesneyi tanımlar.|
|[Kur](#swap)|Bu `basic_istream` nesnesini, belirtilen `basic_istream` nesne parametresi için değiştirir.|
|[Eşitleme](#sync)|Akışın ilgili giriş cihazını akışın arabelleğine eşitler.|
|[tellg](#tellg)|Akıştaki geçerli okuma konumunu raporlar.|
|[unget](#unget)|En son okunan karakteri akışa geri koyar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç > >](#op_gt_gt)|Giriş akışında bir işlev çağırır veya giriş akışından biçimlendirilen verileri okur.|
|[işleç =](#op_eq)|Bu nesneye işlecinin sağ tarafına `basic_istream` atar. Bu, arka planda olmayan bir `rvalue` başvurusunu içeren bir taşıma atamasıdır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<ıstream >

**Ad alanı:** std

## <a name="basic_istream"></a>basic_istream:: basic_istream

`basic_istream`türünde bir nesne oluşturur.

```cpp
explicit basic_istream(
    basic_streambuf<Char_T, Tr>* strbuf,
    bool _Isstd = false);

basic_istream(basic_istream&& right);
```

### <a name="parameters"></a>Parametreler

*strarabelleğe*\
[Basic_streambuf](../standard-library/basic-streambuf-class.md)türünde bir nesne.

*_Isstd*\
Standart akış ise **doğru** ; Aksi takdirde, **false**.

*sağ*\
Kopyalanacak `basic_istream` nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, [`init`](../standard-library/basic-ios-class.md#init)`(strbuf)`çağırarak temel sınıfı başlatır. Ayrıca, ayıklama sayısında sıfır depolar. Bu ayıklama sayısı hakkında daha fazla bilgi için [Basic_istream sınıfına](../standard-library/basic-istream-class.md) genel bakış ' ın açıklamalar bölümüne bakın.

İkinci Oluşturucu, `move(right)`çağırarak temel sınıfı başlatır. Ayrıca, ayıklama sayımında `right.gcount()` depolar ve * Right * * ayıklama sayısında sıfır depolar.

### <a name="example"></a>Örnek

Giriş akışları hakkında daha fazla bilgi edinmek için [basic_ifstream:: basic_ifstream](../standard-library/basic-ifstream-class.md#basic_ifstream) örneğe bakın.

## <a name="gcount"></a>basic_istream:: gcount

Biçimlendirilmemiş son girdi sırasında okunan karakter sayısını döndürür.

```cpp
streamsize gcount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayıklama sayısı.

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş karakterleri okumak için [basic_istream:: Get](#get) kullanın.

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

## <a name="get"></a>basic_istream:: Get

Giriş akışından bir veya daha fazla karakteri okur.

```cpp
int_type get();

basic_istream<Char_T, Tr>& get(Char_T& Ch);
basic_istream<Char_T, Tr>& get(Char_T* str, streamsize count);
basic_istream<Char_T, Tr>& get(Char_T* str, streamsize count, Char_T delimiter);

basic_istream<Char_T, Tr>& get(basic_streambuf<Char_T, Tr>& strbuf);
basic_istream<Char_T, Tr>& get(basic_streambuf<Char_T, Tr>& strbuf, Char_T delimiter);
```

### <a name="parameters"></a>Parametreler

*sayı*\
*Strarabelleğe*okunacak karakter sayısı.

*sınırlayıcı*\
*Count*'tan önce karşılaşılırsa okumayı sonlanacak karakter.

*str*\
Yazılacak bir dize.

*Ch*\
Alınacak bir karakter.

*strarabelleğe*\
Yazılacak bir arabellek.

### <a name="return-value"></a>Dönüş Değeri

Parametresiz formu, bir tamsayı veya dosya sonu olarak okunan öğeyi döndürür. Kalan formlar akışı döndürüyor (* `this`).

### <a name="remarks"></a>Açıklamalar

İlk biçimlendirilmemiş giriş işlevi, mümkünse `rdbuf->sbumpc`dönerek bir öğeyi ayıklar. Aksi takdirde, `traits_type::`[`eof`](../standard-library/char-traits-struct.md#eof)döndürür. İşlev hiçbir öğe ayıklaıyorsa, [`setstate`](../standard-library/basic-ios-class.md#setstate)`(failbit)`çağırır.

İkinci işlev [int_type](../standard-library/basic-ios-class.md#int_type) öğesi `meta` aynı şekilde ayıklar. `meta`, `traits_type::eof`eşit olarak karşılaştırıyorsa işlev `setstate(failbit)`çağırır. Aksi takdirde, `traits_type::`[`to_char_type`](../standard-library/char-traits-struct.md#to_char_type)`(meta)` de *ch*içinde depolar. İşlev __* this__döndürür.

Üçüncü işlev `get(str, count, widen('\n'))`döndürür.

Dördüncü işlev `count - 1` öğeleri ayıklar ve bunları *Str*ile başlayan dizi içinde depolar. `char_type` her zaman, depoladığı tüm ayıklanan öğelerden sonra depolar. Sınama sırasında, ayıklama durduruluyor:

- Dosya sonunda.

- İşlev, eşit *sınırlayıcıyla*karşılaştırılmış bir öğeyi ayıkladıktan sonra. Bu durumda, öğesi denetimli diziye geri konur.

- İşlev `count - 1` öğeleri ayıkladıktan sonra.

İşlev hiçbir öğe ayıklaıyorsa, `setstate(failbit)`çağırır. Herhangi bir durumda, __* this__döndürür.

Beşinci işlev `get(strbuf, widen('\n'))`döndürür.

Altıncı işlev öğeleri ayıklar ve bunları *strarabelleğe*ekler. Ayıklama işlemi dosya sonu veya eşit *sınırlayıcıyla*karşılaştırıldığı bir öğe üzerinde veya ayıklanmayan bir öğe üzerinde durduruluyor. Ayrıca, bir ekleme başarısız olursa veya bir özel durum oluşturursa (yakalanırsa ancak yeniden atılmadığında), söz konusu öğeyi ayıklamadan da duraklar. İşlev hiçbir öğe ayıklaıyorsa, `setstate(failbit)`çağırır. Herhangi bir durumda, işlev __* this__döndürür.

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

## <a name="getline"></a>basic_istream:: getline

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

*sayı*\
*Strarabelleğe*okunacak karakter sayısı.

*sınırlayıcı*\
*Count*'tan önce karşılaşılırsa okumayı sonlanacak karakter.

*str*\
Yazılacak bir dize.

### <a name="return-value"></a>Dönüş Değeri

Akış ( __* this__).

### <a name="remarks"></a>Açıklamalar

Bu biçimlendirilmemiş giriş işlevlerinin ilki `getline(str, count, widen('\n'))`döndürür.

İkinci işlev `count - 1` öğeleri ayıklar ve bunları *Str*ile başlayan dizi içinde depolar. Bu, her zaman dize sonlandırma karakterini, depoladığı herhangi bir ayıklanan öğeden sonra depolar. Sınama sırasında, ayıklama durduruluyor:

- Dosya sonunda.

- İşlev, eşit *sınırlayıcıyla*karşılaştırılmış bir öğeyi ayıkladıktan sonra. Bu durumda, öğesi geri yerleştirmez ve denetlenen diziye eklenmez.

- İşlev `count - 1` öğeleri ayıkladıktan sonra.

İşlev hiçbir öğe veya `count - 1` öğesi ayıklaıyorsa, [`setstate`](../standard-library/basic-ios-class.md#setstate)`(failbit)`çağırır. Herhangi bir durumda, __* this__döndürür.

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

## <a name="ignore"></a>basic_istream:: Ignore

Geçerli okuma konumundan bir dizi öğenin atlanmasına neden olur.

```cpp
basic_istream<Char_T, Tr>& ignore(
    streamsize count = 1,
    int_type delimiter = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*sayı*\
Geçerli okuma konumundan atlanacak öğe sayısı.

*sınırlayıcı*\
Count 'tan önce karşılaşılırsa öğesi, *sınırlayıcıların* okunmasının ardından tüm öğelerin dönmesini ve izin vermesini `ignore` neden olur.

### <a name="return-value"></a>Dönüş Değeri

Akış ( __* this__).

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş giriş işlevi öğeleri *saymak* için ayıklar ve bunları atar. Eğer *Count* eşitse `numeric_limits<int>::max`, ancak rastgele büyük olarak alınır. Ayıklama işlemi dosya sonunda veya bir öğe `Ch`, `traits_type::`[`to_int_type`](../standard-library/char-traits-struct.md#to_int_type)`(Ch)` *sınırlayıcıyla* (Ayrıca ayıklanır) daha önce duraklar. İşlev __* this__döndürür.

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

## <a name="op_gt_gt"></a>temel\_IStream:: operator > >

Giriş akışında bir işlev çağırır veya giriş akışından biçimlendirilen verileri okur.

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

*PFN*\
Bir işlev işaretçisi.

*strarabelleğe*\
`stream_buf` türünün bir nesnesi.

*val*\
Akıştan okunacak değer.

### <a name="return-value"></a>Dönüş Değeri

Akış ( __* this__).

### <a name="remarks"></a>Açıklamalar

\<IStream > üst bilgisi birçok genel ayıklama işlecini de tanımlar. Daha fazla bilgi için bkz. [operator > > (\<ıstream >)](../standard-library/istream-operators.md#op_gt_gt).

İlk üye işlevi, bir form ifadesinin `istr >> ws` [`ws`](../standard-library/istream-functions.md#ws)`(istr)`çağırmasını sağlar ve ardından __* this__döndürür. İkinci ve üçüncü işlevleri, [`hex`](../standard-library/ios-functions.md#hex)gibi diğer işleicilere benzer şekilde davrandığından emin olmanızı sağlamaktır. Kalan işlevler, biçimlendirilen giriş işlevleridir.

İşlev:

```cpp
basic_istream& operator>>(
    basic_streambuf<Char_T, Tr>* strbuf);
```

*strarabelleğe* boş bir işaretçi değilse öğeleri ayıklar ve bunları *strarabelleğe*ekler. Dosya sonunda ayıklama durduruluyor. Ayrıca, bir ekleme başarısız olursa veya bir özel durum oluşturursa (yakalanırsa ancak yeniden atılmadığında), söz konusu öğeyi ayıklamadan da duraklar. İşlev hiçbir öğe ayıklaıyorsa, [`setstate`](../standard-library/basic-ios-class.md#setstate)`(failbit)`çağırır. Herhangi bir durumda, işlev __* this__döndürür.

İşlev:

```cpp
basic_istream& operator>>(bool& val);
```

bir alanı ayıklar ve [`use_facet`](../standard-library/basic-filebuf-class.md#open)`< num_get<Char_T, InIt>(`[`getloc`](../standard-library/ios-base-class.md#getloc)`).`[`get`](../standard-library/ios-base-class.md#getloc) [`( InIt(``rdbuf``), Init(0), *this, getloc, val)`çağırarak](../standard-library/basic-ios-class.md#rdbuf) bir Boole değerine dönüştürür. Burada `InIt` [`istreambuf_iterator`](../standard-library/istreambuf-iterator-class.md)`<Char_T, Tr>`olarak tanımlanmıştır. İşlev __* this__döndürür.

İşlevlerin her biri:

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

`use_facet<num_get<Char_T, InIt>(getloc).`[`get`](#get)`(InIt(rdbuf), Init(0), *this, getloc, val)`çağırarak bir alanı ayıklayın ve sayısal değere dönüştürün. Burada, `InIt` `istreambuf_iterator<Char_T, Tr>`olarak tanımlanmıştır ve *değer* , gerektiği gibi **Long**, **unsigned long**veya **void** <strong>\*</strong> türündedir.

Dönüştürülen değer *Val*türü olarak temsil edilemiyorsa, işlev [`setstate`](../standard-library/basic-ios-class.md#setstate)`(failbit)`çağırır. Herhangi bir durumda, işlev __* this__döndürür.

İşlevlerin her biri:

```cpp
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```

`use_facet<num_get<Char_T, InIt>(getloc).get(InIt(rdbuf), Init(0), *this, getloc, val)`çağırarak bir alanı ayıklayın ve sayısal değere dönüştürün. Burada, `InIt` `istreambuf_iterator<Char_T, Tr>`olarak tanımlanmıştır ve *değer* gerektiğinde **Double** ya da **Long Double** türündedir.

Dönüştürülmüş değer *Val*türü olarak temsil edilemiyorsa işlev `setstate(failbit)`çağırır. Herhangi bir durumda, __* this__döndürür.

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

## <a name="op_eq"></a>basic_istream:: operator =

Bu nesneye işlecinin sağ tarafına `basic_istream` atar. Bu, arka planda olmayan bir `rvalue` başvurusunu içeren bir taşıma atamasıdır.

```cpp
basic_istream& operator=(basic_istream&& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Bir `basic_ifstream` nesnesine `rvalue` başvurusu.

### <a name="return-value"></a>Dönüş Değeri

__* This__döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işleci `swap(right)`çağırır.

## <a name="peek"></a>basic_istream::p EEK

Okunacak sonraki karakteri döndürür.

```cpp
int_type peek();
```

### <a name="return-value"></a>Dönüş Değeri

Okunacak sonraki karakter.

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş giriş işlevi, mümkünse `rdbuf->`[`sgetc`](../standard-library/basic-streambuf-class.md#sgetc)döndüren gibi bir öğeyi ayıklar. Aksi takdirde, `traits_type::`[`eof`](../standard-library/char-traits-struct.md#eof)döndürür.

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

## <a name="putback"></a>basic_istream::p utback

Belirtilen bir karakteri akışa koyar.

```cpp
basic_istream<Char_T, Tr>& putback(
    char_type Ch);
```

### <a name="parameters"></a>Parametreler

*Ch*\
Akışa geri yerleştirilecek bir karakter.

### <a name="return-value"></a>Dönüş Değeri

Akış ( __* this__).

### <a name="remarks"></a>Açıklamalar

[Biçimlendirilmemiş giriş işlevi](../standard-library/basic-istream-class.md) , mümkünse [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf)`->`[`sputbackc`](../standard-library/basic-streambuf-class.md#sputbackc)çağırarak olduğu *gibi geri koyar*. `rdbuf` null işaretçisiyse veya `sputbackc` çağrısı `traits_type::`[`eof`](../standard-library/char-traits-struct.md#eof)döndürürse, işlev [`setstate`](../standard-library/basic-ios-class.md#setstate)`(badbit)`çağırır. Herhangi bir durumda, __* this__döndürür.

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

## <a name="read"></a>basic_istream:: Read

Akıştan belirtilen sayıda karakteri okur ve bunları bir dizide depolar.

Bu yöntem, geçilen değerlerin doğru olup olmadığını denetlemek için çağrıyı yapana bağlı olduğundan güvenli olmayabilir.

```cpp
basic_istream<Char_T, Tr>& read(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*str*\
Karakterlerin okunacağı dizi.

*sayı*\
Okunacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Akış (`*this`).

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş giriş işlevi, öğeleri *saymak* için ayıklar ve *Str*' den başlayarak dizi içinde depolar. Ayıklama, dosyanın sonunda erken durduruluyor, bu durumda işlev [`setstate`](../standard-library/basic-ios-class.md#setstate)`(failbit)`çağırır. Herhangi bir durumda, __* this__döndürür.

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

## <a name="readsome"></a>basic_istream:: readsome

Belirtilen karakter değerleri sayısını okur.

Bu yöntem, geçilen değerlerin doğru olup olmadığını denetlemek için çağrıyı yapana bağlı olduğundan güvenli olmayabilir.

```cpp
streamsize readsome(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*str*\
`readsome` okuduğu karakterleri depolayan dizi.

*sayı*\
Okunacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Gerçekten okunan karakter sayısı [`gcount`](#gcount).

### <a name="remarks"></a>Açıklamalar

Bu biçimlendirilmemiş giriş işlevi, giriş akışındaki öğeleri *saymak* için ayıklar ve bunları dizi *Str*içinde depolar.

Bu işlev girişi beklemez. Hangi verilerin kullanılabildiğini okur.

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

## <a name="seekg"></a>basic_istream:: seekg

Bir akıştaki okuma konumunu gider.

```cpp
basic_istream<Char_T, Tr>& seekg(pos_type pos);

basic_istream<Char_T, Tr>& seekg(off_type off, ios_base::seekdir way);
```

### <a name="parameters"></a>Parametreler

*pos*\
Okuma işaretçisinin taşınacağı mutlak konum.

*kapalı*\
Okuma işaretçisini göreli olarak taşımaya yönelik bir göreli *yol*.

*yol*\
[İos_base:: seekdir](../standard-library/ios-base-class.md#seekdir) Numaralandırmalardan biri.

### <a name="return-value"></a>Dönüş Değeri

Akış ( __* this__).

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi mutlak bir arama gerçekleştirir, ikinci üye işlevi göreli bir arama gerçekleştirir.

> [!NOTE]
> Standart C++ metin dosyalarında göreli aramalar desteklemediğinden, ikinci üye işlevi metin dosyalarıyla birlikte kullanmayın.

[`fail`](../standard-library/basic-ios-class.md#fail) false ise, ilk üye işlevi bazı`pubseekpos`geçici nesne`(pos)`için `newpos = `[`rdbuf`](../standard-library/basic-ios-class.md#rdbuf)`->`[`pos_type`](../standard-library/basic-streambuf-class.md#pubseekpos) `newpos`çağırır. `fail` false ise, ikinci işlev `newpos = rdbuf->`[`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff)`( off, way)`çağırır. Her iki durumda da, `(off_type)newpos == (off_type)(-1)` (konumlandırma işlemi başarısız olursa), işlev `istr.`[`setstate`](../standard-library/basic-ios-class.md#setstate)`(failbit)`çağırır. Her iki işlev de __* this__döndürür.

[`fail`](../standard-library/basic-ios-class.md#fail) true ise üye işlevleri hiçbir şey yapmaz.

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

## <a name="sentry"></a>basic_istream:: Sentry

İç içe yerleştirilmiş sınıf, bildirimi biçimli ve biçimlendirilmemiş giriş işlevlerini yapısını içeren bir nesneyi tanımlar.

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

`_Istr.`[`good`](../standard-library/basic-ios-class.md#good) true ise, Oluşturucu:

- `_Istr.tie` null bir işaretçi değilse [`flush`](../standard-library/basic-ostream-class.md#flush)`->``_Istr.`[`tie`](../standard-library/basic-ios-class.md#tie) çağırır.

- `_Istr.`[`flags`](../standard-library/ios-base-class.md#flags)` & `[`skipws`](../standard-library/ios-functions.md#skipws) sıfır dışında olduğunda [`ws`](../standard-library/istream-functions.md#ws)`(_Istr)` etkin bir şekilde çağırır.

Bu tür bir hazırlığından sonra `_Istr.good`, Oluşturucu `_Istr.`[`setstate`](../standard-library/basic-ios-class.md#setstate)`(failbit)`çağırır. Herhangi bir durumda, Oluşturucu `status``_Istr.good` tarafından döndürülen değeri depolar. Daha sonraki bir `operator bool` çağrısı, bu depolanmış değeri sağlar.

## <a name="swap"></a>basic_istream:: swap

İki `basic_istream` nesnesinin içeriğini değiş tokuş eder.

```cpp
void swap(basic_istream& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
`basic_istream` nesnesine bir lvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [`basic_ios::swap`](../standard-library/basic-ios-class.md#swap)`(right)`çağırır. Ayrıca ayıklama sayısını *sağ*için ayıklama sayısı ile de değiştirir.

## <a name="sync"></a>basic_istream:: Sync

Akışın ilgili giriş cihazını akışın arabelleğine eşitler.

```cpp
int sync();
```

### <a name="return-value"></a>Dönüş Değeri

[`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) null işaretçisiyse, işlev-1 döndürür. Aksi takdirde, `rdbuf->`[`pubsync`](../standard-library/basic-streambuf-class.md#pubsync)çağırır. Bu çağrı-1 döndürürse, işlev [`setstate`](../standard-library/basic-ios-class.md#setstate)`(badbit)` çağırır ve-1 döndürür. Aksi takdirde, işlev sıfır döndürür.

## <a name="tellg"></a>basic_istream:: tellg

Akıştaki geçerli okuma konumunu raporlar.

```cpp
pos_type tellg();
```

### <a name="return-value"></a>Dönüş Değeri

Akıştaki geçerli konum.

### <a name="remarks"></a>Açıklamalar

[`fail`](../standard-library/basic-ios-class.md#fail) false ise, üye işlevi [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf)`->`[`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff)`(0, cur, in)`döndürür. Aksi takdirde, `pos_type(-1)`döndürür.

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

## <a name="unget"></a>basic_istream:: unget

En son okunan karakteri akışa geri koyar.

```cpp
basic_istream<Char_T, Tr>& unget();
```

### <a name="return-value"></a>Dönüş Değeri

Akış ( __* this__).

### <a name="remarks"></a>Açıklamalar

[Biçimlendirilmemiş giriş işlevi](../standard-library/basic-istream-class.md) , mümkünse, `rdbuf->`[`sungetc`](../standard-library/basic-streambuf-class.md#sungetc)çağırarak olduğu gibi akışta önceki öğeyi geri koyar. [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) null işaretçisiyse veya `sungetc` çağrısı `traits_type::`[`eof`](../standard-library/basic-ios-class.md#eof)döndürürse, işlev [`setstate`](../standard-library/basic-ios-class.md#setstate)`(badbit)`çağırır. Herhangi bir durumda, __* this__döndürür.

`unget` nasıl başarısız olabileceği hakkında bilgi için bkz. [`basic_streambuf::sungetc`](../standard-library/basic-streambuf-class.md#sungetc).

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

[Standart kitaplıkta Iş parçacığı güvenliği\ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
