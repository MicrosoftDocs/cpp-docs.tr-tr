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
ms.openlocfilehash: 75c9a96b727ef60280055536296f850f492d16ac
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327310"
---
# <a name="strstreambuf-class"></a>strstreambuf Sınıfı

Depolanan öğelerin bir dizisi gelen ve giden öğeleri aktarımını denetleyen bir akış arabelleğinin açıklayan bir **char** dizi nesnesi.

## <a name="syntax"></a>Sözdizimi

```cpp
class strstreambuf : public streambuf
```

## <a name="remarks"></a>Açıklamalar

Nesne nasıl oluşturulur bağlı olarak, ayrılmış, genişletilebilir ve değişiklikler sıralamadaki sığdırmak için gerektiği şekilde serbest.

Sınıfın bir nesnesi `strstreambuf` birkaç BITS modu bilgileri depolar, `strstreambuf` modu. Bu bit göstermek isteyip denetlenen dizi:

- Ayrıldı ve sonunda boşaltılması gerekiyor.

- Değiştirilebilir olur.

- Depolama tahsis tarafından Genişletilebilir olarak var.

- Dondurulmuş ve bu nedenle nesne dışındaki bir kurum tarafından nesne yok veya (ayırdığınızda) serbest önce çözülmüş gerekir.

Dondurulmuş denetlenen bir dizi değiştirilemez veya genişletilmiş, bu ayrı modu BITS durumu ne olursa olsun.

Nesneyi de denetleyen iki işlev işaretçileri depolar `strstreambuf` ayırma. Null işaretçiler bunlar, nesne ayırma ve serbest bırakma denetlenen dizi için depolama kendi yöntemi devises.

