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
ms.openlocfilehash: 28399a1cd55407aadbc5d59e1e835892218ad0c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376604"
---
# <a name="strstreambuf-class"></a>strstreambuf Sınıfı

**Char** dizisi nesnesinde depolanan öğeler dizisine ve bu öğelerden öğelerin iletimini kontrol eden bir akış arabelleği açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class strstreambuf : public streambuf
```

## <a name="remarks"></a>Açıklamalar

Nesnenin nasıl oluşturulduruna bağlı olarak, dizideki değişiklikleri karşılamak için gerektiğinde ayrılabilir, genişletilebilir ve serbest bırakılabilir.

Sınıfın `strstreambuf` bir `strstreambuf` nesnesi, mod olarak birkaç mod bilgisi biti depolar. Bu bitler, denetlenen dizinin:

- Tahsis edildi ve eninde sonunda serbest bırakılmaları gerekiyor.

- Değiştirilebilir.

- Depolama yeniden tahsis edilerek genişletilebilir.

- Dondurulmuş ve bu nedenle nesne yok edilmeden önce çözülmüş olması gerekir veya nesne dışında bir ajans tarafından serbest (tahsis) .

Bu ayrı mod bitlerinin durumuna bakılmaksızın, dondurulan denetlenen bir dizi değiştirilemez veya genişletilemez.

Nesne ayrıca ayırmayı denetleyen `strstreambuf` iki işlev için işaretçiler depolar. Bunlar null işaretçileriyse, nesne denetitilen sıra için depolamayı ayırma ve serbest etme yöntemini tasarlar.

> [!NOTE]
> Bu sınıf amortismana uğradı. Bunun yerine [stringbuf](../standard-library/sstream-typedefs.md#stringbuf) veya [wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf) kullanmayı düşünün.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Strstreambuf](#strstreambuf)|Türünde `strstreambuf`bir nesne oluşturuyor.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Dondurmak](#freeze)|Akış arabelleği akışı arabellek işlemleri nde kullanılamamasına neden olur.|
|[Taşma](#overflow)|Tam bir arabelleğe yeni bir karakter eklendiğinde çağrılabilen korumalı sanal işlev.|
|[pbackfail](#pbackfail)|Giriş akışına bir öğeyi geri koymaya çalışan ve sonra onu geçerli öğe (bir sonraki işaretçitarafından işaret edilen) yapmaya çalışan korumalı bir sanal üye işlev.|
|[pcount](#pcount)|Denetlenmeye nisken diziye yazılan öğe sayısının sayısını döndürür.|
|[seekoff](#seekoff)|Denetitilen akışlar için geçerli konumları değiştirmeye çalışan korumalı sanal üye işlevi.|
|[seekpos](#seekpos)|Denetitilen akışlar için geçerli konumları değiştirmeye çalışan korumalı sanal üye işlevi.|
|[Str](#str)|Çağrılar [donuyor](#freeze)ve ardından bir işaretçiyi denetitilen dizinin başına döndürür.|
|[akış altı](#underflow)|Giriş akışından geçerli öğeyi ayıklamak için korunan bir sanal işlev.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<strstream>

**Ad alanı:** std

## <a name="strstreambuffreeze"></a><a name="freeze"></a>strstreambuf::dondurma

Akış arabelleği akışı arabellek işlemleri nde kullanılamamasına neden olur.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Parametreler

*_Freezeit*\
Derenin dondurulmasını isteyip istemediğini gösteren **bir bool.**

### <a name="remarks"></a>Açıklamalar

*_Freezeit* doğruysa, işlev depolanan `strstreambuf` modu değiştirerek denetlenir diziyi dondurabilir. Aksi takdirde, kontrollü dizi dondurulmuş değil yapar.

[str](#str) `freeze`anlamına gelir .

> [!NOTE]
> Dondurulmuş bir arabellek imha `strstreambuf` sırasında serbest bırakılmaz. Bellek sızıntısını önlemek için boşverilmeden önce arabelleği çözmeniz gerekir.

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

## <a name="strstreambufoverflow"></a><a name="overflow"></a>strstreambuf::taşma

Tam bir arabelleğe yeni bir karakter eklendiğinde çağrılabilen korumalı sanal işlev.

```cpp
virtual int overflow(int _Meta = EOF);
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `EOF`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olamazsa, döndürür. `EOF` Aksi takdirde, * \_Meta* == `EOF`ise, başka `EOF`bir değer döndürür . Aksi takdirde, * \_Meta*döndürür.

