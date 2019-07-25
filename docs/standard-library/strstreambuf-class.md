---
title: strstreambuf Sınıfı
ms.date: 11/04/2016
f1_keywords:
- strstream/std::strstreambuf::freeze
- strstream/std::strstreambuf::overflow
- strstream/std::strstreambuf::pbackfail
- strstream/std::strstreambuf::pcount
- strstream/std::strstreambuf::seekoff
- strstream/std::strstreambuf::seekpos
- strstream/std::strstreambuf::str
- strstream/std::strstreambuf::underflow
helpviewer_keywords:
- std::strstreambuf [C++], freeze
- std::strstreambuf [C++], overflow
- std::strstreambuf [C++], pbackfail
- std::strstreambuf [C++], pcount
- std::strstreambuf [C++], seekoff
- std::strstreambuf [C++], seekpos
- std::strstreambuf [C++], str
- std::strstreambuf [C++], underflow
ms.assetid: b040b8ea-0669-4eba-8908-6a9cc159c54b
ms.openlocfilehash: f24d8fe99bc211e026172e42669cf5e430ad31e8
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459070"
---
# <a name="strstreambuf-class"></a>strstreambuf Sınıfı

Bir **char** dizi nesnesinde depolanan bir öğe dizisine ve öğesinden öğelerin aktarılmasını denetleyen bir akış arabelleği tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class strstreambuf : public streambuf
```

## <a name="remarks"></a>Açıklamalar

Nesnenin nasıl oluşturulduğuna bağlı olarak, dizideki değişikliklere uyum sağlamak için gerektiğinde ayrılabilir, genişletilebilir ve serbest bırakılmış olabilir.

Sınıfının `strstreambuf` bir nesnesi, `strstreambuf` modu gibi birkaç bit mod bilgisini depolar. Bu bitler denetimli sıranın olup olmadığını gösterir:

- Ayrıldı ve sonunda serbest bırakılmalıdır.

- Değiştirilebilir.

- , Depolama alanı realolarak eklenerek genişletilebilir.

- Dondurulmuş ve bu nedenle nesne yok edilirken veya (ayrılmışsa) nesne dışında bir acenteden önce dondurulmamış olması gerekir.

Dondurulmuş olan denetimli bir sıra, bu ayrı mod bitlerinin durumundan bağımsız olarak değiştirilemez veya genişletilemez.

Nesne Ayrıca, ayırmayı denetleyen `strstreambuf` iki işleve işaretçiler depolar. Bunlar null işaretçilerse, nesne, denetimli sıra için depolamayı ayırmak ve serbest bırakma yöntemine sahiptir.

> [!NOTE]
> Bu sınıf kullanım dışıdır. Bunun yerine [stringarabelleğe](../standard-library/sstream-typedefs.md#stringbuf) veya [wstringarabelleğe](../standard-library/sstream-typedefs.md#wstringbuf) kullanmayı düşünün.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[strstreambuf](#strstreambuf)|Türünde `strstreambuf`bir nesne oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[amazsınız](#freeze)|Akış arabelleği işlemleri aracılığıyla akış arabelleğinin kullanılamamasına neden olur.|
|[taşma](#overflow)|Tam arabelleğe yeni bir karakter eklendiğinde çağrılabilen, korunan bir sanal işlev.|
|[pbackfail](#pbackfail)|Giriş akışına bir öğe geri döndürmeye çalışan korumalı bir sanal üye işlevi ve ardından bunu geçerli öğe (sonraki işaretçinin gösterdiği) yapın.|
|[pcount](#pcount)|Denetlenen diziye yazılan öğe sayısının sayısını döndürür.|
|[seekoff](#seekoff)|Denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışan korumalı bir sanal üye işlevi.|
|[seekpos](#seekpos)|Denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışan korumalı bir sanal üye işlevi.|
|[üstbilgisine](#str)|Çağırır [ve](#freeze)sonra denetlenen sıranın başlangıcına bir işaretçi döndürür.|
|[öğe](#underflow)|Giriş akışından geçerli öğeyi ayıklamak için korunan bir sanal işlev.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<strstream >

**Ad alanı:** std

## <a name="freeze"></a>strstreamarabelleğe:: Freeze

Akış arabelleği işlemleri aracılığıyla akış arabelleğinin kullanılamamasına neden olur.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Parametreler

*_Freezeit*\
Akışın dondurulmuş olmasını isteyip istemediğinizi belirten bir **bool** .

### <a name="remarks"></a>Açıklamalar

*_Freezeit* true ise, işlev, denetlenen diziyi dondurulmuş hale `strstreambuf` getirmek için saklı modu değiştirir. Aksi takdirde, denetlenen sıranın dondurulmuş olmasını sağlar.

[Str](#str) şunları `freeze`belirtir.

> [!NOTE]
> Dondurulmuş bir arabellek, yok etme sırasında `strstreambuf` serbest bırakılmaz. Bellek sızıntısını önlemek için, serbest bırakmadan önce arabelleği ortadan kaldırmalısınız.

### <a name="example"></a>Örnek

```cpp
// strstreambuf_freeze.cpp
// compile with: /EHsc

