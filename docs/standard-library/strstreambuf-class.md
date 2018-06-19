---
title: strstreambuf sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- strstream/std::strstreambuf::freeze
- strstream/std::strstreambuf::overflow
- strstream/std::strstreambuf::pbackfail
- strstream/std::strstreambuf::pcount
- strstream/std::strstreambuf::seekoff
- strstream/std::strstreambuf::seekpos
- strstream/std::strstreambuf::str
- strstream/std::strstreambuf::underflow
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0512e2794e5ac493a997b5d4d885931d9a9fc14
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33862344"
---
# <a name="strstreambuf-class"></a>strstreambuf Sınıfı

Öğeleri depolanan öğe dizisi gelen ve giden iletimini denetleyen bir Akış Arabellek açıklar bir `char` dizi nesnesi.

## <a name="syntax"></a>Sözdizimi

```cpp
class strstreambuf : public streambuf
```

## <a name="remarks"></a>Açıklamalar

Nesne nasıl oluşturulur bağlı olarak ayrılan, genişletilmiş ve olması dizisi değişiklikleri uyum için gereken serbest.

Sınıfın bir nesnesi `strstreambuf` birkaç BITS modu bilgileri depolar, `strstreambuf` modu. Bu BITS belirtmek olup olmadığını denetimli dizisi:

- Ayrıldı ve sonunda boşaltılması gerekiyor.

- Değiştirilebilir olur.

- Depolama tahsis tarafından Genişletilebilir olur.

- Dondurulmuş ve bu nedenle nesne dışında bir Teşkilatı tarafından nesne yok veya (ayrılan varsa) serbest önce çözülmüş gerekir.

Dondurulmuş denetimli bir sırası değiştirilemiyor veya bu ayrı mod BITS durumuna bakılmaksızın, genişletilmiş.

Nesne denetleyen iki işlev işaretçileri de depolar `strstreambuf` ayırma. Null işaretçiler bunlar, nesne ayırma ve denetlenen dizisi için depolama boşaltma kendi yöntemi devises.

