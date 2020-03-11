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
ms.openlocfilehash: 16d485320eb3970bd5c1e4a7a7fabb0602149e6f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856587"
---
# <a name="basic_filebuf-class"></a>basic_filebuf Sınıfı

Karakter *nitelikleri, bir*dış dosyada depolanan öğelerin dizisine ve sonuna kadar olan *Char_T*türündeki öğelerin aktarımını denetleyen bir akış arabelleğini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Char_T, class Tr = char_traits<Char_T>>
class basic_filebuf : public basic_streambuf<Char_T, Tr>
```

### <a name="parameters"></a>Parametreler

*Char_T*\
Dosya arabelleğinin temel öğesi.

*Tr*\
Dosya arabelleğinin temel öğesinin nitelikleri (genellikle `char_traits<Char_T>`).

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, *Char_T*türünde öğelerin aktarımını denetleyen bir akış arabelleği tanımlar. Bu, karakter nitelikleri, bir dış dosyada depolanan öğelerin dizisine ve sonuna *kadar, karakter*nitelikleri belirler.

> [!NOTE]
> `basic_filebuf` türündeki nesneler, *Char_T*tür parametresi tarafından belirtilen `char_type` ne olursa olsun, Char türünde bir iç arabellekle oluşturulur __\*__ . Bu, bir Unicode dizesinin ( **wchar_t** karakter içeren), iç arabelleğe yazılmadan önce bir ANSI dizesine ( **char** karakterleri içeren) dönüştürülemeyeceği anlamına gelir. Arabellekte Unicode dizeleri depolamak için **wchar_t** türünde yeni bir arabellek oluşturun ve [`basic_streambuf::pubsetbuf`](../standard-library/basic-streambuf-class.md#pubsetbuf)`()` yöntemini kullanarak ayarlayın. Bu davranışı gösteren bir örnek görmek için aşağıya bakın.

`basic_filebuf<Char_T, Tr>` sınıfının bir nesnesi, bir açık dosyayla ilişkili akışı denetleyen `FILE` nesnesini atayan bir dosya işaretçisini depolar. Ayrıca, korumalı üye işlevleri [taşması](#overflow) ve [yetersiz kalması](#underflow)tarafından kullanılmak üzere iki dosya dönüştürme modellerinin işaretçilerini depolar. Daha fazla bilgi için bkz. [`basic_filebuf::open`](#open).

## <a name="example"></a>Örnek

Aşağıdaki örnek, `pubsetbuf()` yöntemini çağırarak `basic_filebuf<wchar_t>` türünde bir nesnenin, iç arabellekte Unicode karakterleri depolamasını nasıl zorlanacağını gösterir.

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
|[basic_filebuf](#basic_filebuf)|`basic_filebuf`türünde bir nesne oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir tür adını `Char_T` şablon parametresiyle ilişkilendirir.|
|[int_type](#int_type)|Bu türün `basic_filebuf`kapsam içinde `Tr` kapsamındaki aynı ada sahip olan türüne eşit olmasını sağlar.|
|[off_type](#off_type)|Bu türün `basic_filebuf`kapsam içinde `Tr` kapsamındaki aynı ada sahip olan türüne eşit olmasını sağlar.|
|[pos_type](#pos_type)|Bu türün `basic_filebuf`kapsam içinde `Tr` kapsamındaki aynı ada sahip olan türüne eşit olmasını sağlar.|
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
|[Kur](#swap)|Bu `basic_filebuf` içeriği, belirtilen `basic_filebuf` parametresinin içeriği için değiş tokuş eder.|
|[Eşitleme](#sync)|Korumalı, sanal işlev denetimli akışları ilişkili dış akışlarla eşitlemeye çalışır.|
|[uflow](../standard-library/basic-streambuf-class.md#uflow)|Geçerli öğeyi giriş akışından ayıklamak için korumalı, sanal işlev.|
|[öğe](#underflow)|Geçerli öğeyi giriş akışından ayıklamak için korumalı, sanal işlev.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<fstream >

**Ad alanı:** std

## <a name="basic_filebuf"></a>basic_filebuf:: basic_filebuf

`basic_filebuf`türünde bir nesne oluşturur.

```cpp
basic_filebuf();

