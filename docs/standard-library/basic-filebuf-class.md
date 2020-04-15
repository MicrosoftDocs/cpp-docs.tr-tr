---
title: basic_filebuf Sınıfı
ms.date: 11/04/2016
f1_keywords:
- fstream/std::basic_filebuf
- fstream/std::basic_filebuf::char_type
- fstream/std::basic_filebuf::int_type
- fstream/std::basic_filebuf::off_type
- fstream/std::basic_filebuf::pos_type
- fstream/std::basic_filebuf::traits_type
- fstream/std::basic_filebuf::close
- fstream/std::basic_filebuf::is_open
- fstream/std::basic_filebuf::open
- fstream/std::basic_filebuf::overflow
- fstream/std::basic_filebuf::pbackfail
- fstream/std::basic_filebuf::seekoff
- fstream/std::basic_filebuf::seekpos
- fstream/std::basic_filebuf::setbuf
- fstream/std::basic_filebuf::Swap
- fstream/std::basic_filebuf::sync
- fstream/std::basic_filebuf::uflow
- fstream/std::basic_filebuf::underflow
helpviewer_keywords:
- std::basic_filebuf [C++]
- std::basic_filebuf [C++], char_type
- std::basic_filebuf [C++], int_type
- std::basic_filebuf [C++], off_type
- std::basic_filebuf [C++], pos_type
- std::basic_filebuf [C++], traits_type
- std::basic_filebuf [C++], close
- std::basic_filebuf [C++], is_open
- std::basic_filebuf [C++], open
- std::basic_filebuf [C++], overflow
- std::basic_filebuf [C++], pbackfail
- std::basic_filebuf [C++], seekoff
- std::basic_filebuf [C++], seekpos
- std::basic_filebuf [C++], setbuf
- std::basic_filebuf [C++], Swap
- std::basic_filebuf [C++], sync
- std::basic_filebuf [C++], uflow
- std::basic_filebuf [C++], underflow
ms.assetid: 3196ba5c-bf38-41bd-9a95-70323ddfca1a
ms.openlocfilehash: 35bed08f2495c971df7f79f62e32b3ff68dfb3d2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376878"
---
# <a name="basic_filebuf-class"></a>basic_filebuf Sınıfı

Karakter özellikleri *Tr*sınıfı tarafından belirlenen tip *Char_T*öğelerinin dış dosyada depolanan bir dizi öğeye ve bu öğelerden iletimini kontrol eden bir akış arabelleği açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Char_T, class Tr = char_traits<Char_T>>
class basic_filebuf : public basic_streambuf<Char_T, Tr>
```

### <a name="parameters"></a>Parametreler

*Char_T*\
Dosya arabelleği temel öğesi.

*Tr*\
Dosya arabelleği temel öğesinin özellikleri `char_traits<Char_T>`(genellikle).

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, karakter özellikleri *Tr*sınıfı tarafından belirlenen tür *Char_T*öğelerinin dış dosyada depolanan bir dizi öğeye ve bu öğelerden gelen bir akış arabelleği açıklar.

> [!NOTE]
> Tür `basic_filebuf` nesneleri, Char_T türü *parametresi*tarafından `char_type` belirtilen ne olursa olsun türü __char\* __ bir iç arabellek ile oluşturulur. Bu, iç arabelleğe yazılmadan önce bir Unicode dizesi **(wchar_t** karakter içeren) bir ANSI dizesine **(char** karakterleri içeren) dönüştürüleceği anlamına gelir. Unicode dizeleri arabellekte depolamak **için, wchar_t** türünden yeni bir [`basic_streambuf::pubsetbuf`](../standard-library/basic-streambuf-class.md#pubsetbuf) `()` arabellek oluşturun ve yöntemi kullanarak ayarlayın. Bu davranışı gösteren bir örnek görmek için aşağıya bakın.

Sınıfın `basic_filebuf<Char_T, Tr>` bir nesnesi, açık bir `FILE` dosyayla ilişkili akışı denetleyen nesneyi belirleyen bir dosya işaretçisi depolar. Ayrıca, işaretçileri korumalı üye [işlevler taşma](#overflow) ve alt [akış](#underflow)tarafından kullanılmak üzere iki dosya dönüştürme yönü depolar. Daha fazla bilgi [`basic_filebuf::open`](#open)için bkz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, türündeki `basic_filebuf<wchar_t>` bir nesneyi `pubsetbuf()` yöntemi çağırarak Unicode karakterlerini iç arabelleğinde depolamaya nasıl zorlayacağını gösterir.

```cpp
// unicode_basic_filebuf.cpp
// compile with: /EHsc