### <a name="remarks"></a>Açıklamalar

* \_Meta* != `EOF`, korunan sanal üye işlev çıktı `(char)_Meta` arabelleği içine öğe eklemeye çalışır. Bunu çeşitli şekillerde yapabilirsiniz:

- Bir yazma konumu varsa, öğeyi yazma konumuna depolayabilir ve çıktı arabelleği için bir sonraki işaretçiyi artım.

- Depolanan strstreambuf modu, denetlenmiş sıranın değiştirilebilir, genişletilebilir ve dondurulmadığını söylüyorsa, işlev çıktı arabelleği için yeni bir ayırma yaparak bir yazma konumu sağlayabilir. Çıktı arabelleği bu şekilde genişletilmesi de ilişkili giriş arabellek genişletir.

## <a name="strstreambufpbackfail"></a><a name="pbackfail"></a>strstreambuf::pbackfail

Giriş akışına bir öğeyi geri koymaya çalışan ve sonra onu geçerli öğe (bir sonraki işaretçitarafından işaret edilen) yapan korumalı sanal üye işlev.

```cpp
virtual int pbackfail(int _Meta = EOF);
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `EOF`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olamazsa, döndürür. `EOF` Aksi takdirde, * \_Meta* == `EOF`ise, başka `EOF`bir değer döndürür . Aksi takdirde, * \_Meta*döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlev, bir öğeyi giriş arabellesine geri koymaya ve sonra onu geçerli öğe (bir sonraki işaretçiye işaret eden) yapmaya çalışır.

* \_Meta* == ise, geri itmek için öğe etkili bir geçerli öğeönce akışı zaten biridir.`EOF` Aksi takdirde, bu öğe `ch = (char)_Meta`nin yerine . İşlev çeşitli şekillerde bir öğegeri koyabilirsiniz:

- Bir geri alma konumu varsa ve orada depolanan öğe `ch`ile karşılaştırıldığında, giriş arabelleği için bir sonraki işaretçiyi atabilir.

- Bir geri alma konumu varsa ve strstreambuf modu denetitilen sıranın değiştirilebilir `ch` olduğunu söylüyorsa, işlev putback konumuna depolayabilir ve giriş arabelleği için bir sonraki işaretçiyi atayabilir.

## <a name="strstreambufpcount"></a><a name="pcount"></a>strstreambuf::p sayısı

Denetlenmeye nisken diziye yazılan öğe sayısının sayısını döndürür.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenmeyen sıraya yazılan öğe sayısının sayısı.

### <a name="remarks"></a>Açıklamalar

Özellikle, [pptr](../standard-library/basic-streambuf-class.md#pptr) null işaretçiise, işlev sıfır döndürür. Aksi takdirde, `pptr`  -  [pbase](../standard-library/basic-streambuf-class.md#pbase)döndürür.

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

## <a name="strstreambufseekoff"></a><a name="seekoff"></a>strstreambuf::seekoff

Denetitilen akışlar için geçerli konumları değiştirmeye çalışan korumalı sanal üye işlevi.

```cpp
virtual streampos seekoff(streamoff _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_off*\
*_Way*göreli aramak için pozisyon .

*_way*\
Ofset işlemleri için başlangıç noktası. Bkz. olası değerler için [seekdir.](../standard-library/ios-base-class.md#seekdir)

*_Which*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

İşlev ya da her iki akış konumunu değiştirmeyi başarırsa, ortaya çıkan akış konumunu döndürür. Aksi takdirde, başarısız olur ve geçersiz bir akış konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Korunan sanal üye işlevi, denetitilen akışlar için geçerli konumları değiştirmeye çalışır. Sınıf strstreambuf bir nesne için, bir akış konumu tamamen bir akış ofset oluşur. Ofset sıfır, denetlenir dizinin ilk öğesini belirtir.

Yeni pozisyon aşağıdaki gibi belirlenir:

- Eğer `_Way == ios_base::beg`, yeni pozisyon akışı artı *_Off*başlangıcıdır.

- Eğer `_Way == ios_base::cur`, yeni konum geçerli akış konumu artı *_Off.*

- Eğer `_Way == ios_base::end`, yeni pozisyon akışı artı *_Off*sonudur.

`_Which & ios_base::in` Sıfır değilse ve giriş arabelleği varsa, işlev giriş arabelleği okumak için bir sonraki konumu değiştirir. Ayrıca `_Which & ios_base::out` sıfır `_Way != ios_base::cur`değilse ve çıktı arabelleği varsa, işlev de okumak için bir sonraki konumu eşleşecek şekilde yazmak için bir sonraki konumu ayarlar.

Aksi takdirde, sıfır olmayan `_Which & ios_base::out` ve çıktı arabellek varsa, işlev çıktı arabelleği yazmak için bir sonraki konumu değiştirir. Aksi takdirde, konumlandırma işlemi başarısız olur. Bir konumlandırma işleminin başarılı olabilmesi için, elde edilen akış konumunun denetlenme sırası içinde olması gerekir.

## <a name="strstreambufseekpos"></a><a name="seekpos"></a>strstreambuf::seekpos

Denetitilen akışlar için geçerli konumları değiştirmeye çalışan korumalı sanal üye işlevi.

```cpp
virtual streampos seekpos(streampos _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*\
Aranacak pozisyon.

*_Which*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

İşlev ya da her iki akış konumunu değiştirmeyi başarırsa, ortaya çıkan akış konumunu döndürür. Aksi takdirde, başarısız olur ve geçersiz bir akış konumunu döndürür. Akış konumunun geçersiz olup olmadığını belirlemek için, `pos_type(off_type(-1))`iade değerini .

### <a name="remarks"></a>Açıklamalar

Korunan sanal üye işlevi, denetitilen akışlar için geçerli konumları değiştirmeye çalışır. Sınıf strstreambuf bir nesne için, bir akış konumu tamamen bir akış ofset oluşur. Ofset sıfır, denetlenir dizinin ilk öğesini belirtir. Yeni pozisyon *_Sp*tarafından belirlenir.

ios_base::in sıfır değilse ve giriş arabelleği varsa, işlev giriş arabelleği okumak için bir sonraki konumu değiştirir. **ios_base::in** `_Which`  &  `_Which` değilse ve çıktı arabelleği varsa, işlev de okumak için bir sonraki konumu eşleşecek şekilde yazmak için bir sonraki konumu  &  `ios_base::out` ayarlar. Aksi takdirde, `_Which`  &  `ios_base::out` sıfır olmayan ve çıktı arabellek varsa, işlev çıktı arabelleği yazmak için bir sonraki konumu değiştirir. Aksi takdirde, konumlandırma işlemi başarısız olur. Bir konumlandırma işleminin başarılı olabilmesi için, elde edilen akış konumunun denetlenme sırası içinde olması gerekir.

## <a name="strstreambufstr"></a><a name="str"></a>strstreambuf::str

Çağrılar [donuyor](#freeze)ve ardından bir işaretçiyi denetitilen dizinin başına döndürür.

```cpp
char *str();
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen dizinin başına bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Açıkça eklemediğiniz sürece sonlandırıcı null öğesi yoktur.

### <a name="example"></a>Örnek

Bkz. [strstreambuf::str](#freeze) kullanan **str**bir örnek için dondurma .

## <a name="strstreambufstrstreambuf"></a><a name="strstreambuf"></a>strstreambuf::strstreambuf

Türünde `strstreambuf`bir nesne oluşturuyor.

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

*Sayısı*\
*_Getptr*işaret eden arabelleğe işaret edilen uzunluğunu belirler. *_Getptr* bir bağımsız değişken (ilk oluşturucu formu) değilse, arabellekler için önerilen bir ayırma boyutu.

*_Freefunc*\
Arabellek belleği serbest için kullanılan işlev.

*_Getptr*\
Giriş için kullanılan bir arabellek.

*_Putptr*\
Çıktı için kullanılan bir arabellek.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, giriş arabelleği, çıktı arabelleği ve strstreambuf ayırmasını denetleyen tüm işaretçilerde bir null işaretçisi depolar. Bu, denetlenmiş sırayı değiştirilebilir ve genişletilebilir hale getirmek için depolanan strstreambuf modunu ayarlar. Ayrıca, önerilen ilk ayırma boyutu olarak *saymayı* kabul eder.

İkinci oluşturucu ilk gibi çalışır, ancak bu depolama ve * \_Freefunc* işlevi için işaretçi olarak depolama ayırmak için aramak için işlev için işaretçi olarak * \_Allocfunc* depolar bu depolama serbest aramak için çağrı.

Üç yapıcı:

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

ayrıca, denetlenebilen sırayı tutmak için kullanılan dizi nesnesini `_Getptr` belirleyen dışında, ilk gibi de görünür. (Bu nedenle, bir null işaretçi olmamalıdır.) Dizideki *N* öğesi sayısı aşağıdaki gibi belirlenir:

- (> 0), sonra *N* . `count``count`

- Eğer`count` ( == 0), `strlen`sonra *N* ( `_Getptr` ( **const** `char` *) ise.

- `count` (< 0), sonra *N* **INT_MAX.**

Null `_Putptr` işaretçiise, işlev yürütülerek sadece bir giriş arabelleği kurar:

```cpp
setg(_Getptr,
    _Getptr,
    _Getptr + N);
```

Aksi takdirde, yürüterek hem giriş hem de çıktı arabellekleri kurar:

```cpp
setg(_Getptr,
    _Getptr,
    _Putptr);

setp(_Putptr,
    _Getptr + N);
```

Bu durumda, `_Putptr` [ `_Getptr`, `_Getptr`  +  *N*] aralığında olmalıdır.

Son olarak, üç yapıcılar:

```cpp
strstreambuf(const char *_Getptr,
    streamsize count);

strstreambuf(const signed char *_Getptr,
    streamsize count);

strstreambuf(const unsigned char *_Getptr,
    streamsize count);
```

tüm aynı şekilde:

```cpp
streambuf((char *)_Getptr, count);
```

depolanan mod, denetlenmiş sırayı ne değiştirilebilir ne de genişletilebilir hale getirir.

## <a name="strstreambufunderflow"></a><a name="underflow"></a>strstreambuf::underflow

Giriş akışından geçerli öğeyi ayıklamak için korunan bir sanal işlev.

```cpp
virtual int underflow();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olamazsa, döndürür. `EOF` Aksi takdirde, yukarıda açıklandığı gibi dönüştürülen giriş akışındaki geçerli öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Korunan sanal üye işlevi, giriş `ch` arabelleğinden geçerli öğeyi ayıklamak, sonra geçerli akış konumunu`int`ilerletmek`unsigned char`ve öğeyi ( )( ) **ch**olarak döndürmek için çaba göstermektedir. Bunu yalnızca tek bir şekilde yapabilir: okuma konumu varsa, okuma konumunda depolanan öğe olarak alır `ch` ve giriş arabelleği için bir sonraki işaretçiyi ilerler.

## <a name="see-also"></a>Ayrıca bkz.

[streambuf](../standard-library/streambuf-typedefs.md#streambuf)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