> [!NOTE]
> Bu sınıf kullanımdan kaldırılmıştır. Kullanmayı [stringbuf](../standard-library/sstream-typedefs.md#stringbuf) veya [wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf) yerine.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[strstreambuf](#strstreambuf)|Türünde bir nesne oluşturur `strstreambuf`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Dondurma](#freeze)|Akış Arabellek işlemleri kullanılabilir olması bir akış arabelleğinin neden olur.|
|[taşma](#overflow)|Yeni bir karakteri tam bir arabelleğe eklendiğinde çağrılabilir korumalı sanal işlev.|
|[pbackfail](#pbackfail)|Yerleştirmeye çalıştığında bir korumalı sanal üye işlevi bir öğe giriş akışa geri ve bunu geçerli öğe (sonraki işaretçisi tarafından işaret edilen) yapın.|
|[pcount](#pcount)|Denetlenen dizi için yazılan öğelerin sayısını döndürür.|
|[seekoff](#seekoff)|Denetlenen akışlar için geçerli konumları alter dener ve korumalı sanal üye işlevi.|
|[seekpos](#seekpos)|Denetlenen akışlar için geçerli konumları alter dener ve korumalı sanal üye işlevi.|
|[str](#str)|Çağrıları [dondurma](#freeze)ve denetlenen dizinin başlangıcı için bir işaretçi döndürür.|
|[yetersiz kalması](#underflow)|Geçerli öğe girdi akışından ayıklanacak korumalı bir sanal işlev.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<strstream >

**Namespace:** std

## <a name="freeze"></a>  strstreambuf::Freeze

Akış Arabellek işlemleri kullanılabilir olması bir akış arabelleğinin neden olur.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Parametreler

*_Freezeit*<br/>
A **bool** donabilir akış isteyip istemediğinizi belirten.

### <a name="remarks"></a>Açıklamalar

Varsa *_Freezeit* işlevi değiştirir saklanan true ise `strstreambuf` yapmak dondurulmuş denetlenen dizi için mod. Aksi takdirde, denetlenen dizideki değil dondurulmuş kolaylaştırır.

[str](#str) gelir `freeze`.

> [!NOTE]
> Dondurulmuş bir arabellek sırasında boşaltılacak değil `strstreambuf` yok etme. Bir bellek sızıntısı önlemek için serbest önce arabellek Çöz gerekir.

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

Yeni bir karakteri tam bir arabelleğe eklendiğinde çağrılabilir korumalı sanal işlev.

```cpp
virtual int overflow(int _Meta = EOF);
```

### <a name="parameters"></a>Parametreler

*_Meta*<br/>
Karakter arabelleğine ekleme veya `EOF`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürür `EOF`. Aksi takdirde  *\_Meta* == `EOF`, dışında bir değer döndürür `EOF`. Aksi halde  *\_Meta*.

### <a name="remarks"></a>Açıklamalar

Varsa  *\_Meta* ! = `EOF`, korumalı sanal üye işlevi öğe ekleme girişiminde `(char)_Meta` çıktı arabelleğine. Bunu çeşitli yöntemlerle yapabilirsiniz:

- Yazma konumunu varsa, bu öğe yazma konumuna depolayabilir ve çıkış arabelleği için sonraki işaretçisine artırılacak.

- Saklı strstreambuf modu denetlenen dizideki değiştirilebilir, genişletilebilir ve değil dondurulmuş bildiriliyorsa, işlev yazma konumunu kullanılabilir yeni çıkış arabelleği için ayırarak yapabilirsiniz. Çıkış arabelleği bu şekilde genişleterek, ilişkili tüm giriş arabelleği genişletir.

## <a name="pbackfail"></a>  strstreambuf::pbackfail

Bir öğe giriş akışa geri yerleştirmek çalışır ve ardından (sonraki işaretçisi tarafından işaret edilen) geçerli öğe yapar korumalı sanal üye işlevi.

```cpp
virtual int pbackfail(int _Meta = EOF);
```

### <a name="parameters"></a>Parametreler

*_Meta*<br/>
Karakter arabelleğine ekleme veya `EOF`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürür `EOF`. Aksi takdirde  *\_Meta* == `EOF`, dışında bir değer döndürür `EOF`. Aksi halde  *\_Meta*.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, bir öğe giriş arabelleğe geri yerleştirin ve ardından (sonraki işaretçisi tarafından işaret edilen) geçerli öğe kolaylaştırmak çalışır.

Varsa  *\_Meta* == `EOF`, geri göndermek için etkili bir şekilde akış önce geçerli öğe zaten bir öğedir. Aksi takdirde, bu öğe tarafından değiştirilir `ch = (char)_Meta`. İşlevi, öğenin çeşitli yollarla geri koyabilirsiniz:

- Putback konum kullanılabilir ve burada depolanan öğenin eşit karşılaştırır `ch`, sonraki işaretçisi giriş arabelleği için azaltma.

- Putback konum kullanılabilir ve strstreambuf modu denetlenen dizideki değiştirilebilir bildiriliyorsa, işlev depolayabilirsiniz `ch` putback konumu ve azaltma için giriş arabelleği sonraki işaretçisi.

## <a name="pcount"></a>  strstreambuf::pcount

Denetlenen dizi için yazılan öğelerin sayısını döndürür.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen dizi için yazılan öğelerin sayısını sayısı.

### <a name="remarks"></a>Açıklamalar

Özellikle, [pptr](../standard-library/basic-streambuf-class.md#pptr) null bir işaretçiyse, sıfır döndürür. Aksi halde `pptr`  -  [pbase](../standard-library/basic-streambuf-class.md#pbase).

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

Denetlenen akışlar için geçerli konumları alter dener ve korumalı sanal üye işlevi.

```cpp
virtual streampos seekoff(streamoff _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Off*<br/>
Arama için göreli konumunu *_Way*.

*_Way*<br/>
İşlemleri için başlangıç noktası. Bkz: [seekdir](../standard-library/ios-base-class.md#seekdir) için olası değerler.

*_Which*<br/>
İşaretçisi konumunu modunu belirtir. Değiştirme okuma ve yazma konumları olanak tanımak için varsayılandır.

### <a name="return-value"></a>Dönüş Değeri

İşlev ya da değiştirme başarılı ya da her ikisini de konumları akış sonuç akış konumu döndürür. Aksi takdirde başarısız olur ve geçersiz akış konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Denetlenen akışlar için geçerli konumları değiştirmek korumalı sanal üye işlevi endeavors. Strstreambuf sınıfı nesne için bir akış konumu bir akış uzaklığı tamamen oluşur. Uzaklık sıfır değerinin denetlenen dizideki ilk öğeyi belirtir.

Yeni konumu şu şekilde belirlenir:

- Varsa `_Way == ios_base::beg`, artı akış başlangıcına yeni konumudur *_Off*.

- Varsa `_Way == ios_base::cur`, yeni konumu geçerli stream konumudur yanı sıra *_Off*.

- Varsa `_Way == ios_base::end`, artı akışın sonuna yeni konumudur *_Off*.

Varsa `_Which & ios_base::in` sıfır dışında olan ve giriş arabelleği var, işlev giriş arabelleğinde okumak için bir sonraki konuma değiştirir. Varsa `_Which & ios_base::out` de sıfır olan `_Way != ios_base::cur`ve çıkış arabelleği var, işlev ayrıca okumak için bir sonraki konuma eşleşecek şekilde yazmak için bir sonraki konuma ayarlar.

Aksi takdirde `_Which & ios_base::out` sıfır dışında olan ve çıkış arabelleği var, çıkış arabelleğinin yazmak için bir sonraki konuma işlevi değiştirir. Aksi takdirde, yerleştirme işlemi başarısız olur. Başarılı olması yerleştirme işlemi için akış konumu, denetlenen bir dizi içinde yer almalıdır.

## <a name="seekpos"></a>  strstreambuf::seekpos

Denetlenen akışlar için geçerli konumları alter dener ve korumalı sanal üye işlevi.

```cpp
virtual streampos seekpos(streampos _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*<br/>
Arama konumu.

*_Which*<br/>
İşaretçisi konumunu modunu belirtir. Değiştirme okuma ve yazma konumları olanak tanımak için varsayılandır.

### <a name="return-value"></a>Dönüş Değeri

İşlev ya da değiştirme başarılı ya da her ikisini de konumları akış sonuç akış konumu döndürür. Aksi takdirde başarısız olur ve geçersiz akış konumunu döndürür. Akış konumu geçersiz olup olmadığını belirlemek için dönüş değeri ile karşılaştırmak `pos_type(off_type(-1))`.

### <a name="remarks"></a>Açıklamalar

Denetlenen akışlar için geçerli konumları değiştirmek korumalı sanal üye işlevi endeavors. Strstreambuf sınıfı nesne için bir akış konumu bir akış uzaklığı tamamen oluşur. Uzaklık sıfır değerinin denetlenen dizideki ilk öğeyi belirtir. Yeni konumu tarafından belirlenir *_Sp*.

Varsa `_Which`  &  **ios_base::in** sıfır dışında olan ve giriş arabelleği var, işlev giriş arabelleğinde okumak için bir sonraki konuma değiştirir. Varsa `_Which`  &  `ios_base::out` sıfır dışında olan ve çıkış arabelleği var, işlev ayrıca okumak için bir sonraki konuma eşleşecek şekilde yazmak için bir sonraki konuma ayarlar. Aksi takdirde `_Which`  &  `ios_base::out` sıfır dışında olan ve çıkış arabelleği var, çıkış arabelleğinin yazmak için bir sonraki konuma işlevi değiştirir. Aksi takdirde, yerleştirme işlemi başarısız olur. Başarılı olması yerleştirme işlemi için akış konumu, denetlenen bir dizi içinde yer almalıdır.

## <a name="str"></a>  strstreambuf::Str

Çağrıları [dondurma](#freeze)ve denetlenen dizinin başlangıcı için bir işaretçi döndürür.

```cpp
char *str();
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen dizinin başlangıcına bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir açıkça Ekle sürece herhangi bir sonlandırıcı null öğe yok.

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

*_Allocfunc*<br/>
Arabellek bellek ayırmak için kullanılan işlev.

*Sayısı*<br/>
Tarafından işaret edilen arabellek uzunluğunu belirler *_Getptr*. Varsa *_Getptr* bir bağımsız değişkeni değil (ilk Oluşturucusu formu), önerilen bir ayırma için arabellek boyutu.

*_Freefunc*<br/>
Arabellek belleği boşaltmak için kullanılan işlev.

*_Getptr*<br/>
Giriş için kullanılan arabellek.

*_Putptr*<br/>
Çıkış için kullanılan arabellek.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu giriş arabelleği, çıkış arabelleği ve strstreambuf ayırma denetleme tüm işaretçilerin null bir işaretçi depolar. Denetlenen dizi değiştirilebilir ve Genişletilebilir olmak için saklı strstreambuf modu ayarlar. Ayrıca kabul *sayısı* önerilen ilk ayırma boyutu.

Depoladığı dışında İkinci kurucu ilk gibi davranır  *\_Allocfunc* ayrılacak çağrılacak işlev işaretçisi olarak ve  *\_Freefunc* işaretçi Bu depolama alanı boşaltmak için aranacak işlev için.

Üç Oluşturucusu:

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

Ayrıca ilk gibi davranır dışında `_Getptr` denetlenen dizideki tutmak için kullanılan bir dizi nesnesi atar. (Bu nedenle, bir null işaretçi olmamalıdır.) Öğe sayısı *N* dizide şu şekilde belirlenir:

- Varsa (`count` > 0), ardından *N* olduğu `count`.

- Varsa (`count` == 0), ardından *N* olduğu `strlen`(( **const** `char` *) `_Getptr` ).

- Varsa (`count` < 0), ardından *N* olduğu **INT_MAX**.

Varsa `_Putptr` null bir işaretçiyse, yürüterek işlevi yalnızca bir giriş arabellek oluşturur:

```cpp
setg(_Getptr,
    _Getptr,
    _Getptr + N);
```

Aksi takdirde, yürüterek giriş ve çıkış arabellekleri kurar:

```cpp
setg(_Getptr,
    _Getptr,
    _Putptr);

setp(_Putptr,
    _Getptr + N);
```

Bu durumda, `_Putptr` aralık olmalıdır [ `_Getptr`, `_Getptr`  +  *N*].

Son olarak, üç Oluşturucusu:

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

dışında değiştirilebilir ve Genişletilebilir denetlenen dizideki saklı modu sağlar.

## <a name="underflow"></a>  strstreambuf::underflow

Geçerli öğe girdi akışından ayıklanacak korumalı bir sanal işlev.

```cpp
virtual int underflow();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürür `EOF`. Aksi takdirde, yukarıda açıklanan şekilde dönüştürülür giriş akışında geçerli öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi endeavors geçerli öğe ayıklanacak `ch` giriş arabellek, ardından geçerli stream konumuna ilerleyin ve öğenin döndürür (`int`) (`unsigned char`) **ch**. Yalnızca bir yolla bunu yapabilirsiniz: Okuma konumuna kullanılabilir haldeyse, sürdüğünü `ch` öğesi salt okunur bir konumda depolanan ve giriş arabelleği için sonraki işaretçisi ilerler.

## <a name="see-also"></a>Ayrıca bkz.

[streambuf](../standard-library/streambuf-typedefs.md#streambuf)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