basic_filebuf(basic_filebuf&& right);
```

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, giriş arabelleğini ve çıkış arabelleğini denetleyen tüm işaretçilerde boş bir işaretçi depolar. Ayrıca dosya işaretçisine bir null işaretçi depolar.

İkinci Oluşturucu, nesneyi *sağ*içeriğiyle başlatır ve rvalue başvurusu olarak kabul edilir.

## <a name="char_type"></a>basic_filebuf:: char_type

Bir tür adını `Char_T` şablon parametresiyle ilişkilendirir.

```cpp
typedef Char_T char_type;
```

## <a name="close"></a>basic_filebuf:: Close

Bir dosyayı kapatır.

```cpp
basic_filebuf<Char_T, Tr> *close();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi null işaretçisiyse üye işlevi null bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

`close` `fclose(fp)`çağırır. Bu işlev sıfır dışında bir değer döndürürse, işlev null bir işaretçi döndürür. Aksi takdirde, dosyanın başarıyla kapatıldığını göstermek için **bunu** döndürür.

Geniş bir akış için, akışın açıldığı veya son `streampos`çağrısından bu yana herhangi bir ekleme gerçekleştiyse, işlev [`overflow`](#overflow)çağırır. Ayrıca, gerektiğinde `fac.unshift` çağırmak için `fac` dosya dönüştürme modeli kullanarak, ilk dönüştürme durumunu geri yüklemek için gereken herhangi bir diziyi de ekler. **Char** türünde oluşturulan her öğe `byte`, dosya işaretçisi tarafından belirtilen ilişkili akışa yazılır ve bu form `fputc(byte, fp)`art arda çağrılar olarak `fp`. `fac.unshift` çağrısı veya herhangi bir yazma işlemi başarısız olursa, işlev başarılı olmaz.

### <a name="example"></a>Örnek

Aşağıdaki örnek Şu anki dizindeki iki dosyayı varsayar: *basic_filebuf_close. txt* (içerik "test") ve *IOTest. txt* (içerik "ssss").

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

## <a name="int_type"></a>basic_filebuf:: int_type

Bu türü `basic_filebuf` kapsam içinde `Tr` kapsamındaki aynı ada sahip olan türe eşit hale getirir.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="is_open"></a>basic_filebuf:: is_open

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

## <a name="off_type"></a>basic_filebuf:: off_type

Bu türü `basic_filebuf` kapsam içinde `Tr` kapsamındaki aynı ada sahip olan türe eşit hale getirir.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="open"></a>basic_filebuf:: Open

Bir dosya açar.

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

*dosya adı*\
Açılacak dosyanın adı.

*mod*\
[`ios_base::openmode`](../standard-library/ios-base-class.md#openmode)Numaralandırmalardan biri.

*koruma*\
Varsayılan dosya açma koruması, [_fsopen _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md) *shflag* parametresine eşdeğerdir.

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi null işaretçisiyse, işlev null bir işaretçi döndürür. Aksi takdirde, bunu **döndürür.**

### <a name="remarks"></a>Açıklamalar

Üye işlevi, [`fopen`](../c-runtime-library/reference/fopen-wfopen.md)`(filename, strmode)`çağırarak dosyayı dosya *adı ile*açar. `strmode` `mode & ~(`[`ate`](../standard-library/ios-base-class.md#openmode)` | `[`binary`](../standard-library/ios-base-class.md#openmode)`)`belirlenir:

- `ios_base::in` `"r"` olur (mevcut dosyayı okumak için açın).

- [ios_base:: Out](../standard-library/ios-base-class.md#fmtflags) veya `ios_base::out | ios_base::trunc` `"w"` hale gelir (var olan dosyayı keser veya yazma için oluşturma).

- `ios_base::out | app` `"a"` hale gelir (tüm yazmaları eklemek için var olan dosyayı aç).

- `ios_base::in | ios_base::out` `"r+"` olur (mevcut dosyayı okumak ve yazmak için açın).

- `ios_base::in | ios_base::out | ios_base::trunc` `"w+"` olur (var olan dosyayı keser veya okuma ve yazma için oluşturma).

- `ios_base::in | ios_base::out | ios_base::app` `"a+"` olur (var olan dosyayı okumak ve tüm yazmaları eklemek için açın).

`mode & ios_base::binary` sıfır değilse, işlevi bir metin akışı yerine bir ikili akışı açmak için `strmode` `b` ekler. Daha sonra dosya işaretçisi `fp``fopen` tarafından döndürülen değeri depolar. `mode & ios_base::ate` sıfır değilse ve dosya işaretçisi boş bir işaretçi değilse, işlev, dosyanın sonunda akışı konumlandırmak için `fseek(fp, 0, SEEK_END)` çağırır. Bu konumlandırma işlemi başarısız olursa, işlev [`close`](#close)`(fp)` çağırır ve dosya işaretçisine boş bir işaretçi depolar.

Dosya işaretçisi boş bir işaretçi değilse, işlev dosya dönüştürme modeli: `use_facet<codecvt<Char_T, char, traits_type::`[`state_type`](../standard-library/char-traits-struct.md#state_type)`> >(`[`getloc`](../standard-library/basic-streambuf-class.md#getloc)`)`, [yetersiz](#underflow) ve [taşma](#overflow)tarafından kullanılacak şekilde belirlenir.

Dosya işaretçisi null işaretçisiyse, işlev null bir işaretçi döndürür. Aksi takdirde, bunu **döndürür.**

### <a name="example"></a>Örnek

`open`kullanan bir örnek için bkz. [`basic_filebuf::close`](#close) .

## <a name="op_eq"></a>basic_filebuf:: operator =

Bu akış arabelleği nesnesinin içeriğini atayın. Bu, arkasında bir kopya terk olmayan bir rvalue içeren bir taşıma atamasıdır.

```cpp
basic_filebuf& operator=(basic_filebuf&& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
[Basic_filebuf](../standard-library/basic-filebuf-class.md) nesnesine bir rvalue başvurusu.

### <a name="return-value"></a>Dönüş Değeri

__* This__döndürür.

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

İşlev başarılı olmazsa `traits_type::eof`döndürür. Aksi halde,`(_Meta)``traits_type::`[`not_eof`](../standard-library/char-traits-struct.md#not_eof) döndürür.

### <a name="remarks"></a>Açıklamalar

`_Meta != traits_type::`[`eof`](../standard-library/char-traits-struct.md#eof), korumalı sanal üye işlevi `ch = traits_type::``(_Meta)` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) öğesini çıkış arabelleğine eklemeyi dener. Bunu çeşitli yollarla yapabilirsiniz:

- Bir yazma konumu varsa, öğeyi yazma konumuna kaydedebilir ve çıkış arabelleği için sonraki işaretçiyi artırabilirsiniz.

- Çıktı arabelleği için yeni veya ek depolama alanı ayırarak bir yazma konumu kullanılabilir hale getirir.

- Gerektiğinde `fac.out` çağırmak için dosya dönüştürme modeli `fac` kullanarak, çıkış arabelleğindeki bekleyen çıktıyı dönüştürebilir `ch`. *Char* türünde oluşturulan her öğe `ch`, dosya işaretçisi tarafından belirtilen ilişkili akışa yazılır ve bu form `fputc(ch, fp)`art arda çağrılar olarak `fp`. Herhangi bir dönüştürme veya yazma işlemi başarısız olursa, işlev başarılı olmaz.

## <a name="pbackfail"></a>basic_filebuf::p geri başarısız

Giriş akışına bir öğe geri döndürmeye çalışır, sonra bunu geçerli öğe yapar (sonraki işaretçinin gösterdiği).

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `traits_type::eof`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olmazsa `traits_type::eof`döndürür. Aksi halde,`(_Meta)``traits_type::`[`not_eof`](../standard-library/char-traits-struct.md#not_eof) döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, giriş arabelleğine bir öğe koyar ve sonra bunu geçerli öğe yapar (sonraki işaretçi tarafından işaret edilen). `_Meta == traits_type::`[`eof`](../standard-library/char-traits-struct.md#eof), geri gönderme öğesi geçerli öğeden önceki bir akışta etkin değil. Aksi takdirde, bu öğe `ch = traits_type::`[`to_char_type`](../standard-library/char-traits-struct.md#to_char_type)`(_Meta)`ile değiştirilmiştir. İşlevi bir öğeyi çeşitli yollarla geri alabilir:

- `putback` bir konum varsa ve bu öğe `ch`eşit olarak karşılaştırırsa, giriş arabelleği için bir sonraki işaretçiyi azaledebilir.

- İşlev `putback` bir konum yapabiliyorsanız, bunu yapabilir, sonraki işaretçiyi o konuma işaret etmek için ayarlayabilir ve bu konumda `ch` deposaklayabilir.

- İşlev, giriş akışına bir öğe geri gönderebiliyorsanız, örneğin **char**türünde bir öğe için `ungetc` çağırarak.

## <a name="pos_type"></a>basic_filebuf::p os_type

Bu türü `basic_filebuf` kapsam içinde `Tr` kapsamındaki aynı ada sahip olan türe eşit hale getirir.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="seekoff"></a>basic_filebuf:: seekoff

Denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışır.

```cpp
virtual pos_type seekoff(
    off_type _Off,
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

Yeni konumu veya geçersiz akış konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları değiştirmeyi dener. [`basic_filebuf`](../standard-library/basic-filebuf-class.md)`<Char_T, Tr>`sınıfının bir nesnesi için, bir akış konumu `fpos_t`türünde bir nesne tarafından temsil edilebilir, bu da geniş bir akışı ayrıştırmak için gereken bir konum ve herhangi bir durum bilgisi depolar. Sıfır değeri akışın ilk öğesine başvurur. ( [`pos_type`](../standard-library/basic-streambuf-class.md#pos_type) türünde bir nesne en az bir `fpos_t` nesnesini depolar.)

Hem okuma hem de yazma için açılmış bir dosya için hem giriş hem de çıkış akışları birlikte konumlandırılır. Ekleme ve ayıklama arasında geçiş yapmak için [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) ya da [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos)çağırmanız gerekir. `pubseekoff` yapılan çağrılar (ve bu nedenle `seekoff`) [metin akışları](../c-runtime-library/text-and-binary-streams.md), [ikili akışlar](../c-runtime-library/text-and-binary-streams.md)ve [geniş akışlar](../c-runtime-library/byte-and-wide-streams.md)için çeşitli sınırlamalara sahiptir.

Dosya işaretçisi `fp` null işaretçisiyse, işlev başarısız olur. Aksi takdirde, `fseek(fp, _Off, _Way)`çağırarak akış konumunu değiştirmeyi dener. Bu işlev başarılı olursa ve sonuçta elde edilen konum `fposn` `fgetpos(fp, &fposn)`çağırarak saptanabilir, işlev başarılı olur. İşlev başarılı olursa, `fposn`içeren `pos_type` türünde bir değer döndürür. Aksi takdirde, geçersiz bir akış konumu döndürür.

## <a name="seekpos"></a>basic_filebuf:: seekpos

Denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışır.

```cpp
virtual pos_type seekpos(
    pos_type _Sp,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*\
Arama yapılacak konum.

*_Which*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin verir.

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi `fp` null işaretçisiyse, işlev başarısız olur. Aksi takdirde, `fsetpos(fp, &fposn)`çağırarak akış konumunu değiştirmeyi dener; burada `fposn` `pos`depolanan `fpos_t` nesnesidir. Bu işlev başarılı olursa, işlev `pos`döndürür. Aksi takdirde, geçersiz bir akış konumu döndürür. Akış konumunun geçersiz olup olmadığını anlamak için dönüş değerini `pos_type(off_type(-1))`ile karşılaştırın.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları değiştirmeyi dener. [`basic_filebuf`](../standard-library/basic-filebuf-class.md)`<Char_T, Tr>`sınıfının bir nesnesi için, bir akış konumu `fpos_t`türünde bir nesne tarafından temsil edilebilir, bu da geniş bir akışı ayrıştırmak için gereken bir konum ve herhangi bir durum bilgisi depolar. Sıfır değeri akışın ilk öğesine başvurur. (`pos_type` türünde bir nesne en az bir `fpos_t` nesnesini depolar.)

Hem okuma hem de yazma için açılmış bir dosya için hem giriş hem de çıkış akışları birlikte konumlandırılır. Ekleme ve ayıklama arasında geçiş yapmak için [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) ya da [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos)çağırmanız gerekir. `pubseekoff` yapılan çağrılar (ve `seekoff`) metin akışları, ikili akışlar ve geniş akışlar için çeşitli sınırlamalara sahiptir.

Geniş bir akış için, akışın açıldığı veya son `streampos`çağrısından bu yana herhangi bir ekleme gerçekleştiyse, işlev [taşma](#overflow)yöntemini çağırır. Ayrıca, gerektiğinde `fac.unshift` çağırmak için `fac` dosya dönüştürme modeli kullanarak, ilk dönüştürme durumunu geri yüklemek için gereken herhangi bir diziyi de ekler. **Char** türünde oluşturulan her öğe `byte`, dosya işaretçisi tarafından belirtilen ilişkili akışa yazılır ve bu form `fputc(byte, fp)`art arda çağrılar olarak `fp`. `fac.unshift` çağrısı veya herhangi bir yazma işlemi başarısız olursa, işlev başarılı olmaz.

## <a name="setbuf"></a>basic_filebuf:: setarabelleğe

Her türetilmiş akış arabelleği için özel bir işlem gerçekleştirir.

```cpp
virtual basic_streambuf<Char_T, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*_Buffer*\
Arabellek işaretçisi.

*sayı*\
Arabelleğin boyutu.

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi `fp` null işaretçisiyse korumalı üye işlevi sıfır değerini döndürür.

### <a name="remarks"></a>Açıklamalar

`setbuf`, akış için bir arabellek olarak *_buffer* başlayan `count` öğelerin dizisini sunmak üzere `setvbuf( fp, (char*) _Buffer, _IOFBF, count * sizeof( Char_T))` çağırır. Bu işlev sıfır dışında bir değer döndürürse, işlev null bir işaretçi döndürür. Aksi takdirde **, bunu başarılı olarak bildirmek için döndürür** .

## <a name="swap"></a>basic_filebuf:: swap

Bu `basic_filebuf` içeriğini, belirtilen `basic_filebuf`içerikleri için değiş tokuş eder.

```cpp
void swap(basic_filebuf& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Başka bir `basic_filebuf`lvalue başvurusu.

## <a name="sync"></a>basic_filebuf:: Sync

Denetlenen akışları ilişkili dış akışlarla eşitlemeye çalışır.

```cpp
virtual int sync();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi `fp` null işaretçisiyse sıfır döndürür. Aksi takdirde, akış için bekleyen çıktıyı reçeteye göre yalnızca [taşma](#overflow) ve `fflush(fp)` çağrıları başarılı olursa sıfır döndürür.

## <a name="traits_type"></a>basic_filebuf:: traits_type

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

İşlev başarılı olmazsa, `traits_type::`[`eof`](../standard-library/char-traits-struct.md#eof)döndürür. Aksi takdirde, açıklamalar bölümünde açıklandığı gibi dönüştürülmüş `ch`döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, giriş akışından `ch` geçerli öğeyi çıkarmaya çalışır ve öğeyi `traits_type::`[`to_int_type`](../standard-library/char-traits-struct.md#to_int_type)`(ch)`olarak döndürebilir. Bunu çeşitli yollarla yapabilirsiniz:

- Bir okuma konumu varsa, okuma konumunda depolanan öğe olarak `ch` alır ve giriş arabelleği için sonraki işaretçiyi ilerletir.

- Bir veya daha fazla **karakter**türünde bir veya daha fazla öğe okuyabilir ve bu, form `fgetc(fp)`art arda çağrılar tarafından gösterildiği gibi, dosya dönüştürme modeli `fac.in` `fac` kullanarak bunları `Char_T` `ch` bir öğe türüne dönüştürebilir. Herhangi bir okuma veya dönüştürme başarısız olursa, işlev başarılı olmaz.

## <a name="see-also"></a>Ayrıca bkz.

[\<fstream >](../standard-library/fstream.md)\
[Standart kitaplıkta Iş parçacığı güvenliği\ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