#include <iostream>
#include <strstream>

using namespace std;

void report(strstream &x)
{
    if (!x.good())
        cout << "stream bad" << endl;
    else
        cout << "stream good" << endl;
}

int main()
{
    strstream x;

    x << "test1";
    cout << "before freeze: ";
    report(x);

    // Calling str freezes stream.
    cout.write(x.rdbuf()->str(), 5) << endl;
    cout << "after freeze: ";
    report(x);

    // Stream is bad now, wrote on frozen stream
    x << "test1.5";
    cout << "after write to frozen stream: ";
    report(x);

    // Unfreeze stream, but it is still bad
    x.rdbuf()->freeze(false);
    cout << "after unfreezing stream: ";
    report(x);

    // Clear stream
    x.clear();
    cout << "after clearing stream: ";
    report(x);

    x << "test3";
    cout.write(x.rdbuf()->str(), 10) << endl;

    // Clean up.  Failure to unfreeze stream will cause a
    // memory leak.
    x.rdbuf()->freeze(false);
}
```

```Output
before freeze: stream good
test1
after freeze: stream good
after write to frozen stream: stream bad
after unfreezing stream: stream bad
after clearing stream: stream good
test1test3
```

## <a name="overflow"></a>strstreamarabelleğe:: overflow

Tam arabelleğe yeni bir karakter eklendiğinde çağrılabilen, korunan bir sanal işlev.

```cpp
virtual int overflow(int _Meta = EOF);
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `EOF`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olmazsa, döndürür `EOF`. Aksi takdirde,  *\_meta* ==  `EOF`ise dışında bir değer döndürür.`EOF` Aksi takdirde,  *\_meta*döndürür.

### <a name="remarks"></a>Açıklamalar

Eğer  *\_meta* ! = `EOF`ise, korumalı sanal üye işlevi öğeyi `(char)_Meta` çıkış arabelleğine eklemeye çalışır. Bunu çeşitli yollarla yapabilirsiniz:

- Bir yazma konumu varsa, öğeyi yazma konumuna kaydedebilir ve çıkış arabelleği için sonraki işaretçiyi artırabilirsiniz.

- Saklı strstreammode, denetlenen sıranın değiştirilebilir, genişletilebilir ve dondurulmuş olduğunu söyyorsa, bu işlev çıktı arabelleği için yeni ayırarak bir yazma konumu kullanılabilir hale getirir. Çıkış arabelleğini bu şekilde genişletmek, ilişkili giriş arabelleğini de genişletir.

## <a name="pbackfail"></a>strstreamarabelleğe::p backfail

Giriş akışına bir öğe geri döndürmeye çalışan korumalı bir sanal üye işlevi ve ardından bunu geçerli öğe yapar (sonraki işaretçinin gösterdiği).

```cpp
virtual int pbackfail(int _Meta = EOF);
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `EOF`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olmazsa, döndürür `EOF`. Aksi takdirde,  *\_meta* ==  `EOF`ise dışında bir değer döndürür.`EOF` Aksi takdirde,  *\_meta*döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, giriş arabelleğine bir öğe geri döndürmeye çalışır ve sonra geçerli öğe (sonraki işaretçinin gösterdiği) yapar.

Eğer  *\_meta*ise,geri`EOF`gönderme öğesi geçerli öğeden önceki bir akışta etkin bir şekilde zaten var. ==  Aksi takdirde, bu öğe ile `ch = (char)_Meta`değiştirilmiştir. İşlevi bir öğeyi çeşitli yollarla geri alabilir:

- Bir Putback konumu varsa ve şuna eşit olarak `ch`karşılaştırıldığı öğe, giriş arabelleği için bir sonraki işaretçiyi azaledebilir.

- Bir Putback konumu varsa ve strstreambuffer modu denetlenen diziyi değiştirilebilir ise, işlev putback konumunu saklayabilir `ch` ve giriş arabelleği için bir sonraki işaretçiyi azaltır.

## <a name="pcount"></a>strstreamarabelleğe::p sayısı

Denetlenen diziye yazılan öğe sayısının sayısını döndürür.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen diziye yazılan öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Özellikle, [pptr](../standard-library/basic-streambuf-class.md#pptr) null işaretçisiyse, işlev sıfır döndürür. Aksi takdirde, `pptr` [pbase](../standard-library/basic-streambuf-class.md#pbase)döndürür.  - 

### <a name="example"></a>Örnek

```cpp
// strstreambuf_pcount.cpp
// compile with: /EHsc
#include <iostream>
#include <strstream>
using namespace std;

