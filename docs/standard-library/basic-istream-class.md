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
ms.openlocfilehash: d1a76e9c639ac56ca693527543ecff5c597456f0
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452546"
---
# <a name="basicistream-class"></a>basic_istream Sınıfı

`Elem` [Char_type](../standard-library/basic-ios-class.md#char_type)olarak da bilinen, ve traits_ olarak da bilinen karakter nitelikleri, olarak da *bilinen sınıf özellikleri*tarafından belirlendiği şekilde, öğelerin ve kodlanmış nesnelerin bir akış arabelleğindeki ayıklanmasını denetleyen bir nesne tanımlar. [ yazın](../standard-library/basic-ios-class.md#traits_type).

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_istream : virtual public basic_ios<Elem, Tr>
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

Her iki işlev grubu, öğelerin ayıklanması sırasında`eofbit`dosya sonuyla karşılaştıklarında [SetState](../standard-library/basic-ios-class.md#setstate)() öğesini çağırır.

Sınıfının `basic_istream` bir< nesnesi, tr > depolar:  `Elem`

- [](../standard-library/basic-ios-class.md)Basic_ios< sınıfınınsanalortaktemelnesnesi`Elem`> `.`

- Son biçimlendirilmemiş giriş işleminin ayıklama sayısı (önceki kodda çağrılır `count` ).

## <a name="example"></a>Örnek

Giriş akışları hakkında daha fazla bilgi için bkz. [Basic_ifstream sınıfı](../standard-library/basic-ifstream-class.md) örneği.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_istream](#basic_istream)|Türünde `basic_istream`bir nesne oluşturur.|

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
|[Kur](#swap)|Bu `basic_istream` nesneyi, belirtilen `basic_istream` nesne parametresi için değiştirir.|
|[Eşitleme](#sync)|Akış ile ilişkili giriş cihazını akışın arabelleğine eşitler.|
|[tellg](#tellg)|Akıştaki geçerli okuma konumunu raporlar.|
|[unget](#unget)|En son okunan karakteri akışa geri koyar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç > >](#op_gt_gt)|Giriş akışında bir işlev çağırır veya giriş akışından biçimlendirilen verileri okur.|
|[operator=](#op_eq)|`basic_istream` İşlecin sağ tarafına bu nesneye atar. Bu, arkasına kopya bırakmayan bir `rvalue` başvuruyu içeren bir taşıma atamasıdır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<IStream >

**Ad alanı:** std

## <a name="basic_istream"></a>basic_istream::basic_istream

Türünde `basic_istream`bir nesne oluşturur.

```cpp
explicit basic_istream(
    basic_streambuf<Elem, Tr>* strbuf,
    bool _Isstd = false);

basic_istream(basic_istream&& right);
```

### <a name="parameters"></a>Parametreler

*strarabelleğe*\
[Basic_streambuf](../standard-library/basic-streambuf-class.md)türünde bir nesne.

*_Isstd*\
bu standart bir akıştır; Aksi takdirde, **false**.

*Right*\
Kopyalanacak `basic_istream` bir nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu [init](../standard-library/basic-ios-class.md#init)(_S `trbuf`) öğesini çağırarak temel sınıfı başlatır. Ayrıca, ayıklama sayısında sıfır depolar. Bu ayıklama sayısı hakkında daha fazla bilgi için [Basic_istream sınıfına](../standard-library/basic-istream-class.md) genel bakış konusunun açıklamalar bölümüne bakın.

İkinci Oluşturucu çağırarak `move( right)`temel sınıfı başlatır. Ayrıca, ayıklama sayısında _r `ight.gcount()` 'yi depolar ve _r `ight`için ayıklama sayısında sıfır depolar.

### <a name="example"></a>Örnek

Giriş akışları hakkında daha fazla bilgi edinmek için [basic_ifstream:: basic_ifstream](../standard-library/basic-ifstream-class.md#basic_ifstream) örneğine bakın.

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

basic_istream<Elem, Tr>& get(Elem& Ch);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count, Elem Delim);

basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf);
basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf, Elem Delim);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Okunacak karakter sayısı `strbuf`.

*Delib*\
*Count*'tan önce karşılaşılırsa, okumayı sonlanacak karakter.

*üstbilgisine*\
Yazılacak bir dize.

*Denetleyebilirsiniz*\
Alınacak bir karakter.

*strarabelleğe*\
Yazılacak bir arabellek.

### <a name="return-value"></a>Dönüş Değeri

Parametresiz formu, bir tamsayı veya dosya sonu olarak okunan öğeyi döndürür. Kalan formlar akışı döndürür (* `this`).

### <a name="remarks"></a>Açıklamalar

Bu biçimlendirilmemiş giriş işlevlerinin ilki, mümkün olduğunda, dönerek `rdbuf` ->  `sbumpc`gibi bir öğesi ayıklar. Aksi takdirde, **traits_type::** [EOF](../standard-library/char-traits-struct.md#eof)döndürür. İşlev hiçbir öğe ayıklaıyorsa, [SetState](../standard-library/basic-ios-class.md#setstate)(`failbit`) öğesini çağırır.

İkinci işlev [int_type](../standard-library/basic-ios-class.md#int_type) öğesini `meta` aynı şekilde ayıklar. **Traits_type:: EOF**ile eşit olarak karşılaştırıyorsa `setstate` `meta` işlev çağırır ( **failbit**). Aksi halde `meta`, içinde  `Ch`traits_type::[to_char_type](../standard-library/char-traits-struct.md#to_char_type)() depolar. İşlevi  **\*bunu**döndürür.

Üçüncü işlev **Get**(_ *Str*, `count`, `widen`(' \ **n**')) döndürür.

Dördüncü işlev *sayı* -1 öğesine kadar ayıklar ve bu öğeleri dizi Içinde _ *Str*başlayan dizide depolar. Her zaman, `char_type` depoladığı her ayıklanan öğeden sonra depolar. Sınama sırasında, ayıklama durduruluyor:

- Dosya sonunda.

- İşlev, eşit olarak karşılaştırılmış bir öğeyi ayıkladıktan *sonra, bu*durumda öğe denetimli diziye geri konur.

- İşlev *sayı* -1 öğelerini ayıkladıktan sonra.

İşlev hiçbir öğe ayıklaıyorsa, ( `setstate` **failbit**) öğesini çağırır. Herhangi bir durumda,  **\*bunu döndürür.**

Beşinci işlev **Get**( **strarabelleğe**, `widen`(' \ **n**')) döndürür.

Altıncı işlev öğeleri ayıklar ve içine `strbuf`ekler. Ayıklama işlemi, dosya sonu veya ayıklanmayan _ *Delid* ile karşılaştıran bir öğe üzerinde durduruluyor. Ayrıca, bir ekleme başarısız olursa veya bir özel durum oluşturursa (yakalanırsa ancak yeniden atılmadığında), söz konusu öğeyi ayıklamadan da duraklar. İşlev hiçbir öğe ayıklaıyorsa, ( `setstate` **failbit**) öğesini çağırır. Herhangi bir durumda, işlev  **\*bunu**döndürür.

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
basic_istream<Elem, Tr>& getline(
    char_type* str,
    streamsize count);

basic_istream<Elem, Tr>& getline(
    char_type* str,
    streamsize count,
    char_type Delim);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Okunacak karakter sayısı `strbuf`.

*Delib*\
*Count*'tan önce karşılaşılırsa, okumayı sonlanacak karakter.

*üstbilgisine*\
Yazılacak bir dize.

### <a name="return-value"></a>Dönüş Değeri

Stream (  **\*this**).

### <a name="remarks"></a>Açıklamalar

Bu biçimlendirilmemiş giriş işlevlerinin ilki **getline**(_ *Str* `count`,, `widen`(' `\` **n**')) döndürür.

İkinci işlev *say* -1 öğelerine kadar ayıklar ve bunları _ *Str*ile başlayan dizi içinde depolar. Bu, her zaman dize sonlandırma karakterini, depoladığı herhangi bir ayıklanan öğeden sonra depolar. Sınama sırasında, ayıklama durduruluyor:

- Dosya sonunda.

- İşlev, eşit olarak karşılaştırılmış bir öğeyi ayıkladıktan *sonra, bu*durumda öğe hiçbir şekilde geri yerleştirmez veya denetimli diziye eklenmez.

- İşlev *sayı* -1 öğelerini ayıkladıktan sonra.

İşlev hiçbir öğe veya *sayı* -1 öğesi ayıklaıyorsa, [SetState](../standard-library/basic-ios-class.md#setstate)(`failbit`) öğesini çağırır. Herhangi bir durumda,  **\*bunu döndürür.**

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
basic_istream<Elem, Tr>& ignore(
    streamsize count = 1,
    int_type Delim = traits_type::eof());
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Geçerli okuma konumundan atlanacak öğe sayısı.

*Delib*\
Count 'tan daha önce karşılaşılırsa öğesi, `ignore` döndürülmeye ve tüm öğelerin okunmamasını sağlar.

### <a name="return-value"></a>Dönüş Değeri

Stream (  **\*this**).

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş giriş işlevi öğeleri *saymak* için ayıklar ve bunları atar. *Count* değeri **numeric_limits\<int >:: Max**eşitse, bu, rastgele büyük olarak alınır. Ayıklama, dosyanın sonunda veya **traits_type::** [to_int_type](../standard-library/char-traits-struct.md#to_int_type)( `Ch`) `Ch` ile *aynı (ayıklanmış* ) gibi bir öğe üzerinde erken yanıt vermez. İşlevi  **\*bunu**döndürür.

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

*PFN*\
Bir işlev işaretçisi.

*strarabelleğe*\
Türünde `stream_buf`bir nesne.

*Acil*\
Akıştan okunacak değer.

### <a name="return-value"></a>Dönüş Değeri

Stream (  **\*this**).

### <a name="remarks"></a>Açıklamalar

\<IStream > üst bilgisi birçok genel ayıklama işlecini de tanımlar. Daha fazla bilgi için bkz. [operator > >\<(IStream >)](../standard-library/istream-operators.md#op_gt_gt).

İlk üye işlevi, >>  formun`ws` bir ifadesinin [WS](../standard-library/istream-functions.md#ws)( **Ise**) öğesini çağırmasını sağlar ve  **\*bunu**döndürür. İkinci ve üçüncü işlevleri, [onaltılık](../standard-library/ios-functions.md#hex)gibi diğer işleicilere benzer şekilde davrandığından emin olmanızı sağlamaktır. Kalan işlevler, biçimlendirilen giriş işlevlerini oluşturur.

İşlev:

```cpp
basic_istream& operator>>(
    basic_streambuf<Elem, Tr>* strbuf);
```

_ *Strarabelleğe* bir null işaretçi değilse öğeleri ayıklar ve bunları *strarabelleğe*ekler. Dosya sonunda ayıklama durduruluyor. Ayrıca, bir ekleme başarısız olursa veya bir özel durum oluşturursa (yakalanırsa ancak yeniden atılmadığında), söz konusu öğeyi ayıklamadan da duraklar. İşlev hiçbir öğe ayıklaıyorsa, [SetState](../standard-library/basic-ios-class.md#setstate)(`failbit`) öğesini çağırır. Herhangi bir durumda, işlev  **\*bunu**döndürür.

İşlev:

```cpp
basic_istream& operator>>(bool& val);
```

bir alanı ayıklar ve [use_facet](../standard-library/basic-filebuf-class.md#open)  <  `num_get`  [](../standard-library/ios-base-class.md#getloc) eled, INIT > (getloc) çağırarak bir Boole değerine dönüştürür.\< [Al](../standard-library/ios-base-class.md#getloc) ( **INIT**( [rdarabelleğe](../standard-library/basic-ios-class.md#rdbuf)), `Init`(0),  **\*bu**, `getloc`, `val`). Burada **INIT** , [istreambuf_iterator](../standard-library/istreambuf-iterator-class.md) \< **eled**, **tr**> olarak tanımlanır. İşlevi  **\*bunu**döndürür.

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

her biri bir alanı ayıklar ve **eled**, **INIT**> ( `getloc`) `use_facet` çağırarak <  `num_get` \< bir sayısal değere dönüştürür. [Al](#get) ( **INIT**( `rdbuf`), `Init`(0),  **\*bu**, `getloc`, `val`). Burada **INIT** , **eled**, `istreambuf_iterator` **tr**> olarak `val` \< tanımlanır ve gereken tür **Long**, **unsigned long**veya **void** <strong>\*</strong> olur.

Dönüştürülmüş değer türü `val`olarak temsil edilemiyorsa, işlev [SetState](../standard-library/basic-ios-class.md#setstate)(`failbit`) yöntemini çağırır. Herhangi bir durumda, işlev  **\*bunu**döndürür.

İşlevler:

```cpp
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```

her biri bir alanı ayıklar ve **eled**, **INIT**> ( `getloc`) `use_facet` çağırarak <  `num_get` \< bir sayısal değere dönüştürür. **Al** ( **INIT**( `rdbuf`), `Init`(0),  **\*bu**, `getloc`, `val`). Burada, `InIt` **eled**, `istreambuf_iterator` **tr**> olarak \< tanımlanır ve `val` gerektiğinde **Double** veya **Long Double** türü vardır.

Dönüştürülmüş değer türü `val`olarak temsil edilemiyorsa, işlev çağırır `setstate`( **failbit**). Herhangi bir durumda,  **\*bunu döndürür.**

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

`basic_istream` İşlecin sağ tarafına bu nesneye atar. Bu, arkasına kopya bırakmayan bir `rvalue` başvuruyu içeren bir taşıma atamasıdır.

```cpp
basic_istream& operator=(basic_istream&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`rvalue` Bir`basic_ifstream` nesneye başvuru.

### <a name="return-value"></a>Dönüş Değeri

\* This döndürür.

### <a name="remarks"></a>Açıklamalar

Member işleci Swap `( right)`öğesini çağırır.

## <a name="peek"></a>basic_istream::p EEK

Okunacak sonraki karakteri döndürür.

```cpp
int_type peek();
```

### <a name="return-value"></a>Dönüş Değeri

Okunacak sonraki karakter.

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş giriş işlevi, mümkünse `rdbuf` [sgetc](../standard-library/basic-streambuf-class.md#sgetc)döndüren  -> gibi bir öğeyi ayıklar. Aksi takdirde, **traits_type::** [EOF](../standard-library/char-traits-struct.md#eof)döndürür.

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
basic_istream<Elem, Tr>& putback(
    char_type Ch);
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Akışa geri yerleştirilecek bir karakter.

### <a name="return-value"></a>Dönüş Değeri

Stream (  **\*this**).

### <a name="remarks"></a>Açıklamalar

[Biçimlendirilmemiş giriş işlevi](../standard-library/basic-istream-class.md) , mümkünse, [rdarabelleğe](../standard-library/basic-ios-class.md#rdbuf)`->`[sputbackc](../standard-library/basic-streambuf-class.md#sputbackc)çağırarak olduğu *gibi geri alır*. Rdarabelleğe `sputbackc` null bir işaretçisiyse veya çağrısı **traits_type::** [EOF](../standard-library/char-traits-struct.md#eof)döndürürse, işlev [SetState](../standard-library/basic-ios-class.md#setstate)(`badbit`) öğesini çağırır. Herhangi bir durumda,  **\*bunu döndürür.**

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
basic_istream<Elem, Tr>& read(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
Karakterlerin okunacağı dizi.

*biriktirme*\
Okunacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Stream ( `*this`).

### <a name="remarks"></a>Açıklamalar

Biçimlendirilmemiş giriş işlevi, öğeleri *saymak* için ayıklar ve diziliden `Str`başlayarak dizi içinde depolar. Ayıklama işlemi dosya sonundan erken durduruluyor, bu durumda işlev [SetState](../standard-library/basic-ios-class.md#setstate)(`failbit`) öğesini çağırır. Herhangi bir durumda, döndürür `*this`.

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

*üstbilgisine*\
İçinde okuduğu karakterleri `readsome` depolayan dizi.

*biriktirme*\
Okunacak karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Gerçekten okunan karakter sayısı, [gcount](#gcount).

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
basic_istream<Elem, Tr>& seekg(pos_type pos);

basic_istream<Elem, Tr>& seekg(off_type off, ios_base::seekdir way);
```

### <a name="parameters"></a>Parametreler

*'un*\
Okuma işaretçisinin taşınacağı mutlak konum.

*dışına*\
Okuma işaretçisini göreli olarak taşımaya yönelik bir göreli *yol*.

*yapmanın*\
[İos_base:: seekdir](../standard-library/ios-base-class.md#seekdir) Numaralandırmalardan biri.

### <a name="return-value"></a>Dönüş Değeri

Stream (  **\*this**).

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi mutlak bir arama gerçekleştirir, ikinci üye işlevi göreli bir arama gerçekleştirir.

> [!NOTE]
> Standart C++ metin dosyalarında göreli aramalar desteklemediğinden, ikinci üye işlevi metin dosyalarıyla birlikte kullanmayın.

[Başarısız](../standard-library/basic-ios-class.md#fail) olursa, ilk üye işlevi bazı ->  `pos` geçicinesneler`newpos`için **newpos** = [rdarabelleğe](../standard-library/basic-ios-class.md#rdbuf)pubseekpos () yöntemini çağırır.[](../standard-library/basic-streambuf-class.md#pubseekpos) `pos_type`  =  `off` ->  `way` [](../standard-library/basic-streambuf-class.md#pubseekoff)Yanlışsa, ikinci işlev newpos rdarabelleğe pubseekoff (,) yöntemini çağırır. `fail` Her iki durumda da `off_type`() **newpos** = = ( `off_type`) (-1) (konumlandırma işlemi başarısız olursa), işlev çağırır. `istr` [SetState](../standard-library/basic-ios-class.md#setstate) (`failbit`). Her iki işlev de  **\*bunu**döndürür.

[Başarısız](../standard-library/basic-ios-class.md#fail) olursa üye işlevleri hiçbir şey yapmaz.

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

sınıf Sentry {public: Explicit Sentry (basic_istream\<eled, tr > & _Istr, bool _noskip = false); operator bool () const;};

### <a name="remarks"></a>Açıklamalar

Eğer `_Istr.` [iyi](../standard-library/basic-ios-class.md#good) doğru ise, Oluşturucu:

- Çağırır `_Istr`. [](../standard-library/basic-ios-class.md#tie)if ise Flush`_Istr`.[](../standard-library/basic-ostream-class.md#flush)  ->  `tie`null işaretçi değil

- , `_Istr` [](../standard-library/istream-functions.md#ws) EtkinolarakWS()`_Istr`çağırır. [](../standard-library/ios-base-class.md#flags) **&** [skipws](../standard-library/ios-functions.md#skipws) bayrakları sıfır dışı

Varsa, bu tür bir hazırlığından `_Istr`sonra. `good`yanlış, oluşturucu çağırır `_Istr`. [SetState](../standard-library/basic-ios-class.md#setstate) (`failbit`). Herhangi bir durumda, Oluşturucu tarafından `_Istr`döndürülen değeri depolar. `good`içinde `status`. Daha sonraki bir çağrı `operator bool` , bu depolanmış değeri teslim eder.

## <a name="swap"></a>basic_istream:: swap

İki `basic_istream` nesnenin içeriğini değiş tokuş eder.

```cpp
void swap(basic_istream& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir `basic_istream` nesneye lvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [basic_ios:: Swap](../standard-library/basic-ios-class.md#swap)`(right)`öğesini çağırır. Ayrıca ayıklama sayısını *sağ*için ayıklama sayısı ile de değiştirir.

## <a name="sync"></a>basic_istream:: Sync

Akış ile ilişkili giriş cihazını akışın arabelleğine eşitler.

```cpp
int sync();
```

### <a name="return-value"></a>Dönüş Değeri

[Rdarabelleğe](../standard-library/basic-ios-class.md#rdbuf) null bir işaretçisiyse, işlev-1 döndürür. Aksi takdirde, `rdbuf` [pubsync](../standard-library/basic-streambuf-class.md#pubsync)öğesini çağırır.  ->  Eğer-1 döndürürse, işlev [SetState](../standard-library/basic-ios-class.md#setstate)(`badbit`) öğesini çağırır ve-1 döndürür. Aksi takdirde, işlev sıfır döndürür.

## <a name="tellg"></a>basic_istream:: tellg

Akıştaki geçerli okuma konumunu raporlar.

```cpp
pos_type tellg();
```

### <a name="return-value"></a>Dönüş Değeri

Akıştaki geçerli konum.

### <a name="remarks"></a>Açıklamalar

[Başarısız](../standard-library/basic-ios-class.md#fail) olursa, üye işlevi [rdarabelleğe](../standard-library/basic-ios-class.md#rdbuf) -> [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(0, `cur` **içinde**) döndürür. Aksi takdirde, ( `pos_type`-1) döndürür.

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
basic_istream<Elem, Tr>& unget();
```

### <a name="return-value"></a>Dönüş Değeri

Stream (  **\*this**).

### <a name="remarks"></a>Açıklamalar

[Biçimlendirilmemiş giriş işlevi](../standard-library/basic-istream-class.md) , mümkünse, `rdbuf` [sungetc](../standard-library/basic-streambuf-class.md#sungetc)'yi çağırarak  -> , varsa akışta önceki öğeyi geri koyar. [Rdarabelleğe](../standard-library/basic-ios-class.md#rdbuf) null bir işaretçisiyse veya `sungetc` çağrısı **traits_type::** [EOF](../standard-library/basic-ios-class.md#eof)döndürürse, işlev [SetState](../standard-library/basic-ios-class.md#setstate)(`badbit`) öğesini çağırır. Herhangi bir durumda,  **\*bunu döndürür.**

Nasıl `unget` başarısız olabileceği hakkında bilgi için bkz. [basic_streambuf:: sungetc](../standard-library/basic-streambuf-class.md#sungetc).

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

[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
