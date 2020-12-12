---
description: 'Hakkında daha fazla bilgi edinin: basic_istream Sınıfı'
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
ms.openlocfilehash: 103777c5a4a590fbbfac95e690329b621497d087
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325699"
---
# <a name="basic_istream-class"></a>basic_istream Sınıfı

Öğesi ve, `Char_T` karakter nitelikleri, [traits_type](../standard-library/basic-ios-class.md#traits_type)olarak da bilinen sınıf özellikleri tarafından belirlendiği [char_type](../standard-library/basic-ios-class.md#char_type)şekilde, öğe ve tür öğeleri olan bir akış arabelleğindeki öğelerin ve kodlanmış nesnelerin ayıklanmasını denetleyen bir nesne tanımlar.

## <a name="syntax"></a>Syntax

```cpp
template <class Char_T, class Tr = char_traits<Char_T>>
class basic_istream : virtual public basic_ios<Char_T, Tr>
```

## <a name="remarks"></a>Açıklamalar

Üye işlevlerinin çoğu aşırı yükleme [işleci>>](#op_gt_gt) , giriş işlevleri olarak biçimlendirilir. Bunlar, şu kalıbı izler:

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

Her iki işlev grubu, [`setstate`](../standard-library/basic-ios-class.md#setstate) `(eofbit)` öğelerin ayıklanması sırasında dosya sonuyla karşılaştıklarında çağırır.

Sınıf `basic_istream<Char_T, Tr>` mağazalarından oluşan nesne:

- Sınıfının sanal ortak temel nesnesi [`basic_ios`](../standard-library/basic-ios-class.md) `<Char_T, Tr>` .

- Son biçimlendirilmemiş giriş işleminin ayıklama sayısı ( `count` Önceki kodda çağrılır).

## <a name="example"></a>Örnek

Giriş akışları hakkında daha fazla bilgi edinmek için [Basic_ifstream sınıfının](../standard-library/basic-ifstream-class.md) örneğine bakın.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_istream](#basic_istream)|Türünde bir nesne oluşturur `basic_istream` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[gcount](#gcount)|Biçimlendirilmemiş son girdi sırasında okunan karakter sayısını döndürür.|
|[get](#get)|Giriş akışından bir veya daha fazla karakteri okur.|
|[getline](#getline)|Giriş akışından bir çizgi okur.|
|[Yoksay](#ignore)|Geçerli okuma konumundan bir dizi öğenin atlanmasına neden olur.|
|[özelliğini](#peek)|Okunacak sonraki karakteri döndürür.|
|[Putback](#putback)|Belirtilen bir karakteri akışa koyar.|
|[okuyamaz](#read)|Akıştan belirtilen sayıda karakteri okur ve bunları bir dizide depolar.|
|[readsome](#readsome)|Yalnızca arabellekten oku.|
|[seekg](#seekg)|Bir akıştaki okuma konumunu gider.|
|[Nöbetçisi](#sentry)|İç içe yerleştirilmiş sınıf, bildirim yapılarını biçimli giriş işlevlerini ve biçimlendirilmemiş giriş işlevlerini içeren bir nesneyi tanımlar.|
|[Kur](#swap)|Bu `basic_istream` nesneyi, belirtilen `basic_istream` nesne parametresi için değiştirir.|
|[Eşitleme](#sync)|Akışın ilgili giriş cihazını akışın arabelleğine eşitler.|
|[tellg](#tellg)|Akıştaki geçerli okuma konumunu raporlar.|
|[unget](#unget)|En son okunan karakteri akışa geri koyar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç>>](#op_gt_gt)|Giriş akışında bir işlev çağırır veya giriş akışından biçimlendirilen verileri okur.|
|[işleç =](#op_eq)|`basic_istream`İşlecin sağ tarafına bu nesneye atar. Bu `rvalue` , arka planda olmayan bir başvuruyu içeren bir taşıma atamasıdır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<istream>

**Ad alanı:** std

## <a name="basic_istreambasic_istream"></a><a name="basic_istream"></a> basic_istream:: basic_istream

Türünde bir nesne oluşturur `basic_istream` .

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
**`true`** Standart bir akışdır; Aksi takdirde, **`false`** .

*Right*\
`basic_istream`Kopyalanacak bir nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu çağırarak temel sınıfı başlatır [`init`](../standard-library/basic-ios-class.md#init) `(strbuf)` . Ayrıca, ayıklama sayısında sıfır depolar. Bu ayıklama sayısı hakkında daha fazla bilgi için [Basic_istream sınıfına](../standard-library/basic-istream-class.md) genel bakış ' ın açıklamalar bölümüne bakın.

İkinci Oluşturucu çağırarak temel sınıfı başlatır `move(right)` . Ayrıca `right.gcount()` , ayıklama sayımında depolar ve * Right * * ayıklama sayısında sıfır depolar.

### <a name="example"></a>Örnek

Giriş akışları hakkında daha fazla bilgi edinmek için [basic_ifstream:: basic_ifstream](../standard-library/basic-ifstream-class.md#basic_ifstream) örneğe bakın.

## <a name="basic_istreamgcount"></a><a name="gcount"></a> basic_istream:: gcount

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

## <a name="basic_istreamget"></a><a name="get"></a> basic_istream:: Get

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

*biriktirme*\
*Strarabelleğe* okunacak karakter sayısı.

*ayırıcı*\
*Count*'tan önce karşılaşılırsa okumayı sonlanacak karakter.

*üstbilgisine*\
Yazılacak bir dize.

*Denetleyebilirsiniz*\
Alınacak bir karakter.

*strarabelleğe*\
Yazılacak bir arabellek.

### <a name="return-value"></a>Dönüş Değeri

Parametresiz formu, bir tamsayı veya dosya sonu olarak okunan öğeyi döndürür. Kalan formlar akışı döndürür (* **`this`** ).

### <a name="remarks"></a>Açıklamalar

İlk biçimlendirilmemiş giriş işlevi, mümkün olursa olduğu gibi bir öğeyi ayıklar `rdbuf->sbumpc` . Aksi takdirde, döndürür `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof) . İşlev hiçbir öğe ayıklaıyorsa, çağırır [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)` .

İkinci işlev [int_type](../standard-library/basic-ios-class.md#int_type) öğesini `meta` aynı şekilde ayıklar. `meta`Şuna eşit olarak karşılaştırıyorsa `traits_type::eof` işlev çağırır `setstate(failbit)` . Aksi halde, `traits_type::` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) `(meta)` *ch*'de depolanır. İşlev __* this__ döndürür.

Üçüncü işlev döndürür `get(str, count, widen('\n'))` .

Dördüncü işlev öğeler için ayıklar `count - 1` ve bu öğeleri *Str*'den başlayarak dizi içinde depolar. Her zaman, `char_type` depoladığı her ayıklanan öğeden sonra depolar. Sınama sırasında, ayıklama durduruluyor:

- Dosya sonunda.

- İşlev, eşit *sınırlayıcıyla* karşılaştırılmış bir öğeyi ayıkladıktan sonra. Bu durumda, öğesi denetimli diziye geri konur.

- İşlev öğeleri ayıkladıktan sonra `count - 1` .

İşlev hiçbir öğe ayıklaıyorsa, çağırır `setstate(failbit)` . Herhangi bir durumda, __* this__ döndürür.

Beşinci işlev döndürür `get(strbuf, widen('\n'))` .

Altıncı işlev öğeleri ayıklar ve bunları *strarabelleğe* ekler. Ayıklama işlemi dosya sonu veya eşit *sınırlayıcıyla* karşılaştırıldığı bir öğe üzerinde veya ayıklanmayan bir öğe üzerinde durduruluyor. Ayrıca, bir ekleme başarısız olursa veya bir özel durum oluşturursa (yakalanırsa ancak yeniden atılmadığında), söz konusu öğeyi ayıklamadan da duraklar. İşlev hiçbir öğe ayıklaıyorsa, çağırır `setstate(failbit)` . Herhangi bir durumda, işlev __* this__ döndürür.

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

## <a name="basic_istreamgetline"></a><a name="getline"></a> basic_istream:: getline

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

*biriktirme*\
*Strarabelleğe* okunacak karakter sayısı.

*ayırıcı*\
*Count*'tan önce karşılaşılırsa okumayı sonlanacak karakter.

*üstbilgisine*\
Yazılacak bir dize.

### <a name="return-value"></a>Dönüş Değeri

Akış (__* this__).

### <a name="remarks"></a>Açıklamalar

Bu biçimlendirilmemiş giriş işlevlerinin ilki döndürür `getline(str, count, widen('\n'))` .

İkinci işlev öğe ayıklar ve bu `count - 1` öğeleri *Str*'dan başlayarak dizi içinde depolar. Bu, her zaman dize sonlandırma karakterini, depoladığı herhangi bir ayıklanan öğeden sonra depolar. Sınama sırasında, ayıklama durduruluyor:

- Dosya sonunda.

- İşlev, eşit *sınırlayıcıyla* karşılaştırılmış bir öğeyi ayıkladıktan sonra. Bu durumda, öğesi geri yerleştirmez ve denetlenen diziye eklenmez.

- İşlev öğeleri ayıkladıktan sonra `count - 1` .

İşlev hiçbir öğe veya öğe ayıklaıyorsa `count - 1` , çağırır [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)` . Herhangi bir durumda, __* this__ döndürür.

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

## <a name="basic_istreamignore"></a><a name="ignore"></a> basic_istream:: Ignore

Geçerli okuma konumundan bir dizi öğenin atlanmasına neden olur.

```cpp
basic_istream<Char_T, Tr>& ignore(
    streamsize count = 1,
    int_type delimiter = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Geçerli okuma konumundan atlanacak öğe sayısı.

*ayırıcı*\
Saymadan önce karşılaşılırsa öğesi, `ignore` *sınırlayıcıdan* sonra tüm öğeleri döndürmeye ve izin vermeye neden olur.

### <a name="return-value"></a>Dönüş Değeri

Akış (__* this__).

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş giriş işlevi öğeleri *saymak* için ayıklar ve bunları atar. Ancak *Count* eşitse, `numeric_limits<int>::max` Bu, rastgele büyük olarak gerçekleştirilir. Ayıklama işlemi, dosyanın sonunda veya bir öğe üzerinde `Ch` `traits_type::` [`to_int_type`](../standard-library/char-traits-struct.md#to_int_type) `(Ch)` (aynı zamanda ayıklanmış) eşitlik ile  karşılaştırılır. İşlev __* this__ döndürür.

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

## <a name="basic_istreamoperator"></a><a name="op_gt_gt"></a> temel \_ IStream:: operator>>

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

*Acil*\
Akıştan okunacak değer.

### <a name="return-value"></a>Dönüş Değeri

Akış (__* this__).

### <a name="remarks"></a>Açıklamalar

\<istream>Üstbilgi Ayrıca birkaç genel ayıklama işleci tanımlar. Daha fazla bilgi için bkz. [operator>>  ( \<istream> )](../standard-library/istream-operators.md#op_gt_gt).

İlk üye işlevi, formun bir ifadesinin çağrı yapılmasını sağlar `istr >> ws` [`ws`](../standard-library/istream-functions.md#ws) `(istr)` ve ardından __* this__ döndürür. İkinci ve üçüncü işlevleri gibi diğer işleicilere [`hex`](../standard-library/ios-functions.md#hex) benzer şekilde davrandığından emin olun. Kalan işlevler, biçimlendirilen giriş işlevleridir.

İşlev:

```cpp
basic_istream& operator>>(
    basic_streambuf<Char_T, Tr>* strbuf);
```

*strarabelleğe* boş bir işaretçi değilse öğeleri ayıklar ve bunları *strarabelleğe* ekler. Dosya sonunda ayıklama durduruluyor. Ayrıca, bir ekleme başarısız olursa veya bir özel durum oluşturursa (yakalanırsa ancak yeniden atılmadığında), söz konusu öğeyi ayıklamadan da duraklar. İşlev hiçbir öğe ayıklaıyorsa, çağırır [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)` . Herhangi bir durumda, işlev __* this__ döndürür.

İşlev:

```cpp
basic_istream& operator>>(bool& val);
```

bir alanı ayıklar ve çağırarak bir Boole değerine dönüştürür [`use_facet`](../standard-library/basic-filebuf-class.md#open) `< num_get<Char_T, InIt>(` [`getloc`](../standard-library/ios-base-class.md#getloc) `).` [`get`](../standard-library/ios-base-class.md#getloc) `( InIt(` [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) `), Init(0), *this, getloc, val)` . Burada, `InIt` olarak tanımlanmıştır [`istreambuf_iterator`](../standard-library/istreambuf-iterator-class.md) `<Char_T, Tr>` . İşlev __* this__ döndürür.

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

bir alanı ayıklayın ve çağırarak sayısal değere dönüştürün `use_facet<num_get<Char_T, InIt>(getloc).` [`get`](#get) `(InIt(rdbuf), Init(0), *this, getloc, val)` . Burada, `InIt` olarak tanımlanmıştır `istreambuf_iterator<Char_T, Tr>` ve *Val* türü **`long`** , ya da **`unsigned long`** **`void`** <strong>\*</strong> gerektiği şekilde tanımlanır.

Dönüştürülen değer *Val* türü olarak temsil edilemiyorsa işlev çağırır [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)` . Herhangi bir durumda, işlev __* this__ döndürür.

İşlevlerin her biri:

```cpp
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```

bir alanı ayıklayın ve çağırarak sayısal değere dönüştürün `use_facet<num_get<Char_T, InIt>(getloc).get(InIt(rdbuf), Init(0), *this, getloc, val)` . Burada, `InIt` olarak tanımlanmıştır `istreambuf_iterator<Char_T, Tr>` ve *Val* türü **`double`** ya da **`long double`** gereklidir.

Dönüştürülen değer *Val* türü olarak temsil edilemiyorsa işlev çağırır `setstate(failbit)` . Herhangi bir durumda, __* this__ döndürür.

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

## <a name="basic_istreamoperator"></a><a name="op_eq"></a> basic_istream:: operator =

`basic_istream`İşlecin sağ tarafına bu nesneye atar. Bu `rvalue` , arka planda olmayan bir başvuruyu içeren bir taşıma atamasıdır.

```cpp
basic_istream& operator=(basic_istream&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`rvalue`Bir `basic_ifstream` nesneye başvuru.

### <a name="return-value"></a>Dönüş Değeri

__* This__ döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işleci çağırır `swap(right)` .

## <a name="basic_istreampeek"></a><a name="peek"></a> basic_istream::p EEK

Okunacak sonraki karakteri döndürür.

```cpp
int_type peek();
```

### <a name="return-value"></a>Dönüş Değeri

Okunacak sonraki karakter.

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş giriş işlevi, mümkün olursa olduğu gibi bir öğeyi ayıklar `rdbuf->` [`sgetc`](../standard-library/basic-streambuf-class.md#sgetc) . Aksi takdirde, döndürür `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof) .

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

## <a name="basic_istreamputback"></a><a name="putback"></a> basic_istream::p utback

Belirtilen bir karakteri akışa koyar.

```cpp
basic_istream<Char_T, Tr>& putback(
    char_type Ch);
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Akışa geri yerleştirilecek bir karakter.

### <a name="return-value"></a>Dönüş Değeri

Akış (__* this__).

### <a name="remarks"></a>Açıklamalar

[Biçimlendirilmemiş giriş işlevi](../standard-library/basic-istream-class.md) , mümkün olduğunda, öğesini çağırarak *, geri koyar* [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) `->` [`sputbackc`](../standard-library/basic-streambuf-class.md#sputbackc) . `rdbuf`Null işaretçisiyse veya çağrısı `sputbackc` döndürürse, `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof) işlev çağırır [`setstate`](../standard-library/basic-ios-class.md#setstate) `(badbit)` . Herhangi bir durumda, __* this__ döndürür.

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

## <a name="basic_istreamread"></a><a name="read"></a> basic_istream:: Read

Akıştan belirtilen sayıda karakteri okur ve bunları bir dizide depolar.

Bu yöntem, geçilen değerlerin doğru olup olmadığını denetlemek için çağrıyı yapana bağlı olduğundan güvenli olmayabilir.

```cpp
basic_istream<Char_T, Tr>& read(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
Karakterlerin okunacağı dizi.

*biriktirme*\
Okunacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Stream ( **`*this`** ).

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş giriş işlevi, öğeleri *saymak* için ayıklar ve *Str*' den başlayarak dizi içinde depolar. Ayıklama işlemi dosya sonundan erken durduruluyor, bu durumda işlev çağırır [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)` . Herhangi bir durumda, __* this__ döndürür.

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

## <a name="basic_istreamreadsome"></a><a name="readsome"></a> basic_istream:: readsome

Belirtilen karakter değerleri sayısını okur.

Bu yöntem, geçilen değerlerin doğru olup olmadığını denetlemek için çağrıyı yapana bağlı olduğundan güvenli olmayabilir.

```cpp
streamsize readsome(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
İçinde `readsome` okuduğu karakterleri depolayan dizi.

*biriktirme*\
Okunacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Gerçekte okunan karakterlerin sayısı [`gcount`](#gcount) .

### <a name="remarks"></a>Açıklamalar

Bu biçimlendirilmemiş giriş işlevi, giriş akışındaki öğeleri *saymak* için ayıklar ve bunları dizi *Str* içinde depolar.

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

## <a name="basic_istreamseekg"></a><a name="seekg"></a> basic_istream:: seekg

Bir akıştaki okuma konumunu gider.

```cpp
basic_istream<Char_T, Tr>& seekg(pos_type pos);

basic_istream<Char_T, Tr>& seekg(off_type off, ios_base::seekdir way);
```

### <a name="parameters"></a>Parametreler

*'un*\
Okuma işaretçisinin taşınacağı mutlak konum.

*dışına*\
Okuma işaretçisini göreli olarak taşımaya yönelik bir göreli *yol*.

*yapmanın*\
[İos_base:: seekdir](../standard-library/ios-base-class.md#seekdir) Numaralandırmalardan biri.

### <a name="return-value"></a>Dönüş Değeri

Akış (__* this__).

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi mutlak bir arama gerçekleştirir, ikinci üye işlevi göreli bir arama gerçekleştirir.

> [!NOTE]
> Standart C++ metin dosyalarında göreli aramalar desteklemediğinden, ikinci üye işlevi metin dosyalarıyla birlikte kullanmayın.

[`fail`](../standard-library/basic-ios-class.md#fail)Yanlışsa, `newpos =` [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) `->` [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos) `(pos)` bazı `pos_type` geçici nesneler için `newpos` ilk üye işlevi çağırır. `fail`Yanlışsa, ikinci işlev çağırır `newpos = rdbuf->` [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) `( off, way)` . Her iki durumda da `(off_type)newpos == (off_type)(-1)` (konumlandırma işlemi başarısız olursa), işlev çağırır `istr.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)` . Her iki işlev de __* this__ döndürür.

[`fail`](../standard-library/basic-ios-class.md#fail)True ise üye işlevleri hiçbir şey yapmaz.

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

## <a name="basic_istreamsentry"></a><a name="sentry"></a> basic_istream:: Sentry

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

`_Istr.` [`good`](../standard-library/basic-ios-class.md#good) True ise, Oluşturucu:

- `_Istr.` [`tie`](../standard-library/basic-ios-class.md#tie) `->` [`flush`](../standard-library/basic-ostream-class.md#flush) `_Istr.tie` Null işaretçisiyse çağırır.

- [`ws`](../standard-library/istream-functions.md#ws) `(_Istr)` `_Istr.` [`flags`](../standard-library/ios-base-class.md#flags) `&` [`skipws`](../standard-library/ios-functions.md#skipws) Sıfır değilse, etkin olarak çağrılır.

Bu tür bir hazırlığından sonra, `_Istr.good` Oluşturucu çağırır `_Istr.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)` . Herhangi bir durumda, Oluşturucu içinde tarafından döndürülen değeri depolar `_Istr.good` `status` . Daha sonraki bir çağrı, `operator bool` Bu depolanmış değeri teslim eder.

## <a name="basic_istreamswap"></a><a name="swap"></a> basic_istream:: swap

İki nesnenin içeriğini değiş tokuş eder `basic_istream` .

```cpp
void swap(basic_istream& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir nesneye lvalue başvurusu `basic_istream` .

### <a name="remarks"></a>Açıklamalar

Üye işlevi çağırır [`basic_ios::swap`](../standard-library/basic-ios-class.md#swap) `(right)` . Ayrıca ayıklama sayısını *sağ* için ayıklama sayısı ile de değiştirir.

## <a name="basic_istreamsync"></a><a name="sync"></a> basic_istream:: Sync

Akışın ilgili giriş cihazını akışın arabelleğine eşitler.

```cpp
int sync();
```

### <a name="return-value"></a>Dönüş Değeri

[`rdbuf`](../standard-library/basic-ios-class.md#rdbuf)Null işaretçisiyse, işlev-1 döndürür. Aksi takdirde, çağırır `rdbuf->` [`pubsync`](../standard-library/basic-streambuf-class.md#pubsync) . Bu çağrı-1 döndürürse, işlevi çağırır [`setstate`](../standard-library/basic-ios-class.md#setstate) `(badbit)` ve-1 döndürür. Aksi takdirde, işlev sıfır döndürür.

## <a name="basic_istreamtellg"></a><a name="tellg"></a> basic_istream:: tellg

Akıştaki geçerli okuma konumunu raporlar.

```cpp
pos_type tellg();
```

### <a name="return-value"></a>Dönüş Değeri

Akıştaki geçerli konum.

### <a name="remarks"></a>Açıklamalar

[`fail`](../standard-library/basic-ios-class.md#fail)Yanlış ise, üye işlevi döndürür [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) `->` [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) `(0, cur, in)` . Aksi takdirde, döndürür `pos_type(-1)` .

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

## <a name="basic_istreamunget"></a><a name="unget"></a> basic_istream:: unget

En son okunan karakteri akışa geri koyar.

```cpp
basic_istream<Char_T, Tr>& unget();
```

### <a name="return-value"></a>Dönüş Değeri

Akış (__* this__).

### <a name="remarks"></a>Açıklamalar

[Biçimlendirilmemiş giriş işlevi](../standard-library/basic-istream-class.md) , mümkünse bir önceki öğeyi, mümkün olduğunda, çağırarak gibi geri koyar `rdbuf->` [`sungetc`](../standard-library/basic-streambuf-class.md#sungetc) . [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf)Null işaretçisiyse veya çağrısı `sungetc` döndürürse, `traits_type::` [`eof`](../standard-library/basic-ios-class.md#eof) işlev çağırır [`setstate`](../standard-library/basic-ios-class.md#setstate) `(badbit)` . Herhangi bir durumda, __* this__ döndürür.

Nasıl başarısız olabileceği hakkında bilgi için `unget` bkz [`basic_streambuf::sungetc`](../standard-library/basic-streambuf-class.md#sungetc) ..

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

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
