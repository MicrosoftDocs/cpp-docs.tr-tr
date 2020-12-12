---
description: 'Hakkında daha fazla bilgi edinin: basic_filebuf sınıfı'
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
ms.openlocfilehash: fedda394d2b10d07cda0580197f6763453455c4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335786"
---
# <a name="basic_filebuf-class"></a>basic_filebuf Sınıfı

Karakter *nitelikleri, bir* dış dosyada depolanan öğelerin dizisine ve sonuna kadar olan *Char_T* türündeki öğelerin aktarımını denetleyen bir akış arabelleğini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Char_T, class Tr = char_traits<Char_T>>
class basic_filebuf : public basic_streambuf<Char_T, Tr>
```

### <a name="parameters"></a>Parametreler

*Char_T*\
Dosya arabelleğinin temel öğesi.

*Tr*\
Dosya arabelleğinin temel öğesinin nitelikleri (genellikle `char_traits<Char_T>` ).

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, *Char_T* türünde öğelerin aktarımını denetleyen bir akış arabelleği tanımlar. Bu, karakter nitelikleri, bir dış dosyada depolanan öğelerin dizisine ve sonuna *kadar, karakter* nitelikleri belirler.

> [!NOTE]
> Türündeki nesneler, tür `basic_filebuf` __\*__ `char_type` parametresi tarafından belirtilen *Char_T* bağımsız olarak char türünde bir iç arabellekle oluşturulur. Bu, bir Unicode dizesinin (karakter içeren **`wchar_t`** ), **`char`** iç arabelleğe yazılmadan önce bir ANSI dizesine (karakterler içeren) dönüştürülemeyeceği anlamına gelir. Arabellekte Unicode dizeleri depolamak için, yeni bir ara bellek oluşturun **`wchar_t`** ve yöntemi kullanarak ayarlayın [`basic_streambuf::pubsetbuf`](../standard-library/basic-streambuf-class.md#pubsetbuf) `()` . Bu davranışı gösteren bir örnek görmek için aşağıya bakın.

Sınıfının bir nesnesi `basic_filebuf<Char_T, Tr>` , bir `FILE` Açık dosyayla ilişkili akışı denetleyen nesneyi atayan bir dosya işaretçisi depolar. Ayrıca, korumalı üye işlevleri [taşması](#overflow) ve [yetersiz kalması](#underflow)tarafından kullanılmak üzere iki dosya dönüştürme modellerinin işaretçilerini depolar. Daha fazla bilgi için bkz. [`basic_filebuf::open`](#open).

## <a name="example"></a>Örnek

Aşağıdaki örnek, yöntemini çağırarak bir nesne türünün, `basic_filebuf<wchar_t>` iç arabellekte Unicode karakterleri nasıl depolayabileceğinizi göstermektedir `pubsetbuf()` .

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
|[basic_filebuf](#basic_filebuf)|Türünde bir nesne oluşturur `basic_filebuf` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir tür adını `Char_T` şablon parametresiyle ilişkilendirir.|
|[int_type](#int_type)|Bu türün `basic_filebuf` kapsamını kapsamdaki aynı adın türüne eşit hale getirir `Tr` .|
|[off_type](#off_type)|Bu türün `basic_filebuf` kapsamını kapsamdaki aynı adın türüne eşit hale getirir `Tr` .|
|[pos_type](#pos_type)|Bu türün `basic_filebuf` kapsamını kapsamdaki aynı adın türüne eşit hale getirir `Tr` .|
|[traits_type](#traits_type)|Bir tür adını `Tr` şablon parametresiyle ilişkilendirir.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[~eksik](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Bir dosyanın açık olup olmadığını gösterir.|
|[açın](#open)|Bir dosya açar.|
|[taşma](#overflow)|Tam arabelleğe yeni bir karakter eklendiğinde çağrılabilen, korunan bir sanal işlev.|
|[pbackfail](#pbackfail)|Korumalı sanal üye işlevi, giriş akışına bir öğe geri döndürmeye çalışır ve sonra geçerli öğe (sonraki işaretçinin gösterdiği) yapar.|
|[seekoff](#seekoff)|Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışır.|
|[seekpos](#seekpos)|Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışır.|
|[setbuf](#setbuf)|Korumalı sanal üye işlevi, her türetilmiş akış arabelleği için bir işlem gerçekleştirir.|
|[Kur](#swap)|Bunun içeriğini, `basic_filebuf` belirtilen parametrenin içeriği için değiş tokuş eder `basic_filebuf` .|
|[Eşitleme](#sync)|Korumalı, sanal işlev denetimli akışları ilişkili dış akışlarla eşitlemeye çalışır.|
|[uflow](../standard-library/basic-streambuf-class.md#uflow)|Geçerli öğeyi giriş akışından ayıklamak için korumalı, sanal işlev.|
|[öğe](#underflow)|Geçerli öğeyi giriş akışından ayıklamak için korumalı, sanal işlev.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<fstream>

**Ad alanı:** std

## <a name="basic_filebufbasic_filebuf"></a><a name="basic_filebuf"></a> basic_filebuf:: basic_filebuf

Türünde bir nesne oluşturur `basic_filebuf` .

```cpp
basic_filebuf();