int main( )
{
   strstream x;
   x << "test1";
   cout << x.rdbuf( )->pcount( ) << endl;
   x << "test2";
   cout << x.rdbuf( )->pcount( ) << endl;
}
```

## <a name="seekoff"></a>strstreamarabelleğe:: seekoff

Denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışan korumalı bir sanal üye işlevi.

```cpp
virtual streampos seekoff(streamoff _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Kapatma*\
*_Yönteme*göre arama yapılacak konum.

*_Yol*\
Dengeleme işlemleri için başlangıç noktası. Olası değerler için bkz. [seekdir](../standard-library/ios-base-class.md#seekdir) .

*_Hangisi*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin verir.

### <a name="return-value"></a>Dönüş Değeri

İşlev ya da her iki akış konumunu değiştirme içinde başarılı olursa, sonuç akış konumunu döndürür. Aksi takdirde, başarısız olur ve geçersiz bir akış konumu döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları endeavors. Strstreamarabelleğe sınıfının bir nesnesi için bir akış konumu yalnızca bir akış sapmasını içerir. Sıfır değeri, denetlenen dizinin ilk öğesini belirler.

Yeni konum aşağıdaki gibi belirlenir:

- İse `_Way == ios_base::beg`, yeni konum akışın başıdır ve *_kapalıdır*.

- İse `_Way == ios_base::cur`, yeni konum geçerli akış konumudur ve *_Off*olur.

- İse `_Way == ios_base::end`, yeni konum akışın sonu ve *_Off*olur.

Sıfır `_Which & ios_base::in` değilse ve giriş arabelleği varsa, işlev giriş arabelleğinde okunacak bir sonraki konumu değiştirir. `_Which & ios_base::out` Ayrıca`_Way != ios_base::cur`sıfır dışında bir değer varsa ve çıkış arabelleği varsa, işlev, sonraki konumu okumak için de bir sonraki konumdan eşleşecek şekilde ayarlar.

Aksi halde, sıfır değilseveçıkışarabelleğivarsa,işlevsonrakikonumuçıkışarabelleğineyazmakiçindeğiştirir.`_Which & ios_base::out` Aksi takdirde, konumlandırma işlemi başarısız olur. Konumlandırma işleminin başarılı olması için, elde edilen akış konumu denetimli sıra içinde olmalıdır.

## <a name="seekpos"></a>strstreamarabelleğe:: seekpos

Denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışan korumalı bir sanal üye işlevi.

```cpp
virtual streampos seekpos(streampos _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*\
Arama yapılacak konum.

*_Hangisi*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin verir.

### <a name="return-value"></a>Dönüş Değeri

İşlev ya da her iki akış konumunu değiştirme içinde başarılı olursa, sonuç akış konumunu döndürür. Aksi takdirde, başarısız olur ve geçersiz bir akış konumu döndürür. Akış konumunun geçersiz olup olmadığını anlamak için dönüş değerini ile `pos_type(off_type(-1))`karşılaştırın.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları endeavors. Strstreamarabelleğe sınıfının bir nesnesi için bir akış konumu yalnızca bir akış sapmasını içerir. Sıfır değeri, denetlenen dizinin ilk öğesini belirler. Yeni konum *_Sp*tarafından belirlenir.

İos_base:: ın sıfır değilse ve giriş arabelleği varsa, işlev giriş arabelleğinde okunacak bir sonraki konumu değiştirir.  `_Which`  &  Sıfır dışında ise ve çıkış arabelleği varsa, bu işlev bir sonraki konumu okumak üzere bir sonraki konumdan eşleşecek şekilde de ayarlar. `_Which`  &  `ios_base::out` Aksihalde,sıfırdeğilseveçıkışarabelleğivarsa,işlevsonrakikonumuçıkışarabelleğineyazmakiçindeğiştirir.`_Which`  &  `ios_base::out` Aksi takdirde, konumlandırma işlemi başarısız olur. Konumlandırma işleminin başarılı olması için, elde edilen akış konumu denetimli sıra içinde olmalıdır.

## <a name="str"></a>strstreamarabelleğe:: Str

Çağırır [ve](#freeze)sonra denetlenen sıranın başlangıcına bir işaretçi döndürür.

```cpp
char *str();
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen dizinin başlangıcına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Açıkça bir tane eklemediğiniz takdirde Sonlandırıcı null öğe yok.

### <a name="example"></a>Örnek

**Str**kullanan bir örnek için bkz. [strstreamarabelleğe:: Freeze](#freeze) .

## <a name="strstreambuf"></a>strstreamarabelleğe:: strstreamarabelleğe

Türünde `strstreambuf`bir nesne oluşturur.

```cpp
explicit strstreambuf(streamsize count = 0);

strstreambuf(void (* _Allocfunc)(size_t),
    void (* _Freefunc)(void*));

strstreambuf(char* _Getptr,
    streamsize count,
    char* _Putptr = 0);

strstreambuf(signed char* _Getptr,
    streamsize count,
    signed char* _Putptr = 0);

strstreambuf(unsigned char* _Getptr,
    streamsize count,
    unsigned char* _Putptr = 0);

strstreambuf(const char* _Getptr,
    streamsize count);

strstreambuf(const signed char* _Getptr,
    streamsize count);

strstreambuf(const unsigned char* _Getptr,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*_Allocfunc*\
Arabellek belleği ayırmak için kullanılan işlev.

*biriktirme*\
*_Getptr*tarafından işaret edilen arabelleğin uzunluğunu belirler. *_Getptr* bir bağımsız değişken (ilk Oluşturucu formu) değilse, arabellekler için önerilen bir ayırma boyutu.

*_Freefunc*\
Arabellek belleğini serbest bırakmak için kullanılan işlev.

*_Getptr*\
Giriş için kullanılan bir arabellek.

*_Putptr*\
Çıktı için kullanılan bir arabellek.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, giriş arabelleğini, çıkış arabelleğini ve strstreambuffer ayırmayı denetleyen tüm işaretçilerde boş bir işaretçi depolar. Denetlenen sırayı değiştirilebilir ve Genişletilebilir hale getirmek için depolanan strstreammode modunu ayarlar. Ayrıca, önerilen ilk ayırma boyutu olarak *Count* kabul eder.

İkinci Oluşturucu ilk gibi davranır, bu, depolamayı serbest bırakmak için çağırmak üzere işlevin işaretçisi olarak depolama ve  *\_freefunc* olarak ayırmak için çağırmak üzere bir işlevin işaretçisi olarak  *\_allocfunc* 'ı saklar.

Üç Oluşturucu:

```cpp
strstreambuf(char *_Getptr,
    streamsize count,
    char *putptr = 0);

strstreambuf(signed char *_Getptr,
    streamsize count,
    signed char *putptr = 0);

strstreambuf(unsigned char *_Getptr,
    streamsize count,
    unsigned char *putptr = 0);
```

aynı zamanda, denetlenen sırayı tutmak için kullanılan `_Getptr` dizi nesnesini atayan hariç, ilki gibi davranır. (Bu nedenle, null bir işaretçi olmaması gerekir.) Dizideki *öğelerin sayısı* şu şekilde belirlenir:

- (`count` > 0) ise, *N* olur `count`.

- `count` (= = 0) ise *N* ( `strlen`( **const** `char` *) `_Getptr` ) olur.

- (`count` < 0) ise, *N* ise **INT_MAX**.

`_Putptr` Null işaretçisiyse, işlev yalnızca şunu yürüterek bir giriş arabelleği oluşturur:

```cpp
setg(_Getptr,
    _Getptr,
    _Getptr + N);
```

Aksi takdirde, şunu yürüterek hem giriş hem de çıkış arabellekleri kurar:

```cpp
setg(_Getptr,
    _Getptr,
    _Putptr);

setp(_Putptr,
    _Getptr + N);
```

Bu durumda `_Putptr` , [ `_Getptr`, `_Getptr` N + ] aralığında olmalıdır.

Son olarak, üç Oluşturucu:

```cpp
strstreambuf(const char *_Getptr,
    streamsize count);

strstreambuf(const signed char *_Getptr,
    streamsize count);

strstreambuf(const unsigned char *_Getptr,
    streamsize count);
```

tümü aynı şekilde davranır:

```cpp
streambuf((char *)_Getptr, count);
```

saklı mod, denetimli sırayı değiştirilebilir veya Genişletilebilir olarak yapmaz.

## <a name="underflow"></a>strstreamarabelleğe:: yetersiz

Giriş akışından geçerli öğeyi ayıklamak için korunan bir sanal işlev.

```cpp
virtual int underflow();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olmazsa, döndürür `EOF`. Aksi halde, yukarıda açıklandığı gibi dönüştürülmüş olarak, giriş akışındaki geçerli öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi `ch` , geçerli öğeyi giriş arabelleğinden ayıklamak için endeavors, sonra geçerli akış konumunu ilerletin ve öğeyi (`int`) (`unsigned char`) **ch**olarak döndürür. Bunu yalnızca bir şekilde yapabilir: bir okuma konumu kullanılabiliyorsa, okuma konumunda depolanan öğe olarak alır `ch` ve giriş arabelleği için bir sonraki işaretçiyi ilerletir.

## <a name="see-also"></a>Ayrıca bkz.

[streambuf](../standard-library/streambuf-typedefs.md#streambuf)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
