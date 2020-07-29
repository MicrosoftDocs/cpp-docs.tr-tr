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
ms.openlocfilehash: e6b4df60f4d28839419d02fd3ed6d7cbf73d327f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87202200"
---
# <a name="strstreambuf-class"></a>strstreambuf Sınıfı

Dizi nesnesinde depolanan bir öğe dizisine ve öğesinden öğelerin aktarılmasını denetleyen bir akış arabelleği tanımlar **`char`** .

## <a name="syntax"></a>Sözdizimi

```cpp
class strstreambuf : public streambuf
```

## <a name="remarks"></a>Açıklamalar

Nesnenin nasıl oluşturulduğuna bağlı olarak, dizideki değişikliklere uyum sağlamak için gerektiğinde ayrılabilir, genişletilebilir ve serbest bırakılmış olabilir.

Sınıfının bir nesnesi `strstreambuf` , modu gibi birkaç bit mod bilgisini depolar `strstreambuf` . Bu bitler denetimli sıranın olup olmadığını gösterir:

- Ayrıldı ve sonunda serbest bırakılmalıdır.

- Değiştirilebilir.

- , Depolama alanı realolarak eklenerek genişletilebilir.

- Dondurulmuş ve bu nedenle nesne yok edilirken veya (ayrılmışsa) nesne dışında bir acenteden önce dondurulmamış olması gerekir.

Dondurulmuş olan denetimli bir sıra, bu ayrı mod bitlerinin durumundan bağımsız olarak değiştirilemez veya genişletilemez.

Nesne Ayrıca, ayırmayı denetleyen iki işleve işaretçiler depolar `strstreambuf` . Bunlar null işaretçilerse, nesne, denetimli sıra için depolamayı ayırmak ve serbest bırakma yöntemine sahiptir.