#include <iostream>
#include <string>
#include <fstream>
#include <iomanip>
#include <memory.h>
#include <string.h>

#define IBUFSIZE 16

using namespace std;

void hexdump(const string& filename);

int main()
{
    wchar_t* wszHello = L"Hello World";
    wchar_t wBuffer[128];

    basic_filebuf<wchar_t> wOutFile;

    // Open a file, wcHello.txt, then write to it, then dump the
    // file's contents in hex
    wOutFile.open("wcHello.txt",
        ios_base::out | ios_base::trunc | ios_base::binary);
    if(!wOutFile.is_open())
    {
        cout << "Error Opening wcHello.txt\n";
        return -1;
    }
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));
    wOutFile.close();
    cout << "Hex Dump of wcHello.txt - note that output is ANSI chars:\n";
    hexdump(string("wcHello.txt"));

    // Open a file, wwHello.txt, then set the internal buffer of
    // the basic_filebuf object to be of type wchar_t, then write
    // to the file and dump the file's contents in hex
    wOutFile.open("wwHello.txt",
        ios_base::out | ios_base::trunc | ios_base::binary);
    if(!wOutFile.is_open())
    {
        cout << "Error Opening wwHello.txt\n";
        return -1;
    }
    wOutFile.pubsetbuf(wBuffer, (streamsize)128);
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));
    wOutFile.close();
    cout << "\nHex Dump of wwHello.txt - note that output is wchar_t chars:\n";
    hexdump(string("wwHello.txt"));

    return 0;
}

// dump contents of filename to stdout in hex
void hexdump(const string& filename)
{
    fstream ifile(filename.c_str(),
        ios_base::in | ios_base::binary);
    char *ibuff = new char[IBUFSIZE];
    char *obuff = new char[(IBUFSIZE*2)+1];
    int i;

    if(!ifile.is_open())
    {
        cout << "Cannot Open " << filename.c_str()
             << " for reading\n";
        return;
    }
    if(!ibuff || !obuff)
    {
        cout << "Cannot Allocate buffers\n";
        ifile.close();
        return;
    }

    while(!ifile.eof())
    {
        memset(obuff,0,(IBUFSIZE*2)+1);
        memset(ibuff,0,IBUFSIZE);
        ifile.read(ibuff,IBUFSIZE);

        // corner case where file is exactly a multiple of
        // 16 bytes in length
        if(ibuff[0] == 0 && ifile.eof())
            break;

        for(i = 0; i < IBUFSIZE; i++)
        {
            if(ibuff[i] >= ' ')
                obuff[i] = ibuff[i];
            else
                obuff[i] = '.';

            cout << setfill('0') << setw(2) << hex
                 << (int)ibuff[i] << ' ';
        }
        cout << "  " << obuff << endl;
    }
    ifile.close();
}
```

```Output
Hex Dump of wcHello.txt - note that output is ANSI chars:
48 65 6c 6c 6f 20 57 6f 72 6c 64 00 00 00 00 00   Hello World.....

