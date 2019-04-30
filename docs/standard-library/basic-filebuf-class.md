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
ms.openlocfilehash: 817e7fb2b434d06d6c0dfdfc100be8004f6fa4ef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62377158"
---
# <a name="basicfilebuf-class"></a>basic_filebuf Sınıfı

Türünde öğeler aktarımını denetleyen bir akış arabelleğinin açıklar *Elem*, olan karakter nitelikleri sınıfı tarafından belirlenen *Tr*, için ve bir dış dosya içinde depolanan öğeleri dizisi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_filebuf : public basic_streambuf<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

*Elem*<br/>
Dosya tamponunun temel öğe.

*tr*<br/>
Temel öğesinin dosya arabelleğinin nitelikler (genellikle `char_traits` <  `Elem`>).

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı türü öğeler aktarımını denetleyen bir akış arabelleğinin tanımlar *Elem*, olan karakter nitelikleri sınıfı tarafından belirlenir *Tr*, için ve depolanan öğelerin bir dizisi dış dosya.

> [!NOTE]
> Türündeki nesneler `basic_filebuf` türü ile bir iç arabellek oluşturulur `char *` bakılmaksızın `char_type` türü parametresi tarafından belirtilen *Elem*. Bir Unicode dize buna (içeren **wchar_t** karakter) bir ANSI dizesine dönüştürülür (içeren **char** karakterler), dahili arabelleğe yazılmadan önce. Arabellekteki Unicode dizeleri depolamak için yeni bir arabellek türü oluşturma **wchar_t** kullanarak ayarlayın [basic_streambuf::pubsetbuf](../standard-library/basic-streambuf-class.md#pubsetbuf) `()` yöntemi. Bu davranış gösteren bir örnek görmek için aşağıya bakın.

Sınıfın bir nesnesi `basic_filebuf` <  `Elem`, `Tr`> atayan bir dosya işaretçisini depolar `FILE` bir açık dosya ile ilişkilendirilmiş akış denetleyen nesne. Ayrıca korumalı üye işlevleri tarafından kullanım için iki dosya dönüştürme modelleri işaretçileri depolar [taşma](#overflow) ve [underflow](#underflow). Daha fazla bilgi için [basic_filebuf::open](#open).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesne türü zorlamak gösterilmiştir `basic_filebuf<wchar_t>` çağırarak kendi iç arabellek Unicode karakterler depolamak için `pubsetbuf()` yöntemi.

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
|[basic_filebuf](#basic_filebuf)|Türünde bir nesne oluşturur `basic_filebuf`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir tür adıyla ilişkilendirir `Elem` şablon parametresi.|
|[int_type](#int_type)|İçinde bu tür yapar `basic_filebuf`'s kapsamı aynı ada türüne eşdeğer `Tr` kapsam.|
|[off_type](#off_type)|İçinde bu tür yapar `basic_filebuf`'s kapsamı aynı ada türüne eşdeğer `Tr` kapsam.|
|[pos_type](#pos_type)|İçinde bu tür yapar `basic_filebuf`'s kapsamı aynı ada türüne eşdeğer `Tr` kapsam.|
|[traits_type](#traits_type)|Bir tür adıyla ilişkilendirir `Tr` şablon parametresi.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[close](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Bir dosya açık olup olmadığını gösterir.|
|[open](#open)|Bir dosya açar.|
|[taşma](#overflow)|Yeni bir karakteri tam bir arabelleğe eklendiğinde çağrılabilir korumalı sanal işlev.|
|[pbackfail](#pbackfail)|Korumalı sanal üye işlevi, bir öğe giriş akışa geri yerleştirin ve ardından (sonraki işaretçisi tarafından işaret edilen) geçerli öğe olun dener.|
|[seekoff](#seekoff)|Korumalı sanal üye işlevi, geçerli konumlar denetimli akışları için alter dener.|
|[seekpos](#seekpos)|Korumalı sanal üye işlevi, geçerli konumlar denetimli akışları için alter dener.|
|[setbuf](#setbuf)|Korumalı sanal üye işlevi her türetilmiş akış arabelleği için bir işlemi belirli gerçekleştirir.|
|[değiştirme](#swap)|Bu içeriği birbiriyle değiştirir `basic_filebuf` içeriği sağlanan `basic_filebuf` parametresi.|
|[Eşitleme](#sync)|Korumalı, sanal işlev ilişkili herhangi bir dış akışlarla denetimli akışları eşitlemeye çalışır.|
|[uflow](../standard-library/basic-streambuf-class.md#uflow)|Korumalı, geçerli öğe girdi akışından ayıklanacak sanal işlev.|
|[yetersiz kalması](#underflow)|Korumalı, geçerli öğe girdi akışından ayıklanacak sanal işlev.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<fstream >

**Namespace:** std

## <a name="basic_filebuf"></a>  basic_filebuf::basic_filebuf

Türünde bir nesne oluşturur `basic_filebuf`.

```cpp
basic_filebuf();

basic_filebuf(basic_filebuf&& right);
```

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu giriş arabelleği ve çıkış arabelleği denetleme tüm işaretçilerin null bir işaretçi depolar. Ayrıca dosya işaretçisini null bir işaretçi depolar.

İkinci oluşturucu içeriğini nesnesiyle başlatır `right`, bir rvalue başvurusu olarak kabul edilir.

## <a name="char_type"></a>  basic_filebuf::char_type

Bir tür adıyla ilişkilendirir `Elem` şablon parametresi.

```cpp
typedef Elem char_type;
```

## <a name="close"></a>  basic_filebuf::Close

Bir dosyayı kapatır.

```cpp
basic_filebuf<Elem, Tr> *close();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisini bir null işaretçi ise üye işlevi bir null işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

`close` çağrıları `fclose`( **fp**). Bu işlev, sıfır olmayan bir değer döndürürse, işlev bir null işaretçi döndürür. Aksi halde **bu** dosya başarıyla kapatıldı belirtmek için.

Akış açıldıktan sonra tüm eklemeleri oluşmadıysa geniş bir akış için ya da son çağrısından sonra `streampos`, işlev çağrıları [taşma](#overflow). Ayrıca ilk dönüştürme durumunu dosya dönüştürme modeli kullanarak geri yüklemek için gerekli herhangi bir dizisi ekler `fac` çağrılacak `fac.unshift` gerektiğinde. Her öğe `byte` türü **char** böylece üretilen dosya işaretçisi tarafından belirlenen ilişkili akışına yazılan `fp` art arda gelen çağrıları biçiminde, olduğu gibi `fputc`( **bayt**, **fp**). Çağrı `fac.unshift` veya herhangi bir yazma başarısız olursa, işlev başarısız olur.

### <a name="example"></a>Örnek

Aşağıdaki örnek iki dosya geçerli dizinde varsayar: basic_filebuf_close.txt (içeriği "test") ve iotest.txt (içeriği olan "ssss").

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

## <a name="int_type"></a>  basic_filebuf::int_type

Bu tür basic_filebuf'ın kapsamında aynı adı türü için eşdeğer yapar `Tr` kapsam.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="is_open"></a>  basic_filebuf::is_open

Bir dosya açık olup olmadığını gösterir.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** dosya işaretçisi null bir işaretçi değilse.

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

## <a name="off_type"></a>  basic_filebuf::off_type

Bu tür basic_filebuf'ın kapsamında aynı adı türü için eşdeğer yapar `Tr` kapsam.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="open"></a>  basic_filebuf::Open

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

*Bilgisi _dosya adını*<br/>
Açmak için dosya adı.

*_Modu*<br/>
Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*<br/>
Koruma, eşdeğer açma varsayılan dosya *shflag* parametresinde [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisini bir null işaretçi ise, işlev bir null işaretçi döndürür. Aksi halde **bu**.

### <a name="remarks"></a>Açıklamalar

Üye işlevi dosya adıyla açılır *filename*, çağırarak [fopen](../c-runtime-library/reference/fopen-wfopen.md)( *filename*, **strmode**). `strmode` gelen belirlenir **modu &**~ ( [tarih](../standard-library/ios-base-class.md#openmode) & &#124; [ikili](../standard-library/ios-base-class.md#openmode)):

- `ios_base::in` olur **"r"** (okuma için mevcut dosyasını açın).

- [ios_base::out](../standard-library/ios-base-class.md#fmtflags) veya **ios_base::out &#124; ios_base::trunc** olur **"w"** (mevcut dosyasını kesmek veya yazma için oluşturun).

- **ios_base::out &#124; uygulama** olur **"a"** (tüm yazma işlemlerini ekleme için mevcut Dosya Aç).

- **ios_base::in &#124; ios_base::out** olur **"r +"** (okuma ve yazma için mevcut dosyasını açın).

- **ios_base::in &#124; ios_base::out &#124; ios_base::trunc** olur **"w +"** (mevcut dosyasını kesmek veya okuma ve yazma için oluşturun).

- **ios_base::in &#124; ios_base::out &#124; ios_base::app** olur **"a +"** (açık mevcut dosyası okuma için ve tüm yazma işlemlerini ekleme için).

Varsa **modu & ios_base::binary** olan sıfır değilse, işlev ekler `b` için `strmode` metin akışına yerine ikili akışa açmak için. Ardından tarafından döndürülen değeri depolar `fopen` dosya işaretçisini içinde `fp`. Varsa **modu & ios_base::ate** sıfır dışında olan ve dosya işaretçisi, null işaretçisiyse, işlev çağrıları değil `fseek`( **fp**, 0, `SEEK_END`) dosya sonunda akış yerleştirmek için. Yerleştirme işlemi başarısız olursa, işlev çağrıları [kapatmak](#close)( `fp`) ve dosya işaretçisi null bir işaretçi depolar.

Dosya işaretçisi, null bir işaretçi değil ise, işlev dosya dönüştürme modeli belirler: `use_facet`< `codecvt`< **Elem**, `char`, **traits_type::**[state_type](../standard-library/char-traits-struct.md#state_type)>> ( [getloc](../standard-library/basic-streambuf-class.md#getloc)), tarafından kullanılmak üzere [underflow](#underflow) ve [taşma](#overflow).

Dosya işaretçisini bir null işaretçi ise, işlev bir null işaretçi döndürür. Aksi halde **bu**.

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::close](#close) kullanan bir örnek için `open`.

## <a name="op_eq"></a>  basic_filebuf::operator =

Bu akış arabelleği nesnenin içeriğini atayın. Bir kopya bırakmaz arkasındaki bir rvalue içeren bir taşıma ataması budur.

```cpp
basic_filebuf& operator=(basic_filebuf&& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Rvalue başvurusuna bir [basic_filebuf](../standard-library/basic-filebuf-class.md) nesne.

### <a name="return-value"></a>Dönüş Değeri

Döndürür * bu.

### <a name="remarks"></a>Açıklamalar

İçeriğini kullanarak üye işleci nesnenin içeriğini değiştirir *doğru*, bir rvalue başvurusu olarak kabul edilir. Daha fazla bilgi için [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="overflow"></a>  basic_filebuf::Overflow

Yeni bir karakteri tam bir arabelleğe eklendiğinde çağrılır.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Parametreler

*_Meta*<br/>
Karakter arabelleğine ekleme veya `traits_type::eof`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürür `traits_type::eof`. Aksi halde **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*).

### <a name="remarks"></a>Açıklamalar

Varsa *_Meta* **! traits_type =::**[eof](../standard-library/char-traits-struct.md#eof), korumalı sanal üye işlevi endeavors öğe eklemek **ch traits_type =::** [ to_char_type](../standard-library/char-traits-struct.md#to_char_type)(*_Meta*) çıktı arabelleğine. Bunu çeşitli yöntemlerle yapabilirsiniz:

- Yazma konumunu varsa, bu öğe yazma konumuna depolayabilir ve çıkış arabelleği için sonraki işaretçisine artırılacak.

- Çıkış arabelleği için yeni veya ek depolama alanı ayırarak bunu yazma konumunu kullanılabilir duruma getirebilirsiniz.

- Ardından, çıkış arabelleği bekleyen herhangi bir çıktı dönüştürebilirsiniz `ch`, dosya dönüştürme modeli kullanarak `fac` çağırmak için `fac.out` gerektiğinde. Her öğe `ch` türü *char* böylece üretilen dosya işaretçisi tarafından belirlenen ilişkili akışına yazılan `fp` art arda gelen çağrıları biçiminde, olduğu gibi `fputc`( **ch**, **fp**). Herhangi bir dönüştürme veya yazma başarısız olursa, işlev başarılı olmaz.

## <a name="pbackfail"></a>  basic_filebuf::pbackfail

Bir öğe giriş akışa geri yerleştirin ve ardından (sonraki işaretçisi tarafından işaret edilen) geçerli öğe olun dener.

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Parametreler

*_Meta*<br/>
Karakter arabelleğine ekleme veya `traits_type::eof`.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürür `traits_type::eof`. Aksi halde **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(*\_Meta*).

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi bir öğe giriş belleğe geri alır ve ardından (sonraki işaretçisi tarafından işaret edilen) geçerli öğe yapar. Varsa  *\_Meta* **traits_type ==::**[eof](../standard-library/char-traits-struct.md#eof), geri göndermek için etkili bir şekilde akış önce geçerli öğe zaten bir öğedir. Aksi takdirde, bu öğe tarafından değiştirilir **ch traits_type =::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(*\_Meta*). İşlevi, öğenin çeşitli yollarla geri koyabilirsiniz:

- Putback konum kullanılabilir ve burada depolanan öğenin eşit karşılaştırır `ch`, sonraki işaretçisi giriş arabelleği için azaltma.

- İşlev geçerliyse bir `putback` getirin ve depolayan konumu Bunu yapmak, sonraki işaretçisi işaret için ayarlanmış kullanılabilir `ch` konumda.

- İşlev giriş akışa geri bir öğe gönderebilir, bunu, gibi çağırarak yapabilirsiniz `ungetc` türünde bir öğe için **char**.

## <a name="pos_type"></a>  basic_filebuf::pos_type

Bu tür basic_filebuf'ın kapsamında aynı adı türü için eşdeğer yapar `Tr` kapsam.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="seekoff"></a>  basic_filebuf::seekoff

Denetlenen akışlar için geçerli konumları alter dener.

```cpp
virtual pos_type seekoff(off_type _Off,
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

Yeni bir konuma veya geçersiz akış konumu döndürür.

### <a name="remarks"></a>Açıklamalar

Denetlenen akışlar için geçerli konumları değiştirmek korumalı sanal üye işlevi endeavors. Sınıfın bir nesnesi için [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>, bir akış konumu türünde bir nesne tarafından temsil edilebilir `fpos_t`, bir uzaklık depolar ve herhangi bir durum bilgi gerekiyor geniş bir akışı ayrıştıramadı. Uzaklık sıfır akışın ilk öğeyi belirtir. (Bir nesne türü [pos_type](../standard-library/basic-streambuf-class.md#pos_type) en az bir depolar `fpos_t` nesne.)

Hem okuma hem de yazma için açılmış bir dosya için girdi ve çıktı akışları dağıtımınızla yerleştirilir. Ekleme ve ayıklama arasında geçiş yapmak için ya da çağırmalıdır [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) veya [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos). Çağrılar `pubseekoff` (ve dolayısıyla için `seekoff`) çeşitli sınırlamaları sahip [metin akışları](../c-runtime-library/text-and-binary-streams.md), [ikili akışlar](../c-runtime-library/text-and-binary-streams.md), ve [geniş akışlar](../c-runtime-library/byte-and-wide-streams.md).

Dosya işaretçisini `fp` null işaretçisiyse, işlev başarısız olur. Aksi takdirde, çağrı yaparak akış konumu değiştirmek endeavors `fseek`( **fp**, `_Off`, `_Way`). Bu işlev başarılı olursa ve konumu `fposn` çağırarak belirlenebilir `fgetpos`( **fp**, **& fposn**), işlev başarılı. İşlev başarılı olursa, türünde bir değer döndürür. `pos_type` içeren `fposn`. Aksi takdirde geçersiz akış konumu döndürür.

## <a name="seekpos"></a>  basic_filebuf::seekpos

Denetlenen akışlar için geçerli konumları alter dener.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*_Sp*<br/>
Arama konumu.

*_Which*<br/>
İşaretçisi konumunu modunu belirtir. Değiştirme okuma ve yazma konumları olanak tanımak için varsayılandır.

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisini `fp` null işaretçisiyse, işlev başarısız olur. Aksi takdirde, çağrı yaparak akış konumu değiştirmek endeavors `fsetpos`( **fp**, **& fposn**), burada `fposn` olduğu `fpos_t` depolanan nesne `pos`. İşlev başarılı olursa bu işlev, döndürür `pos`. Aksi takdirde geçersiz akış konumu döndürür. Akış konumu geçersiz olup olmadığını belirlemek için dönüş değeri ile karşılaştırmak `pos_type(off_type(-1))`.

### <a name="remarks"></a>Açıklamalar

Denetlenen akışlar için geçerli konumları değiştirmek korumalı sanal üye işlevi endeavors. Sınıfın bir nesnesi için [basic_filebuf](../standard-library/basic-filebuf-class.md) \< **Elem**, **Tr**>, bir akış konumu türünde bir nesne tarafından temsil edilebilir `fpos_t`, hangi depoları bir uzaklık ve geniş bir akışı ayrıştırmak için gerekli tüm durum bilgileri. Uzaklık sıfır akışın ilk öğeyi belirtir. (Bir nesne türü `pos_type` en az bir depolar `fpos_t` nesne.)

Hem okuma hem de yazma için açılmış bir dosya için girdi ve çıktı akışları dağıtımınızla yerleştirilir. Ekleme ve ayıklama arasında geçiş yapmak için ya da çağırmalıdır [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) veya [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos). Çağrılar `pubseekoff` (ve dolayısıyla için `seekoff`) metin akışları, ikili akışlar ve geniş akışlar için çeşitli sınırlamaları vardır.

Akış açıldıktan sonra tüm eklemeleri oluşmadıysa geniş bir akış için ya da son çağrısından sonra `streampos`, işlev çağrıları [taşma](#overflow). Ayrıca ilk dönüştürme durumunu dosya dönüştürme modeli kullanarak geri yüklemek için gerekli herhangi bir dizisi ekler `fac` çağrılacak **fac** `.unshift` gerektiğinde. Her öğe `byte` türü **char** böylece üretilen dosya işaretçisi tarafından belirlenen ilişkili akışına yazılan `fp` art arda gelen çağrıları biçiminde, olduğu gibi `fputc`( **bayt**, **fp**). Çağrı `fac.unshift` veya herhangi bir yazma başarısız olursa, işlev başarısız olur.

## <a name="setbuf"></a>  basic_filebuf::setbuf

Her türetilmiş akış arabelleği için bir işlemi belirli gerçekleştirir.

```cpp
virtual basic_streambuf<Elem, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

*_Buffer*<br/>
Arabellek için işaretçi.

*Sayısı*<br/>
Arabellek boyutu.

### <a name="return-value"></a>Dönüş Değeri

Korumalı üye işlevi, dosya işaretçisini sıfır döndürür `fp` bir null işaretçidir.

### <a name="remarks"></a>Açıklamalar

`setbuf` çağrıları `setvbuf`( **fp**, ( `char` \*) `_Buffer`, `_IOFBF`, `count` \* `sizeof` ( **Elem**)) sunan için ' ın `count` _ başlayan öğeleri *arabellek* akış için bir arabellek. Bu işlev, sıfır olmayan bir değer döndürürse, işlev bir null işaretçi döndürür. Aksi halde **bu** sinyal başarılı.

## <a name="swap"></a>  basic_filebuf::Swap

Bu içeriğini birbiriyle değiştirir `basic_filebuf` sağlanan içeriklerinin `basic_filebuf`.

```cpp
void swap(basic_filebuf& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bir `lvalue` başka bir başvuru `basic_filebuf`.

## <a name="sync"></a>  basic_filebuf::Sync

Denetlenen akışları ilişkili herhangi bir dış akışlarla eşitlemeye çalışır.

```cpp
virtual int sync();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisini sıfır döndürür `fp` bir null işaretçidir. Aksi takdirde, yalnızca sıfır ise çağıran her iki döndürür [taşma](#overflow) ve `fflush`( **fp**) bekleyen herhangi bir çıktı akışına boşaltma başarılı.

## <a name="traits_type"></a>  basic_filebuf::traits_type

Bir tür adıyla ilişkilendirir `Tr` şablon parametresi.

```cpp
typedef Tr traits_type;
```

## <a name="underflow"></a>  basic_filebuf::underflow

Geçerli öğe girdi akışından ayıklar.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa, döndürür **traits_type::**[eof](../standard-library/char-traits-struct.md#eof). Aksi halde `ch`, açıklamalar bölümünde açıklanan şekilde dönüştürülmüş.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi endeavors geçerli öğe ayıklanacak `ch` girdisinden akışla aktarma ve öğenin iade **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)(`ch`). Bunu çeşitli yöntemlerle yapabilirsiniz:

- Okuma konumuna kullanılabilir haldeyse, sürdüğünü `ch` öğesi salt okunur bir konumda depolanan ve giriş arabelleği için sonraki işaretçisi ilerler.

- Türünde öğeler bir veya daha fazla bilgi edinebilirsiniz **char**, birbirini izleyen çağrılar form gibi tarafından `fgetc`(**fp**) ve bunları bir öğeye Dönüştür **ch** türü `Elem`çağırmak için dosya dönüştürme modeli fac kullanarak `fac.in` gerektiğinde. Herhangi bir okuma veya dönüştürme başarısız olursa, işlev başarılı olmaz.

## <a name="see-also"></a>Ayrıca bkz.

[\<fstream >](../standard-library/fstream.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
