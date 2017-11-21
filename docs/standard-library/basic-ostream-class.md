---
title: "basic_ostream sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ostream/std::basic_ostream
- ostream/std::basic_ostream::flush
- ostream/std::basic_ostream::put
- ostream/std::basic_ostream::seekp
- ostream/std::basic_ostream::sentry
- ostream/std::basic_ostream::swap
- ostream/std::basic_ostream::tellp
- ostream/std::basic_ostream::write
dev_langs: C++
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
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3834e557b4060fd214be137490580412fd2902b6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="basicostream-class"></a>basic_ostream Sınıfı
Bu şablon sınıfı türündeki öğeler ile Akış Arabellek içine ekleme öğelerinin denetleyen bir nesne ve kodlanmış nesneleri açıklar **Elem**, olarak da bilinen [char_type](../standard-library/basic-ios-class.md#char_type), olan karakter nitelikler olan sınıfı tarafından belirlenen **Tr**, olarak da bilinen [traits_type](../standard-library/basic-ios-class.md#traits_type).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_ostream : virtual public basic_ios<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Elem`  
 A `char_type`.  
  
 `Tr`  
 Karakter `traits_type`.  
  
## <a name="remarks"></a>Açıklamalar  
 Üye çoğu, aşırı işlevleri [işleci <<](#op_lt_lt) biçimlendirilmiş çıkışı işlevlerdir. Bunlar düzeni uygular:  
  
```  
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
  
 Diğer iki üye işlevleri biçimlendirilmemiş çıkış işlevlerdir. Bunlar düzeni uygular:  
  
```  
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
  
 İşlev çağrısının her iki grup [setstate](../standard-library/basic-ios-class.md#setstate)**(badbit)** öğeleri eklenirken bir hata karşılaşmaları durumunda.  
  
 Bir nesne sınıfı basic_istream\< **Elem**, **Tr**> yalnızca sanal ortak temel sınıfından bir nesne depolar [basic_ios](../standard-library/basic-ios-class.md)  **\<Elem**, **Tr >**.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [basic_ofstream sınıfı](../standard-library/basic-ofstream-class.md) çıkış akışları hakkında daha fazla bilgi edinmek için.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[basic_ostream](#basic_ostream)|Oluşturan bir `basic_ostream` nesnesi.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[Temizleme](#flush)|Arabelleği temizler.|  
|[yerleştirme](#put)|Bir karakterin bir akışa koyar.|  
|[seekp](#seekp)|Çıkış akışı konumu sıfırlar.|  
|[sentry](#sentry)|İç içe geçmiş sınıf bir nesne, bildirim biçimlendirilmiş çıkış işlevleri ve biçimlendirilmemiş çıkış işlevleri yapıları açıklar.|  
|[değiştirme](#op_eq)|Bu değerleri alış verişleri `basic_ostream` nesne için sağlanan içeriğiyle `basic_ostream` nesnesi.|  
|[tellp](#tellp)|Çıkış akışı konumu raporlar.|  
|[yazma](#write)|Karakterini bir akışa yapar.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](#basic_ostream_operator_eq)|Sağlanan değeri atar `basic_ostream` parametresi bu nesneye nesne.|  
|[işleç <<](#basic_ostream_operator_lt_lt)|Akışa yazar.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<ostream >  
  
 **Namespace:** std  
  
##  <a name="basic_ostream"></a>basic_ostream::basic_ostream  
 Oluşturan bir `basic_ostream` nesnesi.  
  
```  
explicit basic_ostream(
    basic_streambuf<Elem, Tr>* strbuf,  
    bool _Isstd = false);

basic_ostream(basic_ostream&& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `strbuf`  
 Türünde bir nesne [basic_streambuf](../standard-library/basic-streambuf-class.md).  
  
 `_Isstd`  
 `true`Bu standart bir akış ise; Aksi takdirde `false`.  
  
 `right`  
 Rvalue başvuru türünde bir nesneye `basic_ostream`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucu çağırarak temel sınıfı başlatır [init](../standard-library/basic-ios-class.md#init)(`strbuf`). İkinci oluşturucu çağırarak temel sınıfı başlatır [basic_ios::move](../standard-library/basic-ios-class.md#move)`(right)`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) çıkış akışları hakkında daha fazla bilgi edinmek için.  
  
##  <a name="flush"></a>basic_ostream::flush  
 Arabelleği temizler.  
  
```  
basic_ostream<Elem, Tr>& flush();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Basic_ostream nesneye başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa [rdbuf](../standard-library/basic-ios-class.md#rdbuf) işlev çağrıları null işaretçi değil **rdbuf ->**[pubsync](../standard-library/basic-streambuf-class.md#pubsync). -1 değeri döndürülürse, işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)(**badbit**). Döndürdüğü  **\*bu**.  
  
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
  
##  <a name="basic_ostream_operator_lt_lt"></a>basic_ostream::operator&lt;&lt;  
 Akışa yazar.  
  
```  
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
 `Pfn`  
 Bir işlev işaretçisi.  
  
 `strbuf`  
 Bir işaretçi bir **stream_buf** nesnesi.  
  
 `val`  
 Akışa yazmak için bir öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Basic_ostream nesneye başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 `<ostream>` Üstbilgisi ayrıca çeşitli genel ekleme işleçlerini tanımlar. Daha fazla bilgi için bkz: [işleci <<](../standard-library/ostream-operators.md#op_lt_lt).  
  
 İlk üye işlevi biçiminde bir ifade sağlar **ostr << endl** çağrıları [endl](../standard-library/ostream-functions.md#endl)**(ostr)**ve ardından döndürür  **\*bu** . İkinci ve üçüncü işlevleri gibi diğer manipülatörleri olun [onaltılık](../standard-library/ios-functions.md#hex), benzer şekilde davranır. Kalan tüm biçimlendirilmiş çıkış işlevleri işlevlerdir.  
  
 İşlevi  
  
```  
basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
```  
  
 öğeleri ayıklar `strbuf`, `strbuf` null işaretçi değil ve bunları ekler. Ayıklama durdurur dosya sonu üzerinde veya bir ayıklama (hangi işlenemezse) bir özel durum oluşturur. Bu ayrıca, bir ekleme başarısız olursa, söz konusu öğeyi ayıklanıyor olmadan durdurur. İşlev öğe ekler veya bir ayıklama bir özel durum oluşturursa, işlev çağrıları [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). Her iki durumda da işlevi döndürür  **\*bu**.  
  
 İşlevi  
  
```  
basic_ostream<Elem, Tr>& operator<<(bool val);
```  
  
 dönüştürür `_Val` bir Boole değeri alanı ve çağırarak ekler [use_facet](../standard-library/basic-filebuf-class.md#open)**< num_put\<Elem, OutIt >**`(`[getloc](../standard-library/ios-base-class.md#getloc)). [PUT](#put)(**OutIt**([rdbuf](../standard-library/basic-ios-class.md#rdbuf)),  **\*bu**, `getloc`, **val**). Burada, **OutIt** olarak tanımlanan [ostreambuf_iterator](../standard-library/ostreambuf-iterator-class.md)**\<Elem, Tr >**. İşlevi döndürür  **\*bu**.  
  
 İşlevler  
  
```  
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
  
 Her dönüştürme `val` bir sayısal alan ve çağırarak Ekle **use_facet < num_put\<Elem, OutIt >**(`getloc`). **PUT**(**OutIt**(`rdbuf`),  **\*bu**, `getloc`, **val**). Burada, **OutIt** olarak tanımlanan **ostreambuf_iterator\<Elem, Tr >**. İşlevi döndürür  **\*bu**.  
  
 İşlevler  
  
```  
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
```  
  
 Her dönüştürme `val` bir sayısal alan ve çağırarak Ekle **use_facet < num_put\<Elem, OutIt >**(`getloc`)**. put**(**OutIt**(`rdbuf`),  **\*bu**, `getloc`, **val**). Burada, **OutIt** olarak tanımlanan **ostreambuf_iterator\<Elem, Tr >**. İşlevi döndürür  **\*bu**.  
  
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
  
##  <a name="op_eq"></a>basic_ostream::operator =  
 Sağlanan için değerler atayan `basic_ostream` parametresi bu nesneye nesne.  
  
```  
basic_ostream& operator=(basic_ostream&& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Bir `rvalue` başvuru bir `basic_ostream` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işleci çağırır takas `(right)`.  
  
##  <a name="put"></a>basic_ostream::Put  
 Bir karakterin bir akışa koyar.  
  
```  
basic_ostream<Elem, Tr>& put(char_type _Ch);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Ch`  
 Karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Basic_ostream nesneye başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Biçimlendirilmemiş çıkış işlevi öğesi ekler `_Ch`. Döndürdüğü  **\*bu**.  
  
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
  
##  <a name="seekp"></a>basic_ostream::seekp  
 Çıkış akışı konumda sıfırlayın.  
  
```  
basic_ostream<Elem, Tr>& seekp(pos_type _Pos);

basic_ostream<Elem, Tr>& seekp(off_type _Off, ios_base::seekdir _Way);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Pos`  
 Akış konumu.  
  
 `_Off`  
 Göreli uzaklık `_Way`.  
  
 `_Way`  
 Aşağıdakilerden birini [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir) numaralandırmalar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Basic_ostream nesneye başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa [başarısız](../standard-library/basic-ios-class.md#fail) olan **false**, ilk üye işlev çağrılarını **newpos =** [rdbuf](../standard-library/basic-ios-class.md#rdbuf)  **->**  [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)(*_Pos*), bazı `pos_type` geçici nesne **newpos**. Varsa **başarısız** false, ikinci işlev çağrılarını **newpos = rdbuf - >** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(*_Off, _Way*). Her iki durumda da, (`off_type`)**newpos ==** (`off_type`)(-1) (yerleştirme işlemi başarısız oldu), ardından işlevi çağırır **istr.** [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). Her iki işlevi dönüş  **\*bu**.  
  
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
  
##  <a name="sentry"></a>basic_ostream::sentry  
 İç içe geçmiş sınıf bir nesne, bildirim biçimlendirilmiş çıkış işlevleri ve biçimlendirilmemiş çıkış işlevleri yapıları açıklar.  
  
sınıf sentry {  
   Ortak:  
   Açık sentry (basic_ostream\<Elem, Tr > & _Ostr); işleci bool() const; ~ sentry();};  
  
### <a name="remarks"></a>Açıklamalar  
 İç içe geçmiş sınıf bir nesne, bildirim biçimlendirilmiş çıkış işlevleri ve biçimlendirilmemiş çıkış işlevleri yapıları açıklar. Varsa **ostr.** [iyi](../standard-library/basic-ios-class.md#good) olan **true** ve **ostr.** [tie](../standard-library/basic-ios-class.md#tie) Oluşturucu çağrıları null işaretçi değil **ostr.tie ->**[flush](#flush). Oluşturucu tarafından döndürülen değeri, ardından depolayan **ostr.good** içinde **durum**. Sonraki çağrı **işleç bool değeri** Bu saklı değer sunar.  
  
 Varsa `uncaught_exception` döndürür **false** ve [bayrakları](../standard-library/ios-base-class.md#flags)  **&**  [unitbuf](../standard-library/ios-functions.md#unitbuf) sıfır olmayan, olan yıkıcı çağrıları [Temizleme](#flush).  
  
##  <a name="swap"></a>basic_ostream::Swap  
 Bu değerleri alış verişleri `basic_ostream` sağlanan değerler için nesne `basic_ostream`.  
  
```  
void swap(basic_ostream& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Bir başvuru bir `basic_ostream` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlev çağrılarını [basic_ios::swap](../standard-library/basic-ios-class.md#swap) `(right)` bu nesne için içeriğini içeriğini Exchange `right`.  
  
##  <a name="tellp"></a>basic_ostream::tellp  
 Çıkış akışı rapor konumu.  
  
```  
pos_type tellp();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çıkış akışı konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa [başarısız](../standard-library/basic-ios-class.md#fail) olan **false**, üye işlevinin döndürdüğü [rdbuf](../standard-library/basic-ios-class.md#rdbuf)  **->**  [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) (0, `cur`, **içinde**). Aksi takdirde, döndürür `pos_type`(-1).  
  
### <a name="example"></a>Örnek  
  Bkz: [seekp](#seekp) kullanarak bir örnek için `tellp`.  
  
##  <a name="write"></a>basic_ostream::Write  
 Bir akış PUT karakter.  
  
```  
basic_ostream<Elem, Tr>& write(const char_type* str, streamsize count);
```  
  
### <a name="parameters"></a>Parametreler  
 `count`  
 Akışa yerleştirilecek karakter sayısı.  
  
 `str`  
 Akışa yerleştirilecek karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Basic_ostream nesneye başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 [Biçimlendirilmemiş çıkış işlevi](../standard-library/basic-ostream-class.md) dizisini ekler `count` Başlangıç öğeleri `str`.  
  
### <a name="example"></a>Örnek  
  Bkz: [streamsize](../standard-library/ios-typedefs.md#streamsize) kullanarak bir örnek için `write`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream programlama](../standard-library/iostream-programming.md)   
 [iostreams kuralları](../standard-library/iostreams-conventions.md)