Hex Dump of wwHello.txt - note that output is wchar_t chars:
48 00 65 00 6c 00 6c 00 6f 00 20 00 57 00 6f 00   H.e.l.l.o. .W.o.
72 00 6c 00 64 00 00 00 00 00 00 00 00 00 00 00   r.l.d...........
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Basic_filebuf](#basic_filebuf)|Türünde `basic_filebuf`bir nesne oluşturuyor.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|Bir tür adını `Char_T` şablon parametresi ile ilişkilendirer.|
|[Int_type](#int_type)|Bu türü `basic_filebuf`'kapsamı içinde, `Tr` kapsamdaki aynı adın türüne eşdeğer hale getirir.|
|[off_type](#off_type)|Bu türü `basic_filebuf`'kapsamı içinde, `Tr` kapsamdaki aynı adın türüne eşdeğer hale getirir.|
|[pos_type](#pos_type)|Bu türü `basic_filebuf`'kapsamı içinde, `Tr` kapsamdaki aynı adın türüne eşdeğer hale getirir.|
|[traits_type](#traits_type)|Bir tür adını `Tr` şablon parametresi ile ilişkilendirer.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Yakın](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Dosyanın açık olup olmadığını gösterir.|
|[açık](#open)|Bir dosyayı açar.|
|[Taşma](#overflow)|Tam bir arabelleğe yeni bir karakter eklendiğinde çağrılabilen korumalı sanal işlev.|
|[pbackfail](#pbackfail)|Korumalı sanal üye işlevi giriş akışına bir öğegeri koymak için çalışır, sonra geçerli öğe (sonraki işaretçi tarafından işaret) olun.|
|[seekoff](#seekoff)|Korumalı sanal üye işlevi, denetitilen akışlar için geçerli konumları değiştirmeye çalışır.|
|[seekpos](#seekpos)|Korumalı sanal üye işlevi, denetitilen akışlar için geçerli konumları değiştirmeye çalışır.|
|[setbuf](#setbuf)|Korumalı sanal üye işlevi, türetilen her akış arabelleği için özel bir işlem gerçekleştirir.|
|[Değiştir](#swap)|Sağlanan `basic_filebuf` parametrenin `basic_filebuf` içeriği için bunun içeriğini değiştirir.|
|[Eşitleme](#sync)|Korumalı, sanal işlev, denetlenen akışları ilişkili dış akışlarla eşitlemeye çalışır.|
|[uflow](../standard-library/basic-streambuf-class.md#uflow)|Geçerli öğeyi giriş akışından ayıklamak için korumalı, sanal işlev.|
|[akış altı](#underflow)|Geçerli öğeyi giriş akışından ayıklamak için korumalı, sanal işlev.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<fstream>

**Ad alanı:** std

## <a name="basic_filebufbasic_filebuf"></a><a name="basic_filebuf"></a>basic_filebuf:basic_filebuf

Türünde `basic_filebuf`bir nesne oluşturuyor.

```cpp
basic_filebuf();

basic_filebuf(basic_filebuf&& right);
```

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, giriş arabelleği ve çıktı arabelleği denetleyen tüm işaretçilerde bir null işaretçisi depolar. Ayrıca dosya işaretçisinde bir null işaretçisi de polar.

İkinci oluşturucu, nesneyi *hakkın*içeriğiyle başolarak ele alar, rvalue başvurusu olarak kabul edilir.

## <a name="basic_filebufchar_type"></a><a name="char_type"></a>basic_filebuf::char_type

Bir tür adını `Char_T` şablon parametresi ile ilişkilendirer.

```cpp
typedef Char_T char_type;
```

## <a name="basic_filebufclose"></a><a name="close"></a>basic_filebuf::kapat

Bir dosyayı kapatır.

```cpp
basic_filebuf<Char_T, Tr> *close();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi null işaretçisi ise üye işlev bir null işaretçisi döndürür.

### <a name="remarks"></a>Açıklamalar

`close`çağırır. `fclose(fp)` Bu işlev sıfır olmayan bir değer döndürürse, işlev null işaretçisi döndürür. Aksi takdirde, dosyanın başarıyla kapatıldığını belirtmek için **bu** döndürür.

Geniş bir akış için, akış açıldığından bu yana herhangi bir ekleme oluştuysa veya son çağrıdan sonra `streampos`, işlev çağırır. [`overflow`](#overflow) Ayrıca, gerektiğinde aramak `fac` `fac.unshift` için dosya dönüştürme falı kullanarak, ilk dönüştürme durumunu geri yüklemek için gereken herhangi bir sıra ekler. Tür **char'ın** her üretilen öğesi, `fp` `fputc(byte, fp)` `byte` formun art arda gelen çağrılarıyla dosya işaretçisi tarafından atanan ilişkili akışa yazılır. Çağrı `fac.unshift` veya herhangi bir yazma başarısız olursa, işlev başarılı olmaz.

### <a name="example"></a>Örnek

Aşağıdaki örnek geçerli dizinde iki dosya varsayar: *basic_filebuf_close.txt* (içerik "test") ve *iotest.txt* (içerik "ssss").

```cpp
// basic_filebuf_close.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main() {
   using namespace std;
   ifstream file;
   basic_ifstream <wchar_t> wfile;
   char c;
   // Open and close with a basic_filebuf
   file.rdbuf()->open( "basic_filebuf_close.txt", ios::in );
   file >> c;
   cout << c << endl;
   file.rdbuf( )->close( );

   // Open/close directly
   file.open( "iotest.txt" );
   file >> c;
   cout << c << endl;
   file.close( );

   // open a file with a wide character name
   wfile.open( L"iotest.txt" );

   // Open and close a nonexistent with a basic_filebuf
   file.rdbuf()->open( "ziotest.txt", ios::in );
   cout << file.fail() << endl;
   file.rdbuf( )->close( );

   // Open/close directly
   file.open( "ziotest.txt" );
   cout << file.fail() << endl;
   file.close( );
}
```

```Output
t
s
0
1
```

## <a name="basic_filebufint_type"></a><a name="int_type"></a>basic_filebuf:int_type

`basic_filebuf` Bu türü kapsamda, `Tr` kapsamdaki aynı adın türüne eşdeğer hale getirir.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="basic_filebufis_open"></a><a name="is_open"></a>basic_filebuf:is_open

Dosyanın açık olup olmadığını gösterir.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

dosya işaretçisi null değilse **doğru.**

### <a name="example"></a>Örnek

```cpp
// basic_filebuf_is_open.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main( )
{
   using namespace std;
   ifstream file;
   cout << boolalpha << file.rdbuf( )->is_open( ) << endl;

   file.open( "basic_filebuf_is_open.cpp" );
   cout << file.rdbuf( )->is_open( ) << endl;
}
```

```Output
false
true
```

## <a name="basic_filebufoff_type"></a><a name="off_type"></a>basic_filebuf:off_type

`basic_filebuf` Bu türü kapsamda, `Tr` kapsamdaki aynı adın türüne eşdeğer hale getirir.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="basic_filebufopen"></a><a name="open"></a>basic_filebuf::açık

Bir dosyayı açar.

```cpp
basic_filebuf<Char_T, Tr> *open(
    const char* filename,
    ios_base::openmode mode,
    int protection = (int)ios_base::_Openprot);

basic_filebuf<Char_T, Tr> *open(
    const char* filename,
    ios_base::openmode mode);

basic_filebuf<Char_T, Tr> *open(
    const wchar_t* filename,
    ios_base::openmode mode,
    int protection = (int)ios_base::_Openprot);

basic_filebuf<Char_T, Tr> *open(
    const wchar_t* filename,
    ios_base::openmode mode);
```

### <a name="parameters"></a>Parametreler

*Dosyaadı*\
Açılacak dosyanın adı.

*Modu*\
Bir de sayısallaştırmalar [`ios_base::openmode`](../standard-library/ios-base-class.md#openmode).

*Koruma*\
Varsayılan dosya açma koruması, [_fsopen'daki](../c-runtime-library/reference/fsopen-wfsopen.md) *_wfsopen'* daki dalga parametresine eşdeğerdir.

### <a name="return-value"></a>Dönüş Değeri

Arabellek zaten açıksa veya dosya işaretçisi null işaretçisiyse, işlev null işaretçisini döndürür. Aksi takdirde, **bu**döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlev, dosyayı ad *file*name [`fopen`](../c-runtime-library/reference/fopen-wfopen.md) `(filename, strmode)`ile açarak . `strmode``mode & ~(` [`ate`](../standard-library/ios-base-class.md#openmode) `|` [`binary`](../standard-library/ios-base-class.md#openmode)tarafından `)`belirlenir:

- `ios_base::in`olur `"r"` (okumak için varolan dosyayı açın).

- [ios_base::out](../standard-library/ios-base-class.md#fmtflags) `ios_base::out | ios_base::trunc` veya `"w"` olur (varolan dosyayı truncate veya yazmak için oluşturun).

- `ios_base::out | app`olur `"a"` (tüm yazıları ekolarak açmak için varolan dosyayı açın).

- `ios_base::in | ios_base::out`olur `"r+"` (okuma ve yazma için varolan dosyayı açın).

- `ios_base::in | ios_base::out | ios_base::trunc`olur `"w+"` (varolan dosyayı truncate veya okuma ve yazma için oluşturun).

- `ios_base::in | ios_base::out | ios_base::app`olur `"a+"` (okumak ve tüm yazıları eketmek için varolan dosyayı açın).

Sıfır değilse, işlev metin akışı `strmode` yerine ikili akışı açmak için ekler. `b` `mode & ios_base::binary` Daha sonra dosya işaretçisinde `fopen` `fp`döndürülen değeri depolar. `mode & ios_base::ate` Sıfır değilse ve dosya işaretçisi null işaretçi `fseek(fp, 0, SEEK_END)` değilse, işlev dosyanın sonundaki akışı konumlandırmayı çağırır. Bu konumlandırma işlemi başarısız olursa, [`close`](#close) `(fp)` işlev çağırır ve dosya işaretçisinde null işaretçisi depolar.

Dosya işaretçisi null işaretçisi değilse, işlev dosya `use_facet<codecvt<Char_T, char, traits_type::` [`state_type`](../standard-library/char-traits-struct.md#state_type) `> >(` [`getloc`](../standard-library/basic-streambuf-class.md#getloc) `)`dönüştürme yönünü belirler: , [alt akış](#underflow) ve [taşma](#overflow)tarafından kullanılmak üzere.

Dosya işaretçisi null işaretçisiyse, işlev null işaretçisini döndürür. Aksi takdirde, **bu**döndürür.

### <a name="example"></a>Örnek

Kullanan [`basic_filebuf::close`](#close) `open`bir örnek için bkz.

## <a name="basic_filebufoperator"></a><a name="op_eq"></a>basic_filebuf::operator=

Bu akış arabellek nesnesinin içeriğini atayın. Bu, bir kopyasını geride bırakmayan bir rvalue içeren bir taşıma atamasI.

```cpp
basic_filebuf& operator=(basic_filebuf&& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
[basic_filebuf](../standard-library/basic-filebuf-class.md) bir nesneye rvalue başvurusu.

### <a name="return-value"></a>Dönüş Değeri

*Bu' nun __iadesi.__

### <a name="remarks"></a>Açıklamalar

Üye işleç, nesnenin *içeriğini, rvalue*referansı olarak kabul edilen sağın içeriğini kullanarak değiştirir. Daha fazla bilgi için [Bkz. Rvalue başvuru bildirimcisi: &&. ](../cpp/rvalue-reference-declarator-amp-amp.md)

## <a name="basic_filebufoverflow"></a><a name="overflow"></a>basic_filebuf::taşma

Tam bir arabelleğe yeni bir karakter eklendiğinde çağrılır.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `traits_type::eof`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olamazsa, `traits_type::eof`döndürür. Aksi takdirde, `traits_type::` [`not_eof`](../standard-library/char-traits-struct.md#not_eof) `(_Meta)`döner.

### <a name="remarks"></a>Açıklamalar

Eğer `_Meta != traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof), korumalı sanal üye işlev `ch = traits_type::` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) `(_Meta)` çıktı arabelleği içine öğe eklemek için çalışır. Bunu çeşitli şekillerde yapabilirsiniz:

- Bir yazma konumu varsa, öğeyi yazma konumuna depolayabilir ve çıktı arabelleği için bir sonraki işaretçiyi artım.

- Çıktı arabelleği için yeni veya ek depolama alanı ayırarak yazma konumunu kullanılabilir hale getirebilir.

- Gerektiğinde aramak `ch` `fac` `fac.out` için dosya dönüştürme falı kullanarak, ardından çıktı arabelleği herhangi bir bekleyen çıktı dönüştürebilirsiniz. Tür *char'ın* her üretilen öğesi, `fp` `fputc(ch, fp)` `ch` formun art arda gelen çağrılarıyla dosya işaretçisi tarafından atanan ilişkili akışa yazılır. Herhangi bir dönüştürme veya yazma başarısız olursa, işlev başarılı olmaz.

## <a name="basic_filebufpbackfail"></a><a name="pbackfail"></a>basic_filebuf::pbackfail

Giriş akışına bir öğeyi geri koymaya çalışır, ardından geçerli öğeyi (bir sonraki işaretçitarafından işaret eder) yapar.

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `traits_type::eof`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olamazsa, `traits_type::eof`döndürür. Aksi takdirde, `traits_type::` [`not_eof`](../standard-library/char-traits-struct.md#not_eof) `(_Meta)`döner.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlev, bir öğeyi giriş arabelleğine geri koyar ve sonra onu geçerli öğe (bir sonraki işaretçitarafından işaret edilen) yapar. Eğer `_Meta == traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof), geri itmek için öğe etkili bir geçerli öğeönce akışı zaten biridir. Aksi takdirde, bu öğe `ch = traits_type::` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) `(_Meta)`nin yerine . İşlev çeşitli şekillerde bir öğegeri koyabilirsiniz:

- Bir `putback` konum varsa ve orada depolanan öğe ile `ch`karşılaştırıldığında, giriş arabelleği için bir sonraki işaretçiyi atabilir.

- İşlev bir `putback` konumu kullanılabilir hale getirebilirse, bunu yapabilir, bir sonraki işaretçiyi bu konumu işaret etmek için ayarlayabilir ve bu konumda depolayabilir. `ch`

- İşlev bir öğeyi giriş akışına geri itebiliyorsa, bunu, `ungetc` tür **char**öğesi için çağrıda bulunarak yapabilir.

## <a name="basic_filebufpos_type"></a><a name="pos_type"></a>basic_filebuf::pos_type

`basic_filebuf` Bu türü kapsamda, `Tr` kapsamdaki aynı adın türüne eşdeğer hale getirir.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="basic_filebufseekoff"></a><a name="seekoff"></a>basic_filebuf::seekoff

Denetlenmeye niçin geçerli konumları değiştirmeye çalışır.

```cpp
virtual pos_type seekoff(
    off_type _Off,
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

Yeni konumu veya geçersiz akış konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, denetitilen akışlar için geçerli konumları değiştirmeye çalışır. Sınıfın bir nesnesi [`basic_filebuf`](../standard-library/basic-filebuf-class.md) `<Char_T, Tr>`için, akış konumu, bir `fpos_t`ofset ve geniş bir akışı ayrışdırmak için gereken tüm durum bilgilerini depolayan bir tür nesnesi tarafından temsil edilebilir. Ofset sıfır, akışın ilk öğesini ifade eder. (Bir tür [`pos_type`](../standard-library/basic-streambuf-class.md#pos_type) nesnesi `fpos_t` en az bir nesneyi depolar.)

Hem okuma hem de yazma için açılan bir dosya için hem giriş hem de çıkış akışları birlikte konumlandırılır. Ekleme ve çıkarma arasında geçiş yapmak için, [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos)ya da aramanız gerekir . Aramalar `pubseekoff` `seekoff`(ve dolayısıyla) [metin akışları,](../c-runtime-library/text-and-binary-streams.md)ikili [akışları](../c-runtime-library/text-and-binary-streams.md)ve geniş akışları için çeşitli [sınırlamalar](../c-runtime-library/byte-and-wide-streams.md)var.

Dosya işaretçisi null işaretçisiise, `fp` işlev başarısız olur. Aksi takdirde, çağırarak `fseek(fp, _Off, _Way)`akış konumunu değiştirmeye çalışır. Bu işlev başarılı olursa ve `fposn` ortaya çıkan konum `fgetpos(fp, &fposn)`çağrılar alınarak belirlenebilirse, işlev başarılı olur. İşlev başarılı olursa, içeren bir `pos_type` tür `fposn`değeri döndürür. Aksi takdirde, geçersiz bir akış konumu döndürür.

## <a name="basic_filebufseekpos"></a><a name="seekpos"></a>basic_filebuf::seekpos

Denetlenmeye niçin geçerli konumları değiştirmeye çalışır.

```cpp
virtual pos_type seekpos(
    pos_type _Sp,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*\
Aranacak pozisyon.

*_Which*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi null işaretçisiise, `fp` işlev başarısız olur. Aksi takdirde, akarsu konumunu çağırarak `fsetpos(fp, &fposn)`değiştirmeye `fposn` çalışır `fpos_t` , nerede `pos`nesne depolanır . Bu işlev başarılı olursa, `pos`işlev döndürür. Aksi takdirde, geçersiz bir akış konumu döndürür. Akış konumunun geçersiz olup olmadığını belirlemek için, `pos_type(off_type(-1))`iade değerini .

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, denetitilen akışlar için geçerli konumları değiştirmeye çalışır. Sınıfın bir nesnesi [`basic_filebuf`](../standard-library/basic-filebuf-class.md) `<Char_T, Tr>`için, akış konumu, bir `fpos_t`ofset ve geniş bir akışı ayrışdırmak için gereken tüm durum bilgilerini depolayan bir tür nesnesi tarafından temsil edilebilir. Ofset sıfır, akışın ilk öğesini ifade eder. (Bir tür `pos_type` nesnesi `fpos_t` en az bir nesneyi depolar.)

Hem okuma hem de yazma için açılan bir dosya için hem giriş hem de çıkış akışları birlikte konumlandırılır. Ekleme ve çıkarma arasında geçiş yapmak için, [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos)ya da aramanız gerekir . Aramaların `pubseekoff` (ve) `seekoff`metin akışları, ikili akışlar ve geniş akışlar için çeşitli sınırlamaları vardır.

Geniş bir akış için, akış açıldığından bu yana herhangi bir ekleme oluştuysa veya son çağrıdan sonra `streampos`işlev [taşması](#overflow)çağırır. Ayrıca, gerektiğinde aramak `fac` `fac.unshift` için dosya dönüştürme falı kullanarak, ilk dönüştürme durumunu geri yüklemek için gereken herhangi bir sıra ekler. Tür **char'ın** her üretilen öğesi, `fp` `fputc(byte, fp)` `byte` formun art arda gelen çağrılarıyla dosya işaretçisi tarafından atanan ilişkili akışa yazılır. Çağrı `fac.unshift` veya herhangi bir yazma başarısız olursa, işlev başarılı olmaz.

## <a name="basic_filebufsetbuf"></a><a name="setbuf"></a>basic_filebuf::setbuf

Türetilen her akış arabelleği için özel bir işlem gerçekleştirir.

```cpp
virtual basic_streambuf<Char_T, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*_Buffer*\
Arabellek için işaretçi.

*Sayısı*\
Arabelleğe boyutu.

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi null işaretçisi `fp` ise korumalı üye işlevi sıfır döndürür.

### <a name="remarks"></a>Açıklamalar

`setbuf`akış `setvbuf( fp, (char*) _Buffer, _IOFBF, count * sizeof( Char_T))` için bir `count` arabellek olarak *_Buffer* başlayan öğelerin dizi sunmak için çağırır. Bu işlev sıfır olmayan bir değer döndürürse, işlev null işaretçisi döndürür. Aksi takdirde, **bu** sinyal başarı döndürür.

## <a name="basic_filebufswap"></a><a name="swap"></a>basic_filebuf::takas

Verilen `basic_filebuf`içeriği için `basic_filebuf` bu içeriğini değiştirir.

```cpp
void swap(basic_filebuf& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bir diğerine `basic_filebuf`bir lvalue başvurusu .

## <a name="basic_filebufsync"></a><a name="sync"></a>basic_filebuf::senkronize

Denetlenen akışları ilişkili dış akışlarla eşitlemeye çalışır.

```cpp
virtual int sync();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi `fp` null işaretçisiyse sıfır döndürür. Aksi takdirde, yalnızca hem [taşmaya](#overflow) çağrılması hem de bekleyen çıktıyı akışa yıkamayı `fflush(fp)` başarırsa sıfır döndürür.

## <a name="basic_filebuftraits_type"></a><a name="traits_type"></a>basic_filebuf:traits_type

Bir tür adını `Tr` şablon parametresi ile ilişkilendirer.

```cpp
typedef Tr traits_type;
```

## <a name="basic_filebufunderflow"></a><a name="underflow"></a>basic_filebuf::underflow

Giriş akışından geçerli öğeyi ayıklar.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olamazsa, `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof)döndürür. Aksi takdirde, `ch`Açıklamalar bölümünde açıklandığı gibi dönüştürülür, döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlev, giriş `ch` akışından geçerli öğeyi ayıklamaya `traits_type::` [`to_int_type`](../standard-library/char-traits-struct.md#to_int_type) `(ch)`ve öğeyi . Bunu çeşitli şekillerde yapabilirsiniz:

- Okuma konumu varsa, okuma `ch` konumunda depolanan öğe olarak alır ve giriş arabelleği için bir sonraki işaretçiyi ilerler.

- Bu tür **char**bir veya daha fazla öğeyi okuyabilir `fgetc(fp)`, formun ardışık `ch` aramaları `Char_T` sanki , ve `fac` gerektiğinde `fac.in` aramak için dosya dönüştürme falı kullanarak tür bir öğeye dönüştürmek. Herhangi bir okuma veya dönüştürme başarısız olursa, işlev başarılı olmaz.

## <a name="see-also"></a>Ayrıca bkz.

[\<fstream>](../standard-library/fstream.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