> [!NOTE]
> Bu sınıf kullanım dışıdır. Kullanmayı [stringbuf](../standard-library/sstream-typedefs.md#stringbuf) veya [wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf) yerine.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[strstreambuf](#strstreambuf)|Türünde bir nesne oluşturur `strstreambuf`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Dondurma](#freeze)|Bir Akış Arabellek Akış Arabellek işlemleri kullanılamaz hale gelmesine neden olur.|
|[Taşma](#overflow)|Yeni bir karakter tam arabelleğine takıldığında çağrılabilir korumalı sanal işlev.|
|[pbackfail](#pbackfail)|Almaya çalıştığında bir korumalı sanal üye işlevi bir öğenin Giriş akışı yedekleyin ve (tarafından sonraki işaretçisi işaret) geçerli öğe olun.|
|[pcount](#pcount)|Denetimli sıraya yazılan öğeleri sayısını döndürür.|
|[seekoff](#seekoff)|Geçerli konumlar denetimli akışlar için alter dener korumalı sanal üye işlevi.|
|[seekpos](#seekpos)|Geçerli konumlar denetimli akışlar için alter dener korumalı sanal üye işlevi.|
|[str](#str)|Çağrıları [Dondur](#freeze)ve ardından bir işaretçi denetimli sıranın başına döndürür.|
|[underflow](#underflow)|Giriş akışından geçerli öğe ayıklamak için korumalı bir sanal işlev.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<strstream >

**Namespace:** std

## <a name="freeze"></a>  strstreambuf::Freeze

Bir Akış Arabellek Akış Arabellek işlemleri kullanılamaz hale gelmesine neden olur.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Parametreler

`_Freezeit` A `bool` donabilir akış isteyip istemediğinizi belirten.

### <a name="remarks"></a>Açıklamalar

Varsa `_Freezeit` işlevi olarak değiştiren saklı doğrudur `strstreambuf` dondurulmuş denetimli sıra yapmak için modu. Aksi takdirde değil dondurulmuş denetimli dizisi kolaylaştırır.

[str](#str) gelir `freeze`.

> [!NOTE]
> Dondurulmuş arabellek sırasında boşaltılması değil `strstreambuf` yok etme. Bellek sızıntısını önlemek için serbest önce arabellek Çöz gerekir.

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

## <a name="overflow"></a>  strstreambuf::Overflow

Yeni bir karakter tam arabelleğine takıldığında çağrılabilir korumalı sanal işlev.

```cpp
virtual int overflow(int _Meta = EOF);
```

### <a name="parameters"></a>Parametreler

`_Meta` Arabelleğe eklemek için karakter veya `EOF`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarısız olması durumunda, döndürür `EOF`. Aksi halde, eğer _ *Meta* == `EOF`, başka bir değer döndürür `EOF`. Aksi takdirde, döndürür \_ *Meta*.

### <a name="remarks"></a>Açıklamalar

Varsa _ *Meta* ! = `EOF`, korumalı sanal üye fonksiyonu öğe ekleme girişiminde ( `char`)\_ *Meta* çıkış arabelleği içine. Bunu çeşitli yöntemlerle yapabilirsiniz:

- Yazma konumunu varsa, bu öğenin yazma konumunu depolamak ve çıkış arabelleği için sonraki işaretçisi Artır.

- Saklı strstreambuf modu denetimli sırası değiştirilebilir, genişletilebilir ve değil dondurulmuş diyorsa işlevi yazma konumunu yeni için çıkış arabelleği ayırarak sunabilirsiniz. Çıkış arabelleği bu şekilde genişletme, ilişkili tüm giriş arabelleği genişletir.

## <a name="pbackfail"></a>  strstreambuf::pbackfail

Bir öğenin Giriş akışı geri koymak dener ve (tarafından sonraki işaretçisi işaret) geçerli öğe yapar korumalı sanal üye işlevi.

```cpp
virtual int pbackfail(int _Meta = EOF);
```

### <a name="parameters"></a>Parametreler

`_Meta` Arabelleğe eklemek için karakter veya `EOF`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarısız olması durumunda, döndürür `EOF`. Aksi halde, eğer _ *Meta* == `EOF`, başka bir değer döndürür `EOF`. Aksi takdirde, döndürür \_ *Meta*.

### <a name="remarks"></a>Açıklamalar

Bir öğe giriş arabelleğe geri alın ve bunu (tarafından sonraki işaretçisi işaret) geçerli öğe yapmak korumalı sanal üye fonksiyonu çalışır.

Varsa _ *Meta* == `EOF`, geri göndermek için etkili bir şekilde akış geçerli öğe zaten bir öğedir. Aksi takdirde, bu öğenin değiştirilmiştir **ch** = ( `char`)\_ *Meta*. İşlev, çeşitli yollarla bir öğe geri koyabilirsiniz:

- Putback konumu varsa ve depolanan öğesi eşit karşılaştırır **ch**, giriş arabelleği için sonraki işaretçisi azaltma.

- Putback konumu varsa ve strstreambuf modu denetimli sırası değiştirilebilir diyorsa işlevi depolayabilir **ch** putback konumu ve azaltma giriş arabelleği için sonraki işaretçisi.

## <a name="pcount"></a>  strstreambuf::pcount

Denetimli sıraya yazılan öğeleri sayısını döndürür.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimli sıraya yazılan öğe sayısını sayısı.

### <a name="remarks"></a>Açıklamalar

Özellikle, [pptr](../standard-library/basic-streambuf-class.md#pptr) null işaretçi işlevi sıfır döndürür. Aksi takdirde, döndürür `pptr`  -  [pbase](../standard-library/basic-streambuf-class.md#pbase).

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

## <a name="seekoff"></a>  strstreambuf::seekoff

Geçerli konumlar denetimli akışlar için alter dener korumalı sanal üye işlevi.

```cpp
virtual streampos seekoff(streamoff _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

`_Off` Göreli olarak için arama konumunu `_Way`.

`_Way` Uzaklık işlemleri için başlangıç noktası. Bkz: [seekdir](../standard-library/ios-base-class.md#seekdir) olası değerler için.

`_Which` İşaretçi konumunun modunu belirtir. Varsayılan konumlar yazma ve okuma değiştirmek izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

Ya da değiştirme işlevi başarılı ya da her ikisini de konumlar akış, sonuç akış konumunu döndürür. Aksi takdirde, başarısız olur ve geçersiz akış konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimli akışlar için geçerli konumlarını değiştirmek korumalı sanal üye fonksiyonu endeavors. Bir sınıf strstreambuf nesne için bir akışı konumu tamamen akış uzaklığını oluşur. Uzaklık sıfır denetimli dizisinin ilk öğesi belirler.

Yeni bir konuma şu şekilde belirlenir:

- Varsa `_Way`  ==  `ios_base::beg`, yeni bir konuma akış artı _ başlangıcıdır *devre dışı*.

- Varsa `_Way`  ==  `ios_base::cur`, yeni konumu geçerli akışı konumu hem _ olan *devre dışı*.

- Varsa `_Way`  ==  `ios_base::end`, yeni bir konuma akış artı _ sonudur *devre dışı*.

Varsa `_Which`  &  **ios_base::in** sıfır dışında olan ve giriş arabelleği var, işlevi giriş arabelleğini okumaya sonraki konuma değiştirir. Varsa `_Which`  &  **ios_base::out** da sıfır olmayan, olan `_Way` ! = **ios_base::cur**ve çıkış arabelleği varsa, işlev ayrıca eşleşecek şekilde yazmak için bir sonraki konuma ayarlar okunacak sonraki konumu.

Aksi halde, eğer `_Which`  &  `ios_base::out` sıfır dışında olan ve çıkış arabelleği varsa, işlev çıkış arabelleğinin yazmak için bir sonraki konuma değiştirir. Aksi takdirde yerleştirme işlemi başarısız olur. Başarılı olması konumlandırma işlemi için sonuçta elde edilen akışı konumu denetimli sırası içinde yer almalıdır.

## <a name="seekpos"></a>  strstreambuf::seekpos

Geçerli konumlar denetimli akışlar için alter dener korumalı sanal üye işlevi.

```cpp
virtual streampos seekpos(streampos _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

`_Sp` Arama konumu.

`_Which` İşaretçi konumunun modunu belirtir. Varsayılan konumlar yazma ve okuma değiştirmek izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

Ya da değiştirme işlevi başarılı ya da her ikisini de konumlar akış, sonuç akış konumunu döndürür. Aksi takdirde, başarısız olur ve geçersiz akış konumunu döndürür. Akışı konumu geçersiz olup olmadığını belirlemek için dönüş değeri ile karşılaştırın `pos_type(off_type(-1))`.

### <a name="remarks"></a>Açıklamalar

Denetimli akışlar için geçerli konumlarını değiştirmek korumalı sanal üye fonksiyonu endeavors. Bir sınıf strstreambuf nesne için bir akışı konumu tamamen akış uzaklığını oluşur. Uzaklık sıfır denetimli dizisinin ilk öğesi belirler. Yeni bir konuma _ tarafından belirlenir *Sp*.

Varsa `_Which`  &  **ios_base::in** sıfır dışında olan ve giriş arabelleği varsa, işlev giriş önbelleğinde okumak için bir sonraki konuma değiştirir. Varsa `_Which`  &  `ios_base::out` sıfır dışında olan ve çıkış arabelleği var, işlevi de okumak için bir sonraki konuma eşleşecek şekilde yazmak için sonraki konumunu ayarlar. Aksi halde, eğer `_Which`  &  `ios_base::out` sıfır dışında olan ve çıkış arabelleği varsa, işlev çıkış arabelleğinin yazmak için bir sonraki konuma değiştirir. Aksi takdirde yerleştirme işlemi başarısız olur. Başarılı olması konumlandırma işlemi için sonuçta elde edilen akışı konumu denetimli sırası içinde yer almalıdır.

## <a name="str"></a>  strstreambuf::Str

Çağrıları [Dondur](#freeze)ve ardından bir işaretçi denetimli sıranın başına döndürür.

```cpp
char *str();
```

### <a name="return-value"></a>Dönüş Değeri

Denetimli dizisi başına bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Açıkça takın sürece sonlandırma null öğe bulunmaktadır.

### <a name="example"></a>Örnek

Bkz: [strstreambuf::freeze](#freeze) kullanan bir örnek için **str**.

## <a name="strstreambuf"></a>  strstreambuf::strstreambuf

Türünde bir nesne oluşturur `strstreambuf`.

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

*_Allocfunc* arabellek bellek ayırmak için kullanılan işlev.

`count` Gösterdiği arabellek uzunluğu belirler `_Getptr`. Varsa `_Getptr` bir bağımsız değişken değil (ilk Oluşturucusu form), önerilen bir ayırma arabellekleri boyutu.

*_Freefunc* arabellek belleği boşaltmak için kullanılan işlev.

`_Getptr` Giriş için kullanılan arabellek.

`_Putptr` Çıktı için kullanılan arabellek.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucusu null işaretçi giriş arabelleği, çıkış arabelleği ve strstreambuf ayırma denetleme tüm işaretçiler içinde depolar. Denetimli sırası değiştirilebilir ve Genişletilebilir olmak için saklı strstreambuf modunu ayarlar. Ayrıca kabul `count` önerilen ilk ayırma boyutu olarak.

İkinci oluşturucu depoladığı dışında _ ilk gibi davranır *Allocfunc* depolama alanı ayırmak için çağrılacak işlev işaretçisi olarak ve \_ *Freefunc* için işlev işaretçisi olarak Bu depolama boşaltmak için çağrısı.

Üç oluşturucular:

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

Ayrıca ilk gibi davranır dışında `_Getptr` denetimli dizisi tutmak için kullanılan dizi nesnesi belirler. (Bu nedenle, onu bir null işaretçinin olmaması gerekir.) Öğe sayısını *N* dizideki şu şekilde belirlenir:

- Varsa (`count` > 0), ardından *N* olan `count`.

- Varsa (`count` == 0), ardından *N* olan `strlen`(( **const** `char` *) `_Getptr` ).

- Varsa (`count` < 0), ardından *N* olan **INT_MAX**.

Varsa `_Putptr` null işaretçi yürüterek işlevi yalnızca bir giriş arabelleği oluşturur:

```cpp
setg(_Getptr,
    _Getptr,
    _Getptr + N);
```

Aksi takdirde yürüterek giriş ve çıkış arabelleği oluşturur:

```cpp
setg(_Getptr,
    _Getptr,
    _Putptr);

setp(_Putptr,
    _Getptr + N);
```

Bu durumda, `_Putptr` aralığında olmalı [ `_Getptr`, `_Getptr`  +  *N*].

Son olarak, üç oluşturucular:

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

Ancak bu saklı modu denetimli sırası değiştirilebilir ne Genişletilebilir yapar.

## <a name="underflow"></a>  strstreambuf::underflow

Giriş akışından geçerli öğe ayıklamak için korumalı bir sanal işlev.

```cpp
virtual int underflow();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarısız olması durumunda, döndürür `EOF`. Aksi takdirde, geçerli öğe Giriş akışı, yukarıda açıklandığı gibi dönüştürülen döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye fonksiyonu endeavors geçerli öğe ayıklamak **ch** giriş arabelleğinden sonra geçerli akışı konumu ilerleyin ve öğesi olarak döndürür (`int`) (`unsigned char`) **ch** . Yalnızca bir yolla bunu yapabilirsiniz: Okuma konumu varsa, sürdüğünü **ch** öğe okuma konumunda depolanan ve giriş arabelleği için sonraki işaretçisi ilerler.

## <a name="see-also"></a>Ayrıca bkz.

[streambuf](../standard-library/streambuf-typedefs.md#streambuf)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
