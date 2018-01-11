---
title: "basic_istream sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
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
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 14f41a90aab8e95d336df6724a7217947ec1c57c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="basicistream-class"></a>basic_istream Sınıfı
Ayıklama öğelerinin denetleyen bir nesne ve akış arabellek türündeki öğeler ile kodlanmış nesnelerden açıklar `Elem`, olarak da bilinen [char_type](../standard-library/basic-ios-class.md#char_type), olan karakter nitelikler sınıfı tarafından belirlenir *Tr* , olarak da bilinen [traits_type](../standard-library/basic-ios-class.md#traits_type).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_istream : virtual public basic_ios<Elem, Tr>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Üye çoğu, aşırı işlevleri [işleci >>](#op_gt_gt) giriş işlevleri biçimlendirilir. Bunlar düzeni uygular:  
  
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
  
 Diğer birçok üye işlevleri biçimlendirilmemiş giriş işlevlerdir. Bunlar düzeni uygular:  
  
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
  
 İşlev çağrısının her iki grup [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**) öğeleri ayıklanırken dosya sonu karşılaşmaları durumunda.  
  
 Sınıfın bir nesnesi `basic_istream` <  `Elem`, *Tr*> depolar:  
  
-   Sanal ortak temel sınıfından bir nesne [basic_ios](../standard-library/basic-ios-class.md)< `Elem`, *Tr*> `.`  
  
-   Son biçimlendirilmemiş giriş işlemi için bir çıkarma sayısı (adlı **sayısı** önceki kodda).  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [basic_ifstream sınıfı](../standard-library/basic-ifstream-class.md) giriş akışları hakkında daha fazla bilgi edinmek için.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[basic_istream](#basic_istream)|Türünde bir nesne oluşturur `basic_istream`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[gcount](#gcount)|Karakterlerin sayısını döndürür son biçimlendirilmemiş giriş sırasında okuyun.|  
|[get](#get)|Bir veya daha fazla karakter giriş akışından okur.|  
|[getline](#getline)|Bir satır giriş akışından okur.|  
|[Yoksay](#ignore)|Geçerli konumu okuma Atlanan öğe sayısı neden olur.|  
|[Peek](#peek)|Okunacak sonraki karakteri döndürür.|  
|[putback](#putback)|Belirtilen bir karakterin akışa koyar.|  
|[read](#read)|Akıştan belirtilen sayıda karakteri okur ve onları bir dizide depolar.|  
|[readsome](#readsome)|Yalnızca arabelleğinden okuyun.|  
|[seekg](#seekg)|Bir akış okuma konuma taşır.|  
|[sentry](#sentry)|İç içe geçmiş sınıf bir nesne, bildirim biçimlendirilmiş giriş işlevleri ve biçimlendirilmemiş giriş işlevleri yapıları açıklar.|  
|[değiştirme](#swap)|Bu alış verişleri `basic_istream` için sağlanan nesne `basic_istream` parametre nesnesi.|  
|[Eşitleme](#sync)|Akış akışın arabelleği ile ilişkili giriş cihazı eşitler.|  
|[tellg](#tellg)|Geçerli akış konumda okuma bildirir.|  
|[unget](#unget)|Geçirir en son geri akışa karakter okuyun.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[İşleç >>](#op_gt_gt)|Giriş akışı üzerinde bir işlev çağrıları veya giriş akışından biçimlendirilmiş verileri okur.|  
|[işleç =](#op_eq)|Atar `basic_istream` bu nesneye işlecinin sağ tarafında. Bu taşıma atama ilgili olan bir `rvalue` kopyasını bırakmaz arkasında başvuru.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<IStream >  
  
 **Namespace:** std  
  
##  <a name="basic_istream"></a>basic_istream::basic_istream  
 Türünde bir nesne oluşturur `basic_istream`.  
  
```  
explicit basic_istream(
    basic_streambuf<Elem, Tr>* strbuf,  
    bool _Isstd = false);

basic_istream(basic_istream&& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `strbuf`  
 Türünde bir nesne [basic_streambuf](../standard-library/basic-streambuf-class.md).  
  
 `_Isstd`  
 `true`Bu standart bir akış ise; Aksi takdirde `false`.  
  
 `right`  
 A `basic_istream` kopyalamak için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucu çağırarak temel sınıfı başlatır [init](../standard-library/basic-ios-class.md#init)(_Yanları `trbuf`). Ayrıca, ayıklama sayısı sıfır depolar. Bu ayıklama sayısı hakkında daha fazla bilgi için Açıklamalar bölümüne bakın [basic_istream sınıfı](../standard-library/basic-istream-class.md) genel bakış konusunun.  
  
 İkinci oluşturucu çağırarak temel sınıfı başlatır `move( right)`. Ayrıca _R depolar `ight.gcount()` ayıklama sayısı ve sıfır ayıklama sayısı için depolar _R `ight`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [basic_ifstream::basic_ifstream](../standard-library/basic-ifstream-class.md#basic_ifstream) giriş akışları hakkında daha fazla bilgi edinmek için.  
  
##  <a name="gcount"></a>basic_istream::gcount  
 Karakterlerin sayısını döndürür son biçimlendirilmemiş giriş sırasında okuyun.  
  
```  
streamsize gcount() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayıklama sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [basic_istream::get](#get) biçimlendirilmemiş karakter okunamıyor.  
  
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
  
```Output  
  
a  
  
```  
  
```Output  
  
      aType the letter 'a':  
a  
1  
```  
  
##  <a name="get"></a>basic_istream::get  
 Bir veya daha fazla karakter giriş akışından okur.  
  
```  
int_type get();

basic_istream<Elem, Tr>& get(Elem& Ch);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count, Elem Delim);

basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf);
basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf, Elem Delim);
```  
  
### <a name="parameters"></a>Parametreler  
 `count`  
 Okunacak karakter sayısını `strbuf`.  
  
 `Delim`  
 Önce karşılaşılırsa, okuma sonlanmalıdır karakter `count`.  
  
 `str`  
 Bir dize yazmak üzere.  
  
 `Ch`  
 Alınacak karakter.  
  
 `strbuf`  
 Arabellekte yazılacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Get parametresiz biçiminde bir tamsayı veya dosya sonu olarak okuma öğesi döndürür. Akış kalan forms Döndür (* `this`).  
  
### <a name="remarks"></a>Açıklamalar  
 İlk bu biçimlendirilmemiş giriş işlevlerin bir öğe Mümkünse, sanki göre döndürme ayıklar `rdbuf` ->  `sbumpc`. Aksi takdirde, döndürür **traits_type::**[eof](../standard-library/char-traits-struct.md#eof). Hiçbir öğe işlevi ayıklar, çağıran [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**).  
  
 İkinci işlev ayıklar [int_type](../standard-library/basic-ios-class.md#int_type) öğesi `meta` aynı şekilde. Varsa `meta` karşılaştırır eşit **traits_type::eof**, işlev çağrıları `setstate`( **failbit**). Aksi takdirde, depolar **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)( `meta`) içinde `Ch`. İşlevi döndürür  **\*bu**.  
  
 Üçüncü işlevi döndürür **almak**(_ *Str*, `count`, `widen`('\  **n** ')).  
  
 Dördüncü işlevi kadar ayıklar `count` - 1 öğeleri ve _ dizi başında depolar *Str*. Her zaman depolar `char_type` herhangi depoladığı öğeleri ayıklanan sonra. Sınama sırayla ayıklama durdurur:  
  
-   Dosya sonu.  
  
-   Eşit karşılaştıran bir öğe işlevi ayıklar sonra `Delim`, öğe denetimli dizisi geri; bu durumda yerleştirin.  
  
-   İşlev ayıklar sonra `count` - 1 öğeleri.  
  
 Öğe işlevi ayıklar, çağıran `setstate`( **failbit**). Her iki durumda da döndürür  **\*bu**.  
  
 Beşinci işlevi döndürür **almak**( **strbuf**, `widen`('\  **n** ')).  
  
 Altıncı işlevi öğeleri ayıklar ve bunları ekler **strbuf**. Ayıklama durdurur dosya sonu veya _ eşit karşılaştıran bir öğede *Delim,* hangi değil ayıklanır. Bu ayrıca, bir ekleme başarısız olursa veya (hangi yakalanan ancak değil işlenemezse) bir özel durum oluşturur, söz konusu öğeyi ayıklanıyor olmadan durdurur. Öğe işlevi ayıklar, çağıran `setstate`( **failbit**). Her iki durumda da işlevi döndürür  **\*bu**.  
  
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
  
##  <a name="getline"></a>basic_istream::getline  
 Giriş akışından bir satır alır.  
  
```  
basic_istream<Elem, Tr>& getline(
    char_type* str,   
    streamsize count);

basic_istream<Elem, Tr>& getline(
    char_type* str,   
    streamsize count,   
    char_type Delim);
```  
  
### <a name="parameters"></a>Parametreler  
 `count`  
 Okunacak karakter sayısını **strbuf**.  
  
 `Delim`  
 Önce karşılaşılırsa, okuma sonlanmalıdır karakter `count`.  
  
 `str`  
 Bir dize yazmak üzere.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akış (  **\*bu**).  
  
### <a name="remarks"></a>Açıklamalar  
 Biçimlendirilmemiş Bunlardan ilki giriş işlevleri döndürür **getline**(_ *Str*, `count`, `widen`(' `\`  **n** ')).  
  
 İkinci işlev kadar ayıklar `count` - 1 öğeleri ve _ dizi başında depolar *Str*. Her zaman dize sonlandırma karakter depoladığı ayıklanan öğelerden sonra depolar. Sınama sırayla ayıklama durdurur:  
  
-   Dosya sonu.  
  
-   Eşit karşılaştıran bir öğe işlevi ayıklar sonra `Delim`, bu durumda öğesi ne geri alın, ne de denetimli dizisi eklenmiş.  
  
-   İşlev ayıklar sonra `count` - 1 öğeleri.  
  
 Öğe işlevi ayıklar varsa veya `count` - 1 öğeleri çağırır [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**). Her iki durumda da döndürür  **\*bu**.  
  
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
  
##  <a name="ignore"></a>basic_istream::ignore  
 Geçerli konumu okuma Atlanan öğe sayısı neden olur.  
  
```  
basic_istream<Elem, Tr>& ignore(
    streamsize count = 1,  
    int_type Delim = traits_type::eof());
```  
  
### <a name="parameters"></a>Parametreler  
 `count`  
 Geçerli okuma konumdan atlamak için öğe sayısı.  
  
 `Delim`  
 Sayısı önce karşılaştıysanız neden olan öğe **Yoksay** dönün ve sonra tüm öğeleri vererek `Delim` okumak için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akış (  **\*bu**).  
  
### <a name="remarks"></a>Açıklamalar  
 Biçimlendirilmemiş Giriş işlevi kadar ayıklar `count` öğeleri ve bunları atar. Varsa `count` eşittir **numeric_limits\<int >:: max**, ancak bunun gibi büyük alınır. Ayıklama durdurur erken dosya sonu veya öğenin `Ch` şekilde **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( `Ch`) karşılaştırır eşit *Delim* (hangi Ayrıca ayıklanan). İşlevi döndürür  **\*bu**.  
  
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
  
##  <a name="op_gt_gt"></a>temel\_istream::operator >>
  
Giriş akışı üzerinde bir işlev çağrıları veya giriş akışından biçimlendirilmiş verileri okur.  
  
```  
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
 `Pfn`  
 Bir işlev işaretçisi.  
  
 `strbuf`  
 Türünde bir nesne **stream_buf**.  
  
 `val`  
 Akıştan okunan değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akış (  **\*bu**).  
  
### <a name="remarks"></a>Açıklamalar  
 `<istream>` Üstbilgisi ayrıca çeşitli genel ayıklama işleçlerini tanımlar. Daha fazla bilgi için bkz: [işleci >> (\<IStream >)](../standard-library/istream-operators.md#op_gt_gt).  
  
 İlk üye işlevi biçiminde bir ifade sağlar **istr**  >>  `ws` çağrıları [ws](../standard-library/istream-functions.md#ws)( **istr**) ve ardından döndürür  **\*bu**. İkinci ve üçüncü işlevleri gibi diğer manipülatörleri olun [onaltılık](../standard-library/ios-functions.md#hex), benzer şekilde davranır. Kalan işlevleri biçimlendirilmiş giriş işlevleri oluşturur.  
  
 İşlev:  
  
```  
basic_istream& operator>>(
    basic_streambuf<Elem, Tr>* strbuf);
```  
  
 varsa öğeleri ayıklar _ *Strbuf* null işaretçi değildir ve bunların ekler `strbuf`. Ayıklama dosya sonu üzerinde durdurur. Ayrıca, bir ekleme başarısız olursa veya (hangi yakalanan ancak değil işlenemezse) bir özel durum oluşturur, söz konusu öğeyi ayıklanıyor olmadan durdurur. Öğe işlevi ayıklar, çağıran [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**). Her iki durumda da işlevi döndürür  **\*bu**.  
  
 İşlev:  
  
```  
basic_istream& operator>>(bool& val);
```  
  
 bir alan ayıklar ve çağırarak bir Boolean değerine dönüştürür [use_facet](../standard-library/basic-filebuf-class.md#open)  <  `num_get` \< **Elem**, **InIt**> ( [getloc](../standard-library/ios-base-class.md#getloc)). [Alma](../standard-library/ios-base-class.md#getloc)( **InIt**( [rdbuf](../standard-library/basic-ios-class.md#rdbuf)), `Init`(0),  **\*bu**, `getloc`, `val`). Burada, **InIt** olarak tanımlanan [istreambuf_iterator](../standard-library/istreambuf-iterator-class.md) \< **Elem**, **Tr**>. İşlevi döndürür  **\*bu**.  
  
 İşlevler:  
  
```  
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
  
 Her bir alan ayıklayın ve çağırarak sayısal değer Dönüştür `use_facet` <  `num_get` \< **Elem**, **InIt**> ( `getloc`). [Alma](#get)( **InIt**( `rdbuf`), `Init`(0),  **\*bu**, `getloc`, `val`). Burada, **InIt** olarak tanımlanan `istreambuf_iterator` \< **Elem**, **Tr**>, ve `val` türüne sahip **uzun**,`unsigned long`, veya **void \***  gerektiğinde.  
  
 Dönüştürülen değer türü olarak temsil edilemez `val`, işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**). Her iki durumda da işlevi döndürür  **\*bu**.  
  
 İşlevler:  
  
```  
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```  
  
 Her bir alan ayıklayın ve çağırarak sayısal değer Dönüştür `use_facet` <  `num_get` \< **Elem**, **InIt**> ( `getloc`). **Alma**( **InIt**( `rdbuf`), `Init`(0),  **\*bu**, `getloc`, `val`). Burada, **InIt** olarak tanımlanan `istreambuf_iterator` \< **Elem**, **Tr**>, ve `val` türüne sahip **çift** veya `long double` gerektiğinde.  
  
 Dönüştürülen değer türü olarak temsil edilemez `val`, işlev çağrıları `setstate`( **failbit**). Her iki durumda da döndürür  **\*bu**.  
  
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
  
##  <a name="op_eq"></a>basic_istream::operator =  
 Atar `basic_istream` bu nesneye işlecinin sağ tarafında. Bu taşıma atama ilgili olan bir `rvalue` kopyasını bırakmaz arkasında başvuru.  
  
```  
basic_istream& operator=(basic_istream&& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Bir `rvalue` başvuru bir `basic_ifstream` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür * bu.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci çağırır takas `( right)`.  
  
##  <a name="peek"></a>basic_istream::Peek  
 Okunacak sonraki karakteri döndürür.  
  
```  
int_type peek();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Okunacak sonraki karakteri.  
  
### <a name="remarks"></a>Açıklamalar  
 Biçimlendirilmemiş Giriş işlevi bir öğe Mümkünse, sanki göre döndürme ayıklar `rdbuf`  ->  [sgetc](../standard-library/basic-streambuf-class.md#sgetc). Aksi takdirde, döndürür **traits_type::**[eof](../standard-library/char-traits-struct.md#eof).  
  
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
  
```Output  
  
abcde  
  
```  
  
```Output  
  
      abcdeType 'abcde': abcde  
a abcde  
```  
  
##  <a name="putback"></a>basic_istream::putback  
 Belirtilen bir karakterin akışa koyar.  
  
```  
basic_istream<Elem, Tr>& putback(
    char_type Ch);
```  
  
### <a name="parameters"></a>Parametreler  
 `Ch`  
 Akışa geri almaya karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akış (  **\*bu**).  
  
### <a name="remarks"></a>Açıklamalar  
 [Biçimlendirilmemiş Giriş işlevi](../standard-library/basic-istream-class.md) geri koyar `Ch`, mümkünse, göre çağırma sanki [rdbuf](../standard-library/basic-ios-class.md#rdbuf)`->`[sputbackc](../standard-library/basic-streambuf-class.md#sputbackc). Rdbuf null işaretçi olması veya çağrısı `sputbackc` döndürür **traits_type::**[eof](../standard-library/char-traits-struct.md#eof), işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)( **badbit**). Her iki durumda da döndürür  **\*bu**.  
  
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
  
##  <a name="read"></a>basic_istream::Read  
 Akıştan belirtilen sayıda karakteri okur ve onları bir dizide depolar.  
  
 Geçirilen değerlerin doğru olduğunu kontrol etmek için arayan alacağından bu büyük olasılıkla güvensiz bir yöntemdir.  
  
```  
basic_istream<Elem, Tr>& read(
    char_type* str,   
    streamsize count);
```  
  
### <a name="parameters"></a>Parametreler  
 `str`  
 Karakterleri okumak üzere dizisi.  
  
 `count`  
 Okunacak karakter sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akış ( `*this`).  
  
### <a name="remarks"></a>Açıklamalar  
 Biçimlendirilmemiş Giriş işlevi kadar ayıklar `count` öğeleri ve _ dizi başında depolar `Str`. Ayıklama durdurur erken çalışması işlevi çağıran dosya sonu üzerinde [setstate](../standard-library/basic-ios-class.md#setstate)( `failbit`). Her iki durumda da döndürür `*this`.  
  
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
  
```Output  
  
abcde  
  
```  
  
```Output  
  
      abcdeType 'abcde': abcde  
abcde  
```  
  
##  <a name="readsome"></a>basic_istream::readsome  
 Belirtilen sayıda karakter değerleri okur.  
  
 Geçirilen değerlerin doğru olduğunu kontrol etmek için arayan alacağından bu büyük olasılıkla güvensiz bir yöntemdir.  
  
```  
streamsize readsome(
    char_type* str,  
    streamsize count);
```  
  
### <a name="parameters"></a>Parametreler  
 `str`  
 Dizideki `readsome` bunu okuyan karakterleri saklar.  
  
 `count`  
 Okunacak karakter sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gerçekte okunan karakter sayısı [gcount](#gcount).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu biçimlendirilmemiş Giriş işlevi kadar ayıklar `count` giriş öğelerinden akış ve bunları dizideki depolar `str`.  
  
 Bu işlev için giriş beklemez. Bu, hangi veri kullanılabilir okur.  
  
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
  
##  <a name="seekg"></a>basic_istream::seekg  
 Bir akış okuma konuma taşır.  
  
```  
basic_istream<Elem, Tr>& seekg(pos_type pos);

basic_istream<Elem, Tr>& seekg(off_type off, ios_base::seekdir way);
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Hangi okuma işaretçiyi taşımak mutlak konumu.  
  
 `off`  
 Okuma işaretçiyi göreli olarak taşımak için bir uzaklık `way`.  
  
 `way`  
 Aşağıdakilerden birini [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir) numaralandırmalar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akış (  **\*bu**).  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi mutlak bir arama gerçekleştirir, göreli bir arama ikinci üye işlevi gerçekleştirir.  
  
> [!NOTE]
>  İkinci üye işlevi metin dosyalarını kullanmaz, standart C++ desteklemediğinden göreli metin dosyaları arar.  
  
 Varsa [başarısız](../standard-library/basic-ios-class.md#fail) false, ilk üye işlev çağrılarını **newpos** = [rdbuf](../standard-library/basic-ios-class.md#rdbuf) -> [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)( `pos`), bazı **pos_type** geçici nesne **newpos**. Varsa **başarısız** false, ikinci işlev çağrılarını **newpos** = **rdbuf** -> [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)( `off`, `way`). Her iki durumda da, ( `off_type`) **newpos** == ( `off_type`)(-1) (yerleştirme işlemi başarısız oldu), işlev çağrıları **istr**. [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**). Her iki işlevi dönüş  **\*bu**.  
  
 Varsa [başarısız](../standard-library/basic-ios-class.md#fail) üye işlevleri hiçbir şey yapmak true olur.  
  
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
  
##  <a name="sentry"></a>basic_istream::sentry  
 İç içe geçmiş sınıf bir nesne, bildirim biçimlendirilmiş ve biçimlendirilmemiş giriş işlevleri yapıları açıklar.  
  
sınıf sentry {  
   Ortak:  
   Açık sentry (basic_istream\<Elem, Tr > & _Istr,  
   bool _Noskip = false); işleç bool() const; };  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `_Istr.` [iyi](../standard-library/basic-ios-class.md#good) doğrudur Oluşturucusu:  
  
-   Çağrıları `_Istr`. [tie](../standard-library/basic-ios-class.md#tie) -> [Temizleme](../standard-library/basic-ostream-class.md#flush) varsa `_Istr`. `tie`null işaretçinin değil  
  
-   Etkili bir şekilde çağırır [ws](../standard-library/istream-functions.md#ws)( `_Istr`) varsa `_Istr`. [bayrakları](../standard-library/ios-base-class.md#flags)**&**[skipws](../standard-library/ios-functions.md#skipws) sıfır olmayan bir değer değil  
  
 Eğer, böyle herhangi bir hazırlık sonra `_Istr`. **iyi** false, oluşturucu çağrıları `_Istr`. [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**). Oluşturucu tarafından döndürülen değer her iki durumda da depolar `_Istr`. **iyi** içinde **durum**. Sonraki çağrı **işleç bool değeri** Bu saklı değer sunar.  
  
##  <a name="swap"></a>basic_istream::Swap  
 İki içeriğini alış verişleri `basic_istream` nesneleri.  
  
```  
void swap(basic_istream& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Lvalue başvuru için bir `basic_istream` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlev çağrılarını [basic_ios::swap](../standard-library/basic-ios-class.md#swap)`(right)`. Ayrıca ayıklama count için ayıklama sayısı ile alış verişleri `right`.  
  
##  <a name="sync"></a>basic_istream::Sync  
 Akış akışın arabelleği ile ilişkili giriş cihazı eşitler.  
  
```  
int sync();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsa [rdbuf](../standard-library/basic-ios-class.md#rdbuf) null işaretçi işlevi -1 döndürür. Aksi takdirde, çağıran `rdbuf`  ->  [pubsync](../standard-library/basic-streambuf-class.md#pubsync). -1 değeri döndürülürse, işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)( **badbit**) ve -1 döndürür. Aksi takdirde işlevi sıfır döndürür.  
  
##  <a name="tellg"></a>basic_istream::tellg  
 Geçerli akış konumda okuma bildirir.  
  
```  
pos_type tellg();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akış geçerli konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa [başarısız](../standard-library/basic-ios-class.md#fail) üye fonksiyonu verir, yanlış [rdbuf](../standard-library/basic-ios-class.md#rdbuf) -> [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(0, `cur`, **içinde**). Aksi takdirde, döndürür `pos_type`(-1).  
  
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
  
##  <a name="unget"></a>basic_istream::unget  
 Geçirir en son geri akışa karakter okuyun.  
  
```  
basic_istream<Elem, Tr>& unget();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akış (  **\*bu**).  
  
### <a name="remarks"></a>Açıklamalar  
 [Biçimlendirilmemiş Giriş işlevi](../standard-library/basic-istream-class.md) geri önceki öğesi akışında Mümkünse, göre çağırma gibi koyar `rdbuf`  ->  [sungetc](../standard-library/basic-streambuf-class.md#sungetc). Varsa [rdbuf](../standard-library/basic-ios-class.md#rdbuf) null işaretçinin veya çağrısı `sungetc` döndürür **traits_type::**[eof](../standard-library/basic-ios-class.md#eof), işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)() **badbit**). Her iki durumda da döndürür  **\*bu**.  
  
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
  
```Output  
  
abc  
  
```  
  
```Output  
  
      abcType 'abc': abc  
abc  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream programlama](../standard-library/iostream-programming.md)   
 [iostreams Kuralları](../standard-library/iostreams-conventions.md)