> [!NOTE]
> Bu sınıf kullanım dışıdır. Bunun yerine [stringarabelleğe](../standard-library/sstream-typedefs.md#stringbuf) veya [wstringarabelleğe](../standard-library/sstream-typedefs.md#wstringbuf) kullanmayı düşünün.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[strstreambuf](#strstreambuf)|Türünde bir nesne oluşturur `strstreambuf` .|

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

**Üst bilgi:**\<strstream>

**Ad alanı:** std

## <a name="strstreambuffreeze"></a><a name="freeze"></a>strstreamarabelleğe:: Freeze

Akış arabelleği işlemleri aracılığıyla akış arabelleğinin kullanılamamasına neden olur.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Parametreler

*_Freezeit*\
**`bool`** Akışın dondurulmuş olmasını isteyip istemediğinizi belirten bir.

### <a name="remarks"></a>Açıklamalar

*_Freezeit* true ise, işlev, `strstreambuf` denetlenen diziyi dondurulmuş hale getirmek için saklı modu değiştirir. Aksi takdirde, denetlenen sıranın dondurulmuş olmasını sağlar.

[Str](#str) şunları belirtir `freeze` .

> [!NOTE]
> Dondurulmuş bir arabellek, yok etme sırasında serbest bırakılmaz `strstreambuf` . Bellek sızıntısını önlemek için, serbest bırakmadan önce arabelleği ortadan kaldırmalısınız.

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

## <a name="strstreambufoverflow"></a><a name="overflow"></a>strstreamarabelleğe:: overflow

Tam arabelleğe yeni bir karakter eklendiğinde çağrılabilen, korunan bir sanal işlev.

```cpp
virtual int overflow(int _Meta = EOF);
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `EOF` .

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olmazsa, döndürür `EOF` . Aksi takdirde, * \_ meta*ise dışında  ==  `EOF` bir değer döndürür `EOF` . Aksi takdirde, * \_ meta*döndürür.

### <a name="remarks"></a>Açıklamalar

Eğer * \_ meta* ! = ise `EOF` , korumalı sanal üye işlevi öğeyi çıkış arabelleğine eklemeye çalışır `(char)_Meta` . Bunu çeşitli yollarla yapabilirsiniz:

- Bir yazma konumu varsa, öğeyi yazma konumuna kaydedebilir ve çıkış arabelleği için sonraki işaretçiyi artırabilirsiniz.

- Saklı strstreammode, denetlenen sıranın değiştirilebilir, genişletilebilir ve dondurulmuş olduğunu söyyorsa, bu işlev çıktı arabelleği için yeni ayırarak bir yazma konumu kullanılabilir hale getirir. Çıkış arabelleğini bu şekilde genişletmek, ilişkili giriş arabelleğini de genişletir.

## <a name="strstreambufpbackfail"></a><a name="pbackfail"></a>strstreamarabelleğe::p backfail

Giriş akışına bir öğe geri döndürmeye çalışan korumalı bir sanal üye işlevi ve ardından bunu geçerli öğe yapar (sonraki işaretçinin gösterdiği).

```cpp
virtual int pbackfail(int _Meta = EOF);
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `EOF` .

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olmazsa, döndürür `EOF` . Aksi takdirde, * \_ meta*ise dışında  ==  `EOF` bir değer döndürür `EOF` . Aksi takdirde, * \_ meta*döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, giriş arabelleğine bir öğe geri döndürmeye çalışır ve sonra geçerli öğe (sonraki işaretçinin gösterdiği) yapar.

Eğer * \_ meta*ise  ==  `EOF` , geri gönderme öğesi geçerli öğeden önceki bir akışta etkin bir şekilde zaten var. Aksi takdirde, bu öğe ile değiştirilmiştir `ch = (char)_Meta` . İşlevi bir öğeyi çeşitli yollarla geri alabilir:

- Bir Putback konumu varsa ve şuna eşit olarak karşılaştırıldığı öğe, `ch` giriş arabelleği için bir sonraki işaretçiyi azaledebilir.

- Bir Putback konumu varsa ve strstreambuffer modu denetlenen diziyi değiştirilebilir ise, işlev `ch` putback konumunu saklayabilir ve giriş arabelleği için bir sonraki işaretçiyi azaltır.

## <a name="strstreambufpcount"></a><a name="pcount"></a>strstreamarabelleğe::p sayısı

Denetlenen diziye yazılan öğe sayısının sayısını döndürür.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen diziye yazılan öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Özellikle, [pptr](../standard-library/basic-streambuf-class.md#pptr) null işaretçisiyse, işlev sıfır döndürür. Aksi takdirde, `pptr`  -  [pbase](../standard-library/basic-streambuf-class.md#pbase)döndürür.

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

## <a name="strstreambufseekoff"></a><a name="seekoff"></a>strstreamarabelleğe:: seekoff

Denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışan korumalı bir sanal üye işlevi.

```cpp
virtual streampos seekoff(streamoff _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Off*\
*_Way*göreli olarak arama konumu.

*_Way*\
Dengeleme işlemleri için başlangıç noktası. Olası değerler için bkz. [seekdir](../standard-library/ios-base-class.md#seekdir) .

*_Which*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin verir.

### <a name="return-value"></a>Dönüş Değeri

İşlev ya da her iki akış konumunu değiştirme içinde başarılı olursa, sonuç akış konumunu döndürür. Aksi takdirde, başarısız olur ve geçersiz bir akış konumu döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları endeavors. Strstreamarabelleğe sınıfının bir nesnesi için bir akış konumu yalnızca bir akış sapmasını içerir. Sıfır değeri, denetlenen dizinin ilk öğesini belirler.

Yeni konum aşağıdaki gibi belirlenir:

- İse `_Way == ios_base::beg` , yeni konum akışın başıdır ve *_Off*.

- İse `_Way == ios_base::cur` , yeni konum geçerli akış konumu artı *_Off*.

- İse `_Way == ios_base::end` , yeni konum akışın sonu artı *_Off*.

`_Which & ios_base::in`Sıfır değilse ve giriş arabelleği varsa, işlev giriş arabelleğinde okunacak bir sonraki konumu değiştirir. `_Which & ios_base::out`Ayrıca sıfır dışında bir değer varsa `_Way != ios_base::cur` ve çıkış arabelleği varsa, işlev, sonraki konumu okumak için de bir sonraki konumdan eşleşecek şekilde ayarlar.

Aksi halde, `_Which & ios_base::out` sıfır değilse ve çıkış arabelleği varsa, işlev sonraki konumu çıkış arabelleğine yazmak için değiştirir. Aksi takdirde, konumlandırma işlemi başarısız olur. Konumlandırma işleminin başarılı olması için, elde edilen akış konumu denetimli sıra içinde olmalıdır.

## <a name="strstreambufseekpos"></a><a name="seekpos"></a>strstreamarabelleğe:: seekpos

Denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışan korumalı bir sanal üye işlevi.

```cpp
virtual streampos seekpos(streampos _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*\
Arama yapılacak konum.

*_Which*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin verir.

### <a name="return-value"></a>Dönüş Değeri

İşlev ya da her iki akış konumunu değiştirme içinde başarılı olursa, sonuç akış konumunu döndürür. Aksi takdirde, başarısız olur ve geçersiz bir akış konumu döndürür. Akış konumunun geçersiz olup olmadığını anlamak için dönüş değerini ile karşılaştırın `pos_type(off_type(-1))` .

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları endeavors. Strstreamarabelleğe sınıfının bir nesnesi için bir akış konumu yalnızca bir akış sapmasını içerir. Sıfır değeri, denetlenen dizinin ilk öğesini belirler. Yeni konum *_Sp*belirlenir.

`_Which`  &  **İos_base:: ın** sıfır değilse ve giriş arabelleği varsa, işlev giriş arabelleğinde okunacak bir sonraki konumu değiştirir. `_Which`  &  `ios_base::out` Sıfır dışında ise ve çıkış arabelleği varsa, bu işlev bir sonraki konumu okumak üzere bir sonraki konumdan eşleşecek şekilde de ayarlar. Aksi halde, `_Which`  &  `ios_base::out` sıfır değilse ve çıkış arabelleği varsa, işlev sonraki konumu çıkış arabelleğine yazmak için değiştirir. Aksi takdirde, konumlandırma işlemi başarısız olur. Konumlandırma işleminin başarılı olması için, elde edilen akış konumu denetimli sıra içinde olmalıdır.

## <a name="strstreambufstr"></a><a name="str"></a>strstreamarabelleğe:: Str

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

## <a name="strstreambufstrstreambuf"></a><a name="strstreambuf"></a>strstreamarabelleğe:: strstreamarabelleğe

Türünde bir nesne oluşturur `strstreambuf` .

```cpp
explicit strstreambuf(streamsize count = 0);

strstreambuf(void (* alloc_func)(size_t),
    void (* free_func)(void*));

strstreambuf(char* getptr,
    streamsize count,
    char* putptr = 0);

strstreambuf(signed char* getptr,
    streamsize count,
    signed char* putptr = 0);

strstreambuf(unsigned char* getptr,
    streamsize count,
    unsigned char* putptr = 0);

strstreambuf(const char* getptr,
    streamsize count);

strstreambuf(const signed char* getptr,
    streamsize count);

strstreambuf(const unsigned char* getptr,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*alloc_func*\
Arabellek belleği ayırmak için kullanılan işlev.

*biriktirme*\
*Getptr*tarafından işaret edilen arabelleğin uzunluğunu belirler. *Getptr* bir bağımsız değişken (ilk Oluşturucu formu) değilse, arabellekler için önerilen bir ayırma boyutu.

*_Freefunc*\
Arabellek belleğini serbest bırakmak için kullanılan işlev.

*getptr*\
Giriş için kullanılan bir arabellek.

*putptr*\
Çıktı için kullanılan bir arabellek.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, giriş arabelleğini, çıkış arabelleğini ve strstreambuffer ayırmayı denetleyen tüm işaretçilerde boş bir işaretçi depolar. Denetlenen sırayı değiştirilebilir ve Genişletilebilir hale getirmek için depolanan strstreammode modunu ayarlar. Ayrıca, önerilen ilk ayırma boyutu olarak *Count* kabul eder.

İkinci Oluşturucu ilk gibi davranır, ancak depolama alanını ayırmak için çağrılacak işlevin işaretçisi olarak *alloc_func* depolar ve bu depolama alanını serbest bırakmak için çağrılacak işlevin işaretçisi olarak *free_func* .

Üç Oluşturucu:

```cpp
strstreambuf(char *getptr,
    streamsize count,
    char *putptr = 0);

strstreambuf(signed char *getptr,
    streamsize count,
    signed char *putptr = 0);

strstreambuf(unsigned char *getptr,
    streamsize count,
    unsigned char *putptr = 0);
```

aynı zamanda, *getptr* 'nin denetimli sırayı tutmak için kullanılan dizi nesnesini sıralaması dışında, ilki gibi davranır. (Bu nedenle, null bir işaretçi olmaması gerekir.) Dizideki *öğelerin sayısı* şu şekilde belirlenir:

- (*Sayı* > 0 *) ise,* *N* sayılır.

- If (*Count* = = 0), sonra *N* , `strlen((const char *) getptr )` .

- (*Sayı* < 0) Ise, *N* **INT_MAX**.

*Putptr* null işaretçisiyse, işlev yalnızca şunu yürüterek bir giriş arabelleği oluşturur:

```cpp
setg(getptr,
    getptr,
    getptr + N);
```

Aksi takdirde, şunu yürüterek hem giriş hem de çıkış arabellekleri kurar:

```cpp
setg(getptr,
    getptr,
    putptr);

setp(putptr,
    getptr + N);
```

Bu durumda, *putptr* [ *getptr*, *getptr*  +  *N*] aralığında olmalıdır.

Son olarak, üç Oluşturucu:

```cpp
strstreambuf(const char *getptr,
    streamsize count);

strstreambuf(const signed char *getptr,
    streamsize count);

strstreambuf(const unsigned char *getptr,
    streamsize count);
```

tümü aynı şekilde davranır:

```cpp
streambuf((char *)getptr, count);
```

saklı mod, denetimli sırayı değiştirilebilir veya Genişletilebilir olarak yapmaz.

## <a name="strstreambufunderflow"></a><a name="underflow"></a>strstreamarabelleğe:: yetersiz

Giriş akışından geçerli öğeyi ayıklamak için korunan bir sanal işlev.

```cpp
virtual int underflow();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olmazsa, döndürür `EOF` . Aksi halde, yukarıda açıklandığı gibi dönüştürülmüş olarak, giriş akışındaki geçerli öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, geçerli öğeyi `ch` giriş arabelleğinden ayıklamak için endeavors, sonra geçerli akış konumunu ilerletin ve öğesini olarak döndürür `(int)(unsigned char)ch` . Bunu yalnızca bir şekilde yapabilir: bir okuma konumu kullanılabiliyorsa, `ch` okuma konumunda depolanan öğe olarak alır ve giriş arabelleği için bir sonraki işaretçiyi ilerletir.

## <a name="see-also"></a>Ayrıca bkz.

[streambuf](../standard-library/streambuf-typedefs.md#streambuf)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