basic_filebuf(basic_filebuf&& right);
```

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, giriş arabelleğini ve çıkış arabelleğini denetleyen tüm işaretçilerde boş bir işaretçi depolar. Ayrıca dosya işaretçisine bir null işaretçi depolar.

İkinci Oluşturucu, nesneyi *sağ* içeriğiyle başlatır ve rvalue başvurusu olarak kabul edilir.

## <a name="basic_filebufchar_type"></a><a name="char_type"></a> basic_filebuf:: char_type

Bir tür adını `Char_T` şablon parametresiyle ilişkilendirir.

```cpp
typedef Char_T char_type;
```

## <a name="basic_filebufclose"></a><a name="close"></a> basic_filebuf:: Close

Bir dosyayı kapatır.

```cpp
basic_filebuf<Char_T, Tr> *close();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi null işaretçisiyse üye işlevi null bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

`close` çağırır `fclose(fp)` . Bu işlev sıfır dışında bir değer döndürürse, işlev null bir işaretçi döndürür. Aksi takdirde, **`this`** dosyanın başarıyla kapatıldığını göstermek için döndürür.

Geniş bir akış için, akışın açıldığı veya son çağrısından bu yana herhangi bir ekleme gerçekleştiyse, `streampos` işlev çağırır [`overflow`](#overflow) . Ayrıca, gerektiğinde çağırmak için dosya dönüştürme modeli kullanılarak, ilk dönüştürme durumunu geri yüklemek için gereken herhangi bir diziyi de ekler `fac` `fac.unshift` . Türünde oluşturulan her öğe, `byte` **`char`** Dosya işaretçisi tarafından belirlenen ilişkili akışa, `fp` form art arda yapılan çağrılar ile yazılır `fputc(byte, fp)` . `fac.unshift`Veya yazma çağrısı başarısız olursa, işlev başarılı olmaz.

### <a name="example"></a>Örnek

Aşağıdaki örnek Şu anki dizindeki iki dosyayı varsayar: *basic_filebuf_close.txt* (içerik "test") ve *iotest.txt* (içerik "ssss").

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

## <a name="basic_filebufint_type"></a><a name="int_type"></a> basic_filebuf:: int_type

Kapsam içinde bu türü `basic_filebuf` kapsamdaki aynı ada sahip türe eşit hale getirir `Tr` .

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="basic_filebufis_open"></a><a name="is_open"></a> basic_filebuf:: is_open

Bir dosyanın açık olup olmadığını gösterir.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** Dosya işaretçisi null değilse.

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

## <a name="basic_filebufoff_type"></a><a name="off_type"></a> basic_filebuf:: off_type

Kapsam içinde bu türü `basic_filebuf` kapsamdaki aynı ada sahip türe eşit hale getirir `Tr` .

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="basic_filebufopen"></a><a name="open"></a> basic_filebuf:: Open

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

*kısaltın*\
Açılacak dosyanın adı.

*modundaysa*\
İçindeki Numaralandırmalardan biri [`ios_base::openmode`](../standard-library/ios-base-class.md#openmode) .

*korunmasına*\
Varsayılan dosya açma koruması, [_fsopen _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md) *shflag* parametresine eşdeğerdir.

### <a name="return-value"></a>Dönüş Değeri

Arabellek zaten açıksa veya dosya işaretçisi null işaretçisiyse, işlev null bir işaretçi döndürür. Aksi takdirde, döndürür **`this`** .

### <a name="remarks"></a>Açıklamalar

Bu işlev, öğesini `FILE *` `basic_filebuf` çağırmış olsanız gibi geri yüklemek için bir kullanır [`fopen/wfopen`](../c-runtime-library/reference/fopen-wfopen.md) `(filename, strmode)` . `strmode`belirlenir `mode & ~(` [`ate`](../standard-library/ios-base-class.md#openmode) `|` [`binary`](../standard-library/ios-base-class.md#openmode) `)` :

- `ios_base::in` olur `"r"` (mevcut dosyayı okumak için açın).
- [ios_base:: Out](../standard-library/ios-base-class.md#fmtflags) veya `ios_base::out | ios_base::trunc` `"w"` (var olan dosyayı Kes veya yazma için Oluştur) olur.
- `ios_base::out | app` olur `"a"` (tüm yazmaları eklemek için mevcut dosyayı açın).
- `ios_base::in | ios_base::out` olur `"r+"` (mevcut dosyayı okumak ve yazmak için açın).
- `ios_base::in | ios_base::out | ios_base::trunc` olur `"w+"` (var olan dosyayı keser veya okuma ve yazma için oluşturma).
- `ios_base::in | ios_base::out | ios_base::app` olur `"a+"` (var olan dosyayı okumak ve tüm yazmaları eklemek için açın).

`mode & ios_base::binary`Sıfır değilse, işlevi `b` `strmode` bir metin akışı yerine bir ikili akış açmak için öğesine ekler.
`mode & ios_base::ate`Sıfır değilse ve dosya başarıyla açıldıysa, akıştaki geçerli konum dosyanın sonuna yerleştirilir. Bu başarısız olursa, dosya kapatılır.

Yukarıdaki işlemler başarıyla tamamlanırsa, dosya dönüştürme modeli belirlenir: `use_facet<codecvt<Char_T, char, traits_type::` [`state_type`](../standard-library/char-traits-struct.md#state_type) `> >(` [`getloc`](../standard-library/basic-streambuf-class.md#getloc) `)` , [yetersiz](#underflow) ve [taşma](#overflow)tarafından kullanılmak üzere.

Dosya başarıyla açılamadığı takdirde null döndürülür.

### <a name="example"></a>Örnek

Tarafından [`basic_filebuf::close`](#close) kullanılan bir örnek için bkz `open` ..

## <a name="basic_filebufoperator"></a><a name="op_eq"></a> basic_filebuf:: operator =

Bu akış arabelleği nesnesinin içeriğini atayın. Bu, arkasında bir kopya terk olmayan bir rvalue içeren bir taşıma atamasıdır.

```cpp
basic_filebuf& operator=(basic_filebuf&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
[Basic_filebuf](../standard-library/basic-filebuf-class.md) nesnesine bir rvalue başvurusu.

### <a name="return-value"></a>Dönüş Değeri

__* This__ döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işleci, bir rvalue başvurusu olarak kabul edilen, *sağ* içeriğini kullanarak nesnesinin içeriğini değiştirir. Daha fazla bilgi için bkz. [rvalue başvuru bildirimci:  &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="basic_filebufoverflow"></a><a name="overflow"></a> basic_filebuf:: overflow

Tam arabelleğe yeni bir karakter eklendiğinde çağırılır.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `traits_type::eof` .

### <a name="return-value"></a>Dönüş Değeri

İşlev başarısız olursa, döndürür `traits_type::eof` . Aksi takdirde, döndürür `traits_type::` [`not_eof`](../standard-library/char-traits-struct.md#not_eof) `(_Meta)` .

### <a name="remarks"></a>Açıklamalar

Eğer `_Meta != traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof) , korumalı sanal üye işlevi, `ch = traits_type::` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) `(_Meta)` Çıkış arabelleğine öğe eklemeye çalışır. Bunu çeşitli yollarla yapabilirsiniz:

- Bir yazma konumu varsa, öğeyi yazma konumuna kaydedebilir ve çıkış arabelleği için sonraki işaretçiyi artırabilirsiniz.

- Çıktı arabelleği için yeni veya ek depolama alanı ayırarak bir yazma konumu kullanılabilir hale getirir.

- `ch` `fac` Gerekli olduğu gibi çağırmak için dosya dönüştürme modeli ' ni kullanarak çıkış arabelleğindeki bekleyen çıktıyı dönüştürebilir `fac.out` . Char türünde oluşturulan her öğe, `ch`  `fp` form art arda gelen çağrılar tarafından gösterildiği gibi, dosya işaretçisi tarafından belirtilen ilişkili akışa yazılır `fputc(ch, fp)` . Herhangi bir dönüştürme veya yazma işlemi başarısız olursa, işlev başarılı olmaz.

## <a name="basic_filebufpbackfail"></a><a name="pbackfail"></a> basic_filebuf::p geri başarısız

Giriş akışına bir öğe geri döndürmeye çalışır, sonra bunu geçerli öğe yapar (sonraki işaretçinin gösterdiği).

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Parametreler

*_Meta*\
Arabelleğe eklenecek karakter veya `traits_type::eof` .

### <a name="return-value"></a>Dönüş Değeri

İşlev başarısız olursa, döndürür `traits_type::eof` . Aksi takdirde, döndürür `traits_type::` [`not_eof`](../standard-library/char-traits-struct.md#not_eof) `(_Meta)` .

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, giriş arabelleğine bir öğe koyar ve sonra bunu geçerli öğe yapar (sonraki işaretçi tarafından işaret edilen). Varsa `_Meta == traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof) , geri gönderme öğesi geçerli öğeden önceki akışta etkin bir şekilde zaten var. Aksi takdirde, bu öğe ile değiştirilmiştir `ch = traits_type::` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) `(_Meta)` . İşlevi bir öğeyi çeşitli yollarla geri alabilir:

- Bir `putback` konum varsa ve şuna eşit olarak karşılaştırıldığı öğe, `ch` giriş arabelleği için bir sonraki işaretçiyi azaledebilir.

- İşlev bir konum kullanılabilir hale getirmek `putback` için bu işlemi yapabilir, sonraki işaretçiyi o konuma işaret etmek için ayarlayabilir ve `ch` Bu konumda saklayın.

- İşlev, giriş akışına bir öğe geri gönderebiliyorsanız, türü gibi bir öğe çağırarak, bu işlemi yapabilir `ungetc` **`char`** .

## <a name="basic_filebufpos_type"></a><a name="pos_type"></a> basic_filebuf::p os_type

Kapsam içinde bu türü `basic_filebuf` kapsamdaki aynı ada sahip türe eşit hale getirir `Tr` .

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="basic_filebufseekoff"></a><a name="seekoff"></a> basic_filebuf:: seekoff

Denetlenen akışlar için geçerli pozisyonları değiştirmeye çalışır.

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Off*\
*_Way* göreli olarak arama konumu.

*_Way*\
Dengeleme işlemleri için başlangıç noktası. Olası değerler için bkz. [seekdir](../standard-library/ios-base-class.md#seekdir) .

*_Which*\
İşaretçi konumunun modunu belirtir. Varsayılan değer, okuma ve yazma konumlarını değiştirmenize izin verir.

### <a name="return-value"></a>Dönüş Değeri

Yeni konumu veya geçersiz akış konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları değiştirmeyi dener. Sınıfının bir nesnesi için [`basic_filebuf`](../standard-library/basic-filebuf-class.md) `<Char_T, Tr>` , bir akış konumu türünde bir nesne ile temsil edilebilir `fpos_t` , bu da bir sapmayı ve geniş bir akışı ayrıştırmak için gereken durum bilgilerini depolar. Sıfır değeri akışın ilk öğesine başvurur. (Türünde bir nesne [`pos_type`](../standard-library/basic-streambuf-class.md#pos_type) en az bir nesneyi depolar `fpos_t` .)

Hem okuma hem de yazma için açılmış bir dosya için hem giriş hem de çıkış akışları birlikte konumlandırılır. Ekleme ve ayıklama arasında geçiş yapmak için ya da ' i çağırmanız gerekir [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos) . `pubseekoff`(Ve bu nedenle) çağrılarının `seekoff` , [metin akışları](../c-runtime-library/text-and-binary-streams.md), [ikili akışlar](../c-runtime-library/text-and-binary-streams.md)ve [geniş akışlar](../c-runtime-library/byte-and-wide-streams.md)için çeşitli sınırlamaları vardır.

Dosya işaretçisi `fp` null işaretçisiyse, işlev başarısız olur. Aksi halde, çağırarak akış konumunu değiştirmeyi dener `fseek(fp, _Off, _Way)` . Bu işlev başarılı olursa ve sonuçta elde edilen konum `fposn` çağırarak `fgetpos(fp, &fposn)` , işlev başarılı olur. İşlev başarılı olursa, içeren türünde bir değer döndürür `pos_type` `fposn` . Aksi takdirde, geçersiz bir akış konumu döndürür.

## <a name="basic_filebufseekpos"></a><a name="seekpos"></a> basic_filebuf:: seekpos

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

Dosya işaretçisi `fp` null işaretçisiyse, işlev başarısız olur. Aksi halde, öğesini çağırarak akış konumunu değiştirme girişiminde bulunur `fsetpos(fp, &fposn)` , burada ' `fposn` `fpos_t` de depolanan nesnedir `pos` . Bu işlev başarılı olursa, işlev döndürür `pos` . Aksi takdirde, geçersiz bir akış konumu döndürür. Akış konumunun geçersiz olup olmadığını anlamak için dönüş değerini ile karşılaştırın `pos_type(off_type(-1))` .

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, denetlenen akışlar için geçerli pozisyonları değiştirmeyi dener. Sınıfının bir nesnesi için [`basic_filebuf`](../standard-library/basic-filebuf-class.md) `<Char_T, Tr>` , bir akış konumu türünde bir nesne ile temsil edilebilir `fpos_t` , bu da bir sapmayı ve geniş bir akışı ayrıştırmak için gereken durum bilgilerini depolar. Sıfır değeri akışın ilk öğesine başvurur. (Türünde bir nesne `pos_type` en az bir nesneyi depolar `fpos_t` .)

Hem okuma hem de yazma için açılmış bir dosya için hem giriş hem de çıkış akışları birlikte konumlandırılır. Ekleme ve ayıklama arasında geçiş yapmak için ya da ' i çağırmanız gerekir [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos) . `pubseekoff`(Ve için) çağrılarının `seekoff` metin akışları, ikili akışlar ve geniş akışlar için çeşitli sınırlamaları vardır.

Geniş bir akış için, akışın açıldığı veya son çağrısından bu yana herhangi bir ekleme gerçekleştiyse, `streampos` işlev [taşma](#overflow)işlevini çağırır. Ayrıca, gerektiğinde çağırmak için dosya dönüştürme modeli kullanılarak, ilk dönüştürme durumunu geri yüklemek için gereken herhangi bir diziyi de ekler `fac` `fac.unshift` . Türünde oluşturulan her öğe, `byte` **`char`** Dosya işaretçisi tarafından belirlenen ilişkili akışa, `fp` form art arda yapılan çağrılar ile yazılır `fputc(byte, fp)` . `fac.unshift`Veya yazma çağrısı başarısız olursa, işlev başarılı olmaz.

## <a name="basic_filebufsetbuf"></a><a name="setbuf"></a> basic_filebuf:: setarabelleğe

Her türetilmiş akış arabelleği için özel bir işlem gerçekleştirir.

```cpp
virtual basic_streambuf<Char_T, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*_Buffer*\
Arabellek işaretçisi.

*biriktirme*\
Arabelleğin boyutu.

### <a name="return-value"></a>Dönüş Değeri

Korumalı üye işlevi, dosya işaretçisi `fp` null işaretçisiyse sıfır döndürür.

### <a name="remarks"></a>Açıklamalar

`setbuf``setvbuf( fp, (char*) _Buffer, _IOFBF, count * sizeof( Char_T))` `count` akış için bir arabellek olarak *_buffer* başlayarak öğe dizisini sunmaya yönelik çağrılar. Bu işlev sıfır dışında bir değer döndürürse, işlev null bir işaretçi döndürür. Aksi takdirde, sinyal başarı ' ya döner **`this`** .

## <a name="basic_filebufswap"></a><a name="swap"></a> basic_filebuf:: swap

Bunun içeriğini, `basic_filebuf` belirtilen içeriği için değiş tokuş eder `basic_filebuf` .

```cpp
void swap(basic_filebuf& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Başka bir lvalue başvurusu `basic_filebuf` .

## <a name="basic_filebufsync"></a><a name="sync"></a> basic_filebuf:: Sync

Denetlenen akışları ilişkili dış akışlarla eşitlemeye çalışır.

```cpp
virtual int sync();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi `fp` null işaretçisiyse sıfır döndürür. Aksi takdirde, yalnızca [taşmaya](#overflow) yapılan çağrılar ve `fflush(fp)` akışta bekleyen çıktıyı reçeteye göre her ikisi de başarısız olursa sıfır döndürür.

## <a name="basic_filebuftraits_type"></a><a name="traits_type"></a> basic_filebuf:: traits_type

Bir tür adını `Tr` şablon parametresiyle ilişkilendirir.

```cpp
typedef Tr traits_type;
```

## <a name="basic_filebufunderflow"></a><a name="underflow"></a> basic_filebuf:: yetersiz

Giriş akışından geçerli öğeyi ayıklar.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarısız olursa, döndürür `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof) . Aksi takdirde, `ch` açıklamalar bölümünde açıklandığı gibi dönüştürülmüş döndürülür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, giriş akışından geçerli öğeyi çıkarmaya çalışır `ch` ve öğesini olarak döndürebilir `traits_type::` [`to_int_type`](../standard-library/char-traits-struct.md#to_int_type) `(ch)` . Bunu çeşitli yollarla yapabilirsiniz:

- Bir okuma konumu varsa, `ch` okuma konumunda depolanan öğesi olarak alır ve giriş arabelleği için sonraki işaretçiyi ilerletir.

- Bu, **`char`** formun birbirini izleyen çağrılarında olduğu gibi, türünde bir veya daha fazla öğeyi okuyabilir `fgetc(fp)` ve `ch` `Char_T` `fac` gereken şekilde çağırmak için dosya dönüştürme modeli kullanarak bunları türünde bir öğeye dönüştürebilir `fac.in` . Herhangi bir okuma veya dönüştürme başarısız olursa, işlev başarılı olmaz.

## <a name="see-also"></a>Ayrıca bkz.

[\<fstream>](../standard-library/fstream.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
