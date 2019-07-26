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
ms.openlocfilehash: ae72523c5c0a769a0267da94fead5ea29664276e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459478"
---
# <a name="basicfilebuf-class"></a>basic_filebuf Sınıfı

Karakter nitelikleri, bir dış dosyada depolanan öğelerin dizisine ve sonuna kadar olan *Eled*türünde öğelerin aktarımını denetleyen bir akış arabelleğini açıklar .

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_filebuf : public basic_streambuf<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Elem*\
Dosya arabelleğinin temel öğesi.

*Tr*\
Dosya arabelleğinin temel öğesinin nitelikleri (genellikle `char_traits` <  `Elem`>).

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir dış dosyada depolanan öğelerin dizisine ve sonuna karakter nitelikleri belirlenmiş olan *Eled*türünde öğelerin aktarımını denetleyen bir akış arabelleğini tanımlar.

> [!NOTE]
> Türündeki nesneler, *eled*tür parametresi tarafından `char_type` belirtilenden bağımsız olarak `char *` türü bir iç arabellekle oluşturulur. `basic_filebuf` Bu, bir Unicode dizesinin ( **wchar_t** karakter içeren), iç arabelleğe yazılmadan önce bir ANSI dizesine ( **char** karakterleri içeren) dönüştürülemeyeceği anlamına gelir. Arabellekte Unicode dizeleri depolamak için **wchar_t** türünde yeni bir arabellek oluşturun ve [basic_streambuf::p](../standard-library/basic-streambuf-class.md#pubsetbuf) `()` ubsetbuffer metodunu kullanarak ayarlayın. Bu davranışı gösteren bir örnek görmek için aşağıya bakın.

Sınıfının `basic_filebuf` <  `FILE` bir nesnesi ,`Tr`bir açık dosyayla ilişkili akışı denetleyen nesneyi atayan bir dosya işaretçisini >. `Elem` Ayrıca, korumalı üye işlevleri [taşması](#overflow) ve [yetersiz kalması](#underflow)tarafından kullanılmak üzere iki dosya dönüştürme modellerinin işaretçilerini depolar. Daha fazla bilgi için bkz. [basic_filebuf:: Open](#open).

## <a name="example"></a>Örnek

Aşağıdaki örnek, `basic_filebuf<wchar_t>` `pubsetbuf()` yöntemini çağırarak bir nesne türünün, iç arabellekte Unicode karakterleri nasıl depolayabileceğinizi göstermektedir.

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
|[basic_filebuf](#basic_filebuf)|Türünde `basic_filebuf`bir nesne oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir tür adını `Elem` şablon parametresiyle ilişkilendirir.|
|[int_type](#int_type)|Bu türün `basic_filebuf`kapsamını `Tr` kapsamdaki aynı adın türüne eşit hale getirir.|
|[off_type](#off_type)|Bu türün `basic_filebuf`kapsamını `Tr` kapsamdaki aynı adın türüne eşit hale getirir.|
|[pos_type](#pos_type)|Bu türün `basic_filebuf`kapsamını `Tr` kapsamdaki aynı adın türüne eşit hale getirir.|
|[traits_type](#traits_type)|Bir tür adını `Tr` şablon parametresiyle ilişkilendirir.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[close](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Bir dosyanın açık olup olmadığını gösterir.|
|[open](#open)|Bir dosya açar.|
|[taşma](#overflow)|Tam arabelleğe yeni bir karakter eklendiğinde çağrılabilen, korunan bir sanal işlev.|
|[pbackfail](#pbackfail)|Korumalı sanal üye işlevi, giriş akışına bir öğe geri döndürmeye çalışır ve sonra geçerli öğe (sonraki işaretçinin gösterdiği) yapar.|
|[seekoff](#seekoff)|Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışır.|
|[seekpos](#seekpos)|Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışır.|
|[setbuf](#setbuf)|Korumalı sanal üye işlevi, her türetilmiş akış arabelleği için bir işlem gerçekleştirir.|
|[Kur](#swap)|Bunun `basic_filebuf` içeriğini, belirtilen `basic_filebuf` parametrenin içeriği için değiş tokuş eder.|
|[Eşitleme](#sync)|Korumalı, sanal işlev denetimli akışları ilişkili dış akışlarla eşitlemeye çalışır.|
|[uflow](../standard-library/basic-streambuf-class.md#uflow)|Geçerli öğeyi giriş akışından ayıklamak için korumalı, sanal işlev.|
|[öğe](#underflow)|Geçerli öğeyi giriş akışından ayıklamak için korumalı, sanal işlev.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<fstream >

**Ad alanı:** std

## <a name="basic_filebuf"></a>basic_filebuf::basic_filebuf

Türünde `basic_filebuf`bir nesne oluşturur.

```cpp
basic_filebuf();

basic_filebuf(basic_filebuf&& right);
```

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, giriş arabelleğini ve çıkış arabelleğini denetleyen tüm işaretçilerde boş bir işaretçi depolar. Ayrıca dosya işaretçisine bir null işaretçi depolar.

İkinci Oluşturucu, nesnesini, bir rvalue başvurusu olarak kabul `right`edilen içeriğiyle başlatır.

## <a name="char_type"></a>basic_filebuf::char_type

Bir tür adını `Elem` şablon parametresiyle ilişkilendirir.

```cpp
typedef Elem char_type;
```

## <a name="close"></a>basic_filebuf:: Close

Bir dosyayı kapatır.

```cpp
basic_filebuf<Elem, Tr> *close();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi null işaretçisiyse üye işlevi null bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

`close`çağrılar `fclose`( **FP**). Bu işlev sıfır dışında bir değer döndürürse, işlev null bir işaretçi döndürür. Aksi takdirde, dosyanın başarıyla kapatıldığını göstermek için **bunu** döndürür.

Geniş bir akış için, akışın açıldığı veya son çağrısından `streampos`bu yana herhangi bir ekleme gerçekleştiyse, işlev [taşma](#overflow)işlevini çağırır. Ayrıca, gerektiğinde çağırmak `fac` `fac.unshift` için dosya dönüştürme modeli kullanılarak, ilk dönüştürme durumunu geri yüklemek için gereken herhangi bir diziyi de ekler. Bu nedenle `byte` oluşturulan **char** türündeki her öğe `fp` , dosya işaretçisi `fputc`tarafından belirlenen ilişkili akışa yazılır ( **byte**, **FP**). `fac.unshift` Veya yazma çağrısı başarısız olursa, işlev başarılı olmaz.

### <a name="example"></a>Örnek

Aşağıdaki örnek Şu anki dizindeki iki dosyayı varsayar: basic_filebuf_close. txt (içerikler "test") ve IOTest. txt (içerik "ssss").

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

## <a name="int_type"></a>basic_filebuf::int_type

Bu türü, basic_filebuf's Scope içinde, `Tr` kapsamdaki aynı ada sahip türe eşit hale getirir.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="is_open"></a>basic_filebuf::is_open

Bir dosyanın açık olup olmadığını gösterir.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi boş bir işaretçi değilse **true** .

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

## <a name="off_type"></a>basic_filebuf::off_type

Bu türü, basic_filebuf's Scope içinde, `Tr` kapsamdaki aynı ada sahip türe eşit hale getirir.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="open"></a>basic_filebuf:: Open

Bir dosya açar.

```cpp
basic_filebuf<Elem, Tr> *open(
    const char* _Filename,
    ios_base::openmode _Mode,
    int _Prot = (int)ios_base::_Openprot);

basic_filebuf<Elem, Tr> *open(
    const char* _Filename,
    ios_base::openmode _Mode);

basic_filebuf<Elem, Tr> *open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode,
    int _Prot = (int)ios_base::_Openprot);

basic_filebuf<Elem, Tr> *open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode);
```

### <a name="parameters"></a>Parametreler

*_Dosya adı*\
Açılacak dosyanın adı.

*_Mod*\
[İos_base:: OpenMode](../standard-library/ios-base-class.md#openmode)içindeki Numaralandırmalardan biri.

*_Prot*\
Varsayılan dosya açma koruması, [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)içindeki *shflag* parametresine eşdeğerdir.

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi null işaretçisiyse, işlev null bir işaretçi döndürür. Aksi takdirde, bunu **döndürür.**

### <a name="remarks"></a>Açıklamalar

Üye işlevi, [fopen](../c-runtime-library/reference/fopen-wfopen.md)( *dosya adı*, **strmode**) öğesini çağırarak dosya adı *filename*ile dosyasını açar. `strmode`**moddan &** [~ (&](../standard-library/ios-base-class.md#openmode) &#124; [ikiliden](../standard-library/ios-base-class.md#openmode)) belirlenir:

- `ios_base::in` **"r"** olur (mevcut dosyayı okumak için açın).

- [ios_base:: Out](../standard-library/ios-base-class.md#fmtflags) veya **ios_base:: Out &#124; ios_base:: trunc** **"w"** olur (var olan dosyayı keser veya yazma için Oluştur).

- **ios_base:: Out &#124; uygulaması** **"a"** (tüm yazmaları eklemek için var olan dosyayı aç) olur.

- **ios_base:: &#124; ios_base:: Out** **"r +"** olur (mevcut dosyayı okumak ve yazmak için açın).

- **ios_base:: &#124; ios_base:: &#124; Out ios_base:: trunc** **"w +"** olur (var olan dosyayı keser veya okuma ve yazma için oluşturun).

- **ios_base:: ios_base &#124; :: &#124; Out ios_base:: App,** **"a +"** (okuma için mevcut dosyayı aç ve tüm yazmaları eklemek için aç) olur.

**Mode & ios_base:: binary** değeri sıfır değilse, işlevi metin akışı `b` yerine `strmode` bir ikili akış açmak için öğesine ekler. Daha sonra dosya işaretçisine `fopen` `fp`tarafından döndürülen değeri depolar. **Mode & ios_base:: ate** değeri sıfır değilse ve dosya işaretçisi boş bir işaretçi değilse, işlev dosyanın sonuna kadar olan `fseek`akışı konumlandırmak için ( **FP**, 0, `SEEK_END`) çağırır. Bu konumlandırma işlemi başarısız olursa, işlev [Close](#close)( `fp`) öğesini çağırır ve dosya işaretçisine bir null işaretçi depolar.

Dosya işaretçisi boş bir işaretçi değilse, işlev dosya dönüştürme modeli ' ni belirler: `use_facet`< `codecvt`< **Eled**, `char`, **traits_type::** [state_type](../standard-library/char-traits-struct.md#state_type)> > ( [getloc](../standard-library/basic-streambuf-class.md#getloc)), [yetersiz](#underflow) ve [taşma](#overflow)tarafından kullanılmak üzere.

Dosya işaretçisi null işaretçisiyse, işlev null bir işaretçi döndürür. Aksi takdirde, bunu **döndürür.**

### <a name="example"></a>Örnek

Tarafından kullanılan `open`bir örnek için bkz. [basic_filebuf:: Close](#close) .

## <a name="op_eq"></a>basic_filebuf:: operator =

Bu akış arabelleği nesnesinin içeriğini atayın. Bu, arkasına kopya bırakmayan bir rvalue içeren bir taşıma atamasıdır.

```cpp
basic_filebuf& operator=(basic_filebuf&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir [basic_filebuf](../standard-library/basic-filebuf-class.md) nesnesine rvalue başvurusu.

### <a name="return-value"></a>Dönüş Değeri

\* This döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işleci, bir rvalue başvurusu olarak kabul edilen, *sağ*içeriğini kullanarak nesnesinin içeriğini değiştirir. Daha fazla bilgi için bkz. [rvalue başvuru bildirimci: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="overflow"></a>basic_filebuf:: overflow

Tam arabelleğe yeni bir karakter eklendiğinde çağırılır.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `traits_type::eof`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olmazsa, döndürür `traits_type::eof`. Aksi takdirde, **traits_type::** [Not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *meta*) döndürür.

### <a name="remarks"></a>Açıklamalar

*_Meta* **! = traits_type::** [EOF](../standard-library/char-traits-struct.md#eof)ise, korumalı sanal üye işlevi endeavors **= traits_type::** [to_char_type](../standard-library/char-traits-struct.md#to_char_type)( *_Meta*) öğesini çıkış arabelleğine eklemek için. Bunu çeşitli yollarla yapabilirsiniz:

- Bir yazma konumu varsa, öğeyi yazma konumuna kaydedebilir ve çıkış arabelleği için sonraki işaretçiyi artırabilirsiniz.

- Çıktı arabelleği için yeni veya ek depolama alanı ayırarak bir yazma konumu kullanılabilir hale getirir.

- Gerekli olduğu gibi çağırmak `ch` `fac.out` için dosya dönüştürme modeli `fac` ' ni kullanarak çıkış arabelleğindeki bekleyen çıktıyı dönüştürebilir. Bu nedenle `ch` oluşturulan *char* türündeki her öğe `fp` , dosya işaretçisi `fputc`tarafından belirlenen ilişkili akışa yazılır ( **ch**, **FP**). Herhangi bir dönüştürme veya yazma işlemi başarısız olursa, işlev başarılı olmaz.

## <a name="pbackfail"></a>basic_filebuf::p backfail

Giriş akışına bir öğe geri döndürmeye çalışır, sonra bunu geçerli öğe yapar (sonraki işaretçinin gösterdiği).

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `traits_type::eof`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olmazsa, döndürür `traits_type::eof`. Aksi takdirde, **traits_type::** [not_eof](../standard-library/char-traits-struct.md#not_eof)( *\_meta*) döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, giriş arabelleğine bir öğe koyar ve sonra bunu geçerli öğe yapar (sonraki işaretçi tarafından işaret edilen). Eğer  *\_meta* **= = traits_type::** [EOF](../standard-library/char-traits-struct.md#eof)ise, geri gönderme öğesi geçerli öğeden önceki akışta etkin bir şekilde olur. Aksi takdirde, bu öğe **ch = traits_type::** [to_char_type](../standard-library/char-traits-struct.md#to_char_type)( *\_meta*) ile değiştirilmiştir. İşlevi bir öğeyi çeşitli yollarla geri alabilir:

- Bir Putback konumu varsa ve şuna eşit olarak `ch`karşılaştırıldığı öğe, giriş arabelleği için bir sonraki işaretçiyi azaledebilir.

- İşlev bir `putback` konum kullanılabilir hale getirmek için bu işlemi yapabilir, sonraki işaretçiyi o konuma işaret etmek için ayarlayabilir ve bu konumda saklayın `ch` .

- İşlev, giriş akışına bir öğe geri gönderebiliyorsanız, örneğin `ungetc` **char**türünde bir öğe çağırarak, bunu yapabilirsiniz.

## <a name="pos_type"></a>basic_filebuf::p os_type

Bu türü, basic_filebuf's Scope içinde, `Tr` kapsamdaki aynı ada sahip türe eşit hale getirir.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="seekoff"></a>basic_filebuf:: seekoff

Denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışır.

```cpp
virtual pos_type seekoff(off_type _Off,
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

Yeni konumu veya geçersiz akış konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları endeavors. >`Tr` [Basic_filebuf](../standard-library/basic-filebuf-class.md)< sınıfının bir nesnesi için, bir akış konumu türü `fpos_t`bir nesne ile temsil edilebilir, bu da bir sapmayı ve geniş bir akışı ayrıştırmak için gereken durum bilgilerini depolar.`Elem` Sıfır değeri akışın ilk öğesini belirler. ( [Pos_type](../standard-library/basic-streambuf-class.md#pos_type) türündeki bir nesne en az bir `fpos_t` nesnesi depolar.)

Hem okuma hem de yazma için açılmış bir dosya için hem giriş hem de çıkış akışları birlikte konumlandırılır. Ekleme ve ayıklama arasında geçiş yapmak için, [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) veya [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)' ya çağrı yapmanız gerekir. [](../c-runtime-library/byte-and-wide-streams.md) [](../c-runtime-library/text-and-binary-streams.md) [](../c-runtime-library/text-and-binary-streams.md)(Ve bu nedenle) çağrılarının, metin akışları, ikili akışlar ve geniş akışlar için çeşitli sınırlamaları vardır. `seekoff` `pubseekoff`

Dosya işaretçisi `fp` null işaretçisiyse, işlev başarısız olur. Aksi `fseek`takdirde, ( **FP**, `_Off`, `_Way`) öğesini çağırarak akış konumunu değiştirmek için endeavors. Bu işlev başarılı olursa ve sonuçta elde edilen `fposn` konum ( **FP**, **& fposn**) çağrısı `fgetpos`yaparak belirlenebilir, işlev başarılı olur. İşlev başarılı olursa, içeren `pos_type` `fposn`türünde bir değer döndürür. Aksi takdirde, geçersiz bir akış konumu döndürür.

## <a name="seekpos"></a>basic_filebuf:: seekpos

Denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışır.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*\
Arama yapılacak konum.

*_Hangisi*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin verir.

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi `fp` null işaretçisiyse, işlev başarısız olur. Aksi takdirde, ( **FP**, **& fposn**) `fsetpos`öğesini çağırarak akış konumunu değiştirmek için endeavors, `pos`burada `fposn` `fpos_t` depolanan nesnedir. Bu işlev başarılı olursa, işlev döndürür `pos`. Aksi takdirde, geçersiz bir akış konumu döndürür. Akış konumunun geçersiz olup olmadığını anlamak için dönüş değerini ile `pos_type(off_type(-1))`karşılaştırın.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları endeavors. `fpos_t` [Basic_filebuf](../standard-library/basic-filebuf-class.md) \< **eled**, **tr**> sınıfının bir nesnesi için, bir akış konumu türü bir nesne ile temsil edilebilir, bu da geniş bir akışı ayrıştırmak için gereken bir sapmayı ve herhangi bir durum bilgisini depolar. Sıfır değeri akışın ilk öğesini belirler. (Türünde `pos_type` bir nesne en az bir `fpos_t` nesneyi depolar.)

Hem okuma hem de yazma için açılmış bir dosya için hem giriş hem de çıkış akışları birlikte konumlandırılır. Ekleme ve ayıklama arasında geçiş yapmak için, [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) veya [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)' ya çağrı yapmanız gerekir. (Ve bu nedenle) çağrılarının, metin akışları, ikili akışlar ve geniş akışlar için çeşitli sınırlamaları vardır. `seekoff` `pubseekoff`

Geniş bir akış için, akışın açıldığı veya son çağrısından `streampos`bu yana herhangi bir ekleme gerçekleştiyse, işlev [taşma](#overflow)işlevini çağırır. Ayrıca, gerektiğinde `fac` **fac** `.unshift` çağırmak için dosya dönüştürme modeli kullanılarak, ilk dönüştürme durumunu geri yüklemek için gereken herhangi bir diziyi de ekler. Bu nedenle `byte` oluşturulan **char** türündeki her öğe `fp` , dosya işaretçisi `fputc`tarafından belirlenen ilişkili akışa yazılır ( **byte**, **FP**). `fac.unshift` Veya yazma çağrısı başarısız olursa, işlev başarılı olmaz.

## <a name="setbuf"></a>basic_filebuf:: setarabelleğe

Her türetilmiş akış arabelleği için özel bir işlem gerçekleştirir.

```cpp
virtual basic_streambuf<Elem, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*_Arabellek*\
Arabellek işaretçisi.

*biriktirme*\
Arabelleğin boyutu.

### <a name="return-value"></a>Dönüş Değeri

Korumalı üye işlevi, dosya işaretçisi `fp` null işaretçisiyse sıfır döndürür.

### <a name="remarks"></a>Açıklamalar

`setbuf`_ `setvbuf` `_IOFBF` `count` `_Buffer` `char` \* \* ilebaşlayan`sizeof`  öğe`count` dizisini sunmak için (FP, (),, ( **eled**)) çağırır Akış için arabellek olarak arabellek. Bu işlev sıfır dışında bir değer döndürürse, işlev null bir işaretçi döndürür. Aksi takdirde, bunu başarılı olarak **bildirmek için döndürür** .

## <a name="swap"></a>basic_filebuf:: swap

Bunun `basic_filebuf` içeriğini, belirtilen `basic_filebuf`içeriği için değiş tokuş eder.

```cpp
void swap(basic_filebuf& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`lvalue` Başka`basic_filebuf`bir başvuru.

## <a name="sync"></a>basic_filebuf:: Sync

Denetlenen akışları ilişkili dış akışlarla eşitlemeye çalışır.

```cpp
virtual int sync();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi `fp` null işaretçisiyse sıfır döndürür. Aksi takdirde, akış için bekleyen çıktıyı reçeteye göre yalnızca [taşmaya](#overflow) ve `fflush`( **FP**) çağrıları başarılı olursa sıfır döndürür.

## <a name="traits_type"></a>basic_filebuf::traits_type

Bir tür adını `Tr` şablon parametresiyle ilişkilendirir.

```cpp
typedef Tr traits_type;
```

## <a name="underflow"></a>basic_filebuf:: yetersiz

Giriş akışından geçerli öğeyi ayıklar.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olmazsa, **traits_type::** [EOF](../standard-library/char-traits-struct.md#eof)döndürür. Aksi takdirde, açıklamalar `ch`bölümünde açıklandığı gibi dönüştürülmüş döndürülür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, giriş `ch` akışından geçerli öğeyi ayıklamak için endeavors ve öğeyi **traits_type::** [to_int_type](../standard-library/char-traits-struct.md#to_int_type)(`ch`) olarak döndürür. Bunu çeşitli yollarla yapabilirsiniz:

- Bir okuma konumu varsa, okuma konumunda depolanan öğesi `ch` olarak alır ve giriş arabelleği için sonraki işaretçiyi ilerletir.

- **Karakter**türünde bir veya daha fazla öğeyi bir veya daha fazla şekilde okuyabilir. Bu, formun `fgetc`art arda çağrılarında (**FP**) gibi bir veya daha fazla öğeyi okuyabilir ve bunu `Elem` gerektiğinde çağırmak `fac.in` için dosya dönüştürme modeli fac kullanarak bunları türünde **bir öğeye dönüştürebilir** . Herhangi bir okuma veya dönüştürme başarısız olursa, işlev başarılı olmaz.

## <a name="see-also"></a>Ayrıca bkz.

[\<fstream >](../standard-library/fstream.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
