---
title: basic_filebuf sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f39b72fd6ef7d734539a9d0677aeb60ca74bec41
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="basicfilebuf-class"></a>basic_filebuf Sınıfı

Türündeki öğeler iletimini denetleyen bir Akış Arabellek açıklar `Elem`, olan karakter nitelikler sınıfı tarafından belirlenir `Tr`, gelen ve giden bir dış dosyasında depolanan öğeleri dizisi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_filebuf : public basic_streambuf<Elem, Tr>
```

### <a name="parameters"></a>Parametreler

`Elem` Dosya arabellek temel öğesidir.

`Tr` Dosya arabellek temel öğesi olarak nitelikler (genellikle `char_traits` <  `Elem`>).

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı türündeki öğeler iletimini denetleyen bir Akış Arabellek açıklar `Elem`, olan karakter nitelikler sınıfı tarafından belirlenir `Tr`, gelen ve giden bir dış dosyasında depolanan öğeleri dizisi.

> [!NOTE]
> Nesne türü `basic_filebuf` türü ile bir iç arabellek oluşturulan `char *` açmamasından `char_type` tür parametresi tarafından belirtilen `Elem`. Bu bir UNICODE dizesi anlamına gelir (içeren `wchar_t` karakter) bir ANSI dizeye dönüştürülür (içeren `char` karakter), iç arabellek yazılmadan önce. Arabellekte Unicode dizeleri depolamak için yeni bir arabellek türü oluşturma `wchar_t` ve kullanarak ayarlayın [basic_streambuf::pubsetbuf](../standard-library/basic-streambuf-class.md#pubsetbuf) `()` yöntemi. Bu davranış gösteren bir örnek görmek için aşağıya bakın.

Sınıfın bir nesnesi `basic_filebuf` <  `Elem`, `Tr`> atayan bir dosya işaretçisini depolar `FILE` açık bir dosyayla ilişkili akışı denetimleri nesne. Ayrıca korumalı üye işlevleri tarafından kullanım için iki dosya dönüştürme modelleri işaretçiler depolar [taşma](#overflow) ve [underflow](#underflow). Daha fazla bilgi için bkz: [basic_filebuf::open](#open).

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
|[int_type](#int_type)|İçinde bu tür yapar `basic_filebuf`'s kapsam aynı adı türü eşdeğer `Tr` kapsam.|
|[off_type](#off_type)|İçinde bu tür yapar `basic_filebuf`'s kapsam aynı adı türü eşdeğer `Tr` kapsam.|
|[pos_type](#pos_type)|İçinde bu tür yapar `basic_filebuf`'s kapsam aynı adı türü eşdeğer `Tr` kapsam.|
|[traits_type](#traits_type)|Bir tür adıyla ilişkilendirir `Tr` şablon parametresi.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[close](#close)|Bir dosyayı kapatır.|
|[is_open](#is_open)|Bir dosyanın açık olup olmadığını gösterir.|
|[open](#open)|Bir dosyayı açar.|
|[Taşma](#overflow)|Yeni bir karakter tam arabelleğine takıldığında çağrılabilir korumalı sanal işlev.|
|[pbackfail](#pbackfail)|Korumalı sanal üye fonksiyonu geri öğenin Giriş akışı yerleştirin ve ardından (tarafından sonraki işaretçisi işaret) geçerli öğe olun dener.|
|[seekoff](#seekoff)|Korumalı sanal üye fonksiyonu geçerli konumlar denetimli akışlar için alter dener.|
|[seekpos](#seekpos)|Korumalı sanal üye fonksiyonu geçerli konumlar denetimli akışlar için alter dener.|
|[setbuf](#setbuf)|Korumalı sanal üye fonksiyonu her türetilmiş Akış Arabellek bir işlemi belirli gerçekleştirir.|
|[Değiştirme](#swap)|Bu içeriği alış verişleri `basic_filebuf` sağlanan içeriğinin `basic_filebuf` parametresi.|
|[Eşitleme](#sync)|Denetimli akışları ile ilişkili tüm dış akışları eşitlemek korumalı, sanal işlev çalışır.|
|[uflow](../standard-library/basic-streambuf-class.md#uflow)|Korumalı, geçerli öğe giriş akışından ayıklamak için sanal işlev.|
|[underflow](#underflow)|Korumalı, geçerli öğe giriş akışından ayıklamak için sanal işlev.|

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

İlk Oluşturucusu null işaretçi giriş arabelleği ve çıkış arabelleği denetleme tüm işaretçiler içinde depolar. Ayrıca bir null işaretçinin dosya işaretçisini depolar.

İkinci oluşturucu içeriğini nesnesiyle başlatır `right`, rvalue başvuru olarak işlem görür.

## <a name="char_type"></a>  basic_filebuf::char_type

Bir tür adıyla ilişkilendirir **Elem** şablon parametresi.

```cpp
typedef Elem char_type;
```

## <a name="close"></a>  basic_filebuf::Close

Bir dosyayı kapatır.

```cpp
basic_filebuf<Elem, Tr> *close();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisini null işaretçi ise üye işlevi null işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

**Kapat** çağrıları `fclose`( **fp**). Bu işlevi sıfır olmayan bir değer döndürürse, bir null işaretçinin işlevi döndürür. Aksi takdirde, döndürür **bu** dosya başarılı bir şekilde kapatıldı belirtmek için.

Akış açıldıktan sonra tüm eklemeleri oluşmuş, geniş bir akış için ya da son çağrısından sonra `streampos`, işlev çağrıları [taşma](#overflow). Ayrıca dosya dönüştürme modeli kullanarak ilk dönüştürme durumu geri yüklemek için gerekli dizisi ekler **fac** çağırmak için **fac.unshift** gerektiğinde. Her öğe **bayt** türü `char` böylece üretilen dosya işaretçisini tarafından belirlenen ilişkili akışa yazılan **fp** olarak art arda gelen çağrıları formun durumunda da `fputc`( **bayt**, **fp**). Varsa çağrısı **fac.unshift** veya herhangi başarısız yazma, işlevi başarılı olmaz.

### <a name="example"></a>Örnek

Aşağıdaki örnek iki dosya geçerli dizinde varsayar: basic_filebuf_close.txt (içeriği "test") ve iotest.txt ("ssss" içeriği'dir).

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

Bu tür basic_filebuf'ın kapsamında aynı adı türü eşdeğer yapar **Tr** kapsam.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="is_open"></a>  basic_filebuf::is_open

Bir dosyanın açık olup olmadığını gösterir.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** dosya işaretçisi null işaretçi değilse.

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

Bu tür basic_filebuf'ın kapsamında aynı adı türü eşdeğer yapar **Tr** kapsam.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="open"></a>  basic_filebuf::Open

Bir dosyayı açar.

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

`_Filename` Açılacak dosyanın adı.

`_Mode` Numaralandırmalardan biri [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

`_Prot` Koruma, eşdeğer açma varsayılan dosya `shflag` parametresinde [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisini null işaretçi ise, bir null işaretçinin işlevi döndürür. Aksi takdirde, döndürür **bu**.

### <a name="remarks"></a>Açıklamalar

Üye işlevini dosya adıyla açılır *filename*, çağırarak [fopen](../c-runtime-library/reference/fopen-wfopen.md)( *filename*, **strmode**). **strmode** gelen belirlenir **modu &**~ ( [tarih](../standard-library/ios-base-class.md#openmode) & &#124; [ikili](../standard-library/ios-base-class.md#openmode)):

- **ios_base::in** hale **"r"** (okumak için mevcut dosyasını açın).

- [ios_base::out](../standard-library/ios-base-class.md#fmtflags) veya **ios_base::out &#124; ios_base::trunc** hale **"w"** (varolan dosyasını kesmek veya yazma işlemi için oluşturun).

- **ios_base::out &#124; uygulama** hale **"a"** (tüm yazma işlemlerini ekleme için var olan dosyayı Aç).

- **ios_base::in &#124; ios_base::out** hale **"r +"** (okuma ve yazma için mevcut dosyasını açın).

- **ios_base::in &#124; ios_base::out &#124; ios_base::trunc** hale **"w +"** (varolan dosyasını kesmek veya okuma ve yazma için oluşturun).

- **ios_base::in &#124; ios_base::out &#124; ios_base::app** hale **"bir +"** (açık varolan dosyası okuma için ve tüm yazma işlemlerini ekleme için).

Varsa **modu & ios_base::binary** olan sıfır olmayan, işlevi ekler **b** için **strmode** bir metin akış yerine ikili akış açmak için. Ardından tarafından döndürülen değer depolayan `fopen` dosya işaretçisini içinde **fp**. Varsa **modu & ios_base::ate** sıfır olmayan olduğundan ve dosya işaretçisi null işaretçi, işlev çağrıları değil `fseek`( **fp**, 0, `SEEK_END`) dosya sonunda akış konumlandırmak için. Konumlandırma bu işlem başarısız olursa, işlev çağrıları [kapatmak](#close)( **fp**) ve bir null işaretçinin dosya işaretçisini depolar.

Dosya işaretçisini null işaretçi değilse, dosya dönüştürme modeli işlevi belirler: `use_facet` <  `codecvt` <  **Elem**, `char`, **traits_type::** [ state_type](../standard-library/char-traits-struct.md#state_type)>> ( [getloc](../standard-library/basic-streambuf-class.md#getloc)), tarafından kullanılmak üzere [underflow](#underflow) ve [taşma](#overflow).

Dosya işaretçisini null işaretçi ise, bir null işaretçinin işlevi döndürür. Aksi takdirde, döndürür **bu**.

### <a name="example"></a>Örnek

Bkz: [basic_filebuf::close](#close) kullanan bir örnek **açmak**.

## <a name="op_eq"></a>  basic_filebuf::operator =

Bu akış arabellek nesne içeriğini atayın. Bir kopyasını bırakmaz arkasındaki bir rvalue içeren bir taşıma atama budur.

```cpp
basic_filebuf& operator=(basic_filebuf&& right);
```

### <a name="parameters"></a>Parametreler

`right` Rvalue başvuru için bir [basic_filebuf](../standard-library/basic-filebuf-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Döndürür * bu.

### <a name="remarks"></a>Açıklamalar

Üye işleci içeriğini kullanarak nesne içeriğini değiştirir `right`, rvalue başvuru olarak işlem görür. Daha fazla bilgi için bkz: [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="overflow"></a>  basic_filebuf::Overflow

Yeni bir karakter tam arabelleğine takıldığında çağrılır.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Parametreler

`_Meta` Arabelleğe eklemek için karakter veya **traits_type::eof**.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarısız olması durumunda, döndürür **traits_type::eof**. Aksi takdirde, döndürür **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*).

### <a name="remarks"></a>Açıklamalar

Varsa _ * Meta ***! traits_type =::**[eof](../standard-library/char-traits-struct.md#eof), korumalı sanal üye fonksiyonu endeavors öğesi eklemek **ch traits_type =::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type) (\_ *Meta*) çıkış arabelleği içine. Bunu çeşitli yöntemlerle yapabilirsiniz:

- Yazma konumunu varsa, bu öğenin yazma konumunu depolamak ve çıkış arabelleği için sonraki işaretçisi Artır.

- Çıkış arabelleği için yeni veya ek depolama alanı ayırarak, yazma konumunu kullanılabilir hale getirebilirsiniz.

- Ardından çıktı arabelleğine bekleyen herhangi bir çıktı dönüştürebilirsiniz **ch**, dosya dönüştürme modeli kullanarak **fac** çağırmak için **fac.out** gerektiğinde. Her öğe `ch` türü *char* böylece üretilen dosya işaretçisini tarafından belirlenen ilişkili akışa yazılan **fp** olarak art arda gelen çağrıları formun durumunda da `fputc`( **ch**, **fp**). Herhangi bir dönüştürme veya yazma başarısız olursa, işlevi başarılı olmaz.

## <a name="pbackfail"></a>  basic_filebuf::pbackfail

Bir öğenin Giriş akışı geri koymak sonra (tarafından sonraki işaretçisi işaret) geçerli öğe olun dener.

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Parametreler

`_Meta` Arabelleğe eklemek için karakter veya **traits_type::eof**.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarısız olması durumunda, döndürür **traits_type::eof**. Aksi takdirde, döndürür **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*).

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye fonksiyonu geri öğenin giriş arabelleğe alır ve (tarafından sonraki işaretçisi işaret) geçerli öğe hale getirir. Varsa _ *Meta* **traits_type ==::**[eof](../standard-library/char-traits-struct.md#eof), geri göndermek için etkili bir şekilde akış geçerli öğe zaten bir öğedir. Aksi takdirde, bu öğenin değiştirilmiştir **ch traits_type =::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(\_ *Meta*). İşlev, çeşitli yollarla bir öğe geri koyabilirsiniz:

- Putback konumu varsa ve depolanan öğesi eşit karşılaştırır **ch**, giriş arabelleği için sonraki işaretçisi azaltma.

- İşlev yapabiliyorsanız bir `putback` getirin ve depolayan konumu, bunu yapmak, sonraki işaretçisi işaret Ayarla kullanılabilir **ch** konumda.

- İşlev Giriş akışı geri öğenin gönderebilir, bunu gibi çağırarak bunu yapabilirsiniz `ungetc` türünde bir öğe için `char`.

## <a name="pos_type"></a>  basic_filebuf::pos_type

Bu tür basic_filebuf'ın kapsamında aynı adı türü eşdeğer yapar **Tr** kapsam.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="seekoff"></a>  basic_filebuf::seekoff

Geçerli konumlar denetimli akışlar için alter dener.

```cpp
virtual pos_type seekoff(off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

`_Off` Göreli olarak için arama konumunu `_Way`.

`_Way` Uzaklık işlemleri için başlangıç noktası. Bkz: [seekdir](../standard-library/ios-base-class.md#seekdir) olası değerler için.

`_Which` İşaretçi konumunun modunu belirtir. Varsayılan konumlar yazma ve okuma değiştirmek izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir konuma veya geçersiz akış konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimli akışlar için geçerli konumlarını değiştirmek korumalı sanal üye fonksiyonu endeavors. Sınıfın bir nesnesi için [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>, bir akışı konumu türünde bir nesne tarafından temsil edilebilir `fpos_t`, bir uzaklık depolar ve herhangi bir durum bilgi gerekiyor geniş bir akış ayrıştırılamıyor. Uzaklık sıfır akış ilk öğesi belirler. (Bir nesne türü [pos_type](../standard-library/basic-streambuf-class.md#pos_type) en az bir depolar `fpos_t` nesnesi.)

Okuma ve yazma için açılmış olan bir dosya için giriş ve çıkış akışları dağıtımınızla konumlandırılır. Ekleme ve çıkarma arasında geçiş yapmak için ya da çağırmalıdır [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) veya [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos). Çağrılar `pubseekoff` (ve dolayısıyla için `seekoff`) için çeşitli sınırlamaları vardır [metin akışları](../c-runtime-library/text-and-binary-streams.md), [ikili akışlar](../c-runtime-library/text-and-binary-streams.md), ve [geniş akışlar](../c-runtime-library/byte-and-wide-streams.md).

Varsa dosya işaretçisini **fp** null işaretçi, işlev başarısız olur. Aksi takdirde çağırarak akışı konumu değiştirmek endeavors `fseek`( **fp**, `_Off`, `_Way`). Bu işlev başarılı olursa ve sonuçta elde edilen konumu **fposn** çağrılarak belirlenen `fgetpos`( **fp**, **& fposn**), işlevi başarılı olur. İşlev başarılı olursa, türünde bir değer döndürür **pos_type** içeren **fposn**. Aksi halde, bir geçersiz akış konumunu döndürür.

## <a name="seekpos"></a>  basic_filebuf::seekpos

Geçerli konumlar denetimli akışlar için alter dener.

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

`_Sp` Arama konumu.

`_Which` İşaretçi konumunun modunu belirtir. Varsayılan konumlar yazma ve okuma değiştirmek izin vermektir.

### <a name="return-value"></a>Dönüş Değeri

Varsa dosya işaretçisini **fp** null işaretçi, işlev başarısız olur. Aksi takdirde çağırarak akışı konumu değiştirmek endeavors `fsetpos`( **fp**, **& fposn**), burada **fposn** olan `fpos_t` içindedepolanannesnesi`pos`. Bu işlev başarılı olursa, işlevi döndürür `pos`. Aksi halde, bir geçersiz akış konumunu döndürür. Akışı konumu geçersiz olup olmadığını belirlemek için dönüş değeri ile karşılaştırın `pos_type(off_type(-1))`.

### <a name="remarks"></a>Açıklamalar

Denetimli akışlar için geçerli konumlarını değiştirmek korumalı sanal üye fonksiyonu endeavors. Sınıfın bir nesnesi için [basic_filebuf](../standard-library/basic-filebuf-class.md) \< **Elem**, **Tr**>, bir akışı konumu türünde bir nesne tarafından temsil edilebilir `fpos_t`, depolayan bir uzaklık ve geniş bir akış ayrıştırmak için gerekli tüm durum bilgileri. Uzaklık sıfır akış ilk öğesi belirler. (Bir nesne türü `pos_type` en az bir depolar `fpos_t` nesnesi.)

Okuma ve yazma için açılmış olan bir dosya için giriş ve çıkış akışları dağıtımınızla konumlandırılır. Ekleme ve çıkarma arasında geçiş yapmak için ya da çağırmalıdır [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) veya [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos). Çağrılar `pubseekoff` (ve dolayısıyla için `seekoff`) metin akışları, ikili akışlar ve geniş akışlar için çeşitli sınırlamaları vardır.

Akış açıldıktan sonra tüm eklemeleri oluşmuş, geniş bir akış için ya da son çağrısından sonra `streampos`, işlev çağrıları [taşma](#overflow). Ayrıca dosya dönüştürme modeli kullanarak ilk dönüştürme durumu geri yüklemek için gerekli dizisi ekler **fac** çağırmak için **fac** `.unshift` gerektiğinde. Her öğe **bayt** türü `char` böylece üretilen dosya işaretçisini tarafından belirlenen ilişkili akışa yazılan **fp** olarak art arda gelen çağrıları formun durumunda da `fputc`( **bayt**, **fp**). Varsa çağrısı **fac.unshift** veya herhangi başarısız yazma, işlevi başarılı olmaz.

## <a name="setbuf"></a>  basic_filebuf::setbuf

Her türetilmiş Akış Arabellek bir işlemi belirli gerçekleştirir.

```cpp
virtual basic_streambuf<Elem, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Parametreler

`_Buffer` Arabellek için işaretçi.

`count` Arabellek boyutu.

### <a name="return-value"></a>Dönüş Değeri

Korumalı üye işlevi sıfır dosya işaretçisini döndürür `fp` null işaretçi.

### <a name="remarks"></a>Açıklamalar

`setbuf` çağrıları `setvbuf`( **fp**, ( `char` \*) `_Buffer`, `_IOFBF`, `count` \* `sizeof` ( **Elem**)) dizi sunmak için `count` başlangıcı sırasında _ öğeleri *arabellek* akış için arabellek olarak. Bu işlevi sıfır olmayan bir değer döndürürse, bir null işaretçinin işlevi döndürür. Aksi takdirde, döndürür **bu** sinyal başarılı.

## <a name="swap"></a>  basic_filebuf::Swap

Bu içeriği alış verişleri `basic_filebuf` sağlanan içeriklerinin `basic_filebuf`.

```cpp
void swap(basic_filebuf& right);
```

### <a name="parameters"></a>Parametreler

`right` Bir `lvalue` başka bir başvuru `basic_filebuf`.

## <a name="sync"></a>  basic_filebuf::Sync

Denetimli akışları ile ilişkili tüm dış akışları eşitlemeye çalışır.

```cpp
virtual int sync();
```

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisini sıfır verir **fp** null işaretçi. Aksi takdirde, yalnızca sıfır olursa çağırır iki döndürür [taşma](#overflow) ve `fflush`( **fp**) bekleyen herhangi bir çıktı akışına temizleme içinde başarılı.

## <a name="traits_type"></a>  basic_filebuf::traits_type

Bir tür adıyla ilişkilendirir **Tr** şablon parametresi.

```cpp
typedef Tr traits_type;
```

## <a name="underflow"></a>  basic_filebuf::underflow

Geçerli öğe giriş akışından ayıklar.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Dönüş Değeri

İşlev başarısız olması durumunda, döndürür **traits_type::**[eof](../standard-library/char-traits-struct.md#eof). Aksi takdirde, döndürür **ch**, açıklamalar bölümünde açıklandığı şekilde dönüştürülmüş.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye fonksiyonu endeavors geçerli öğe ayıklamak **ch** girdisinden akış ve öğesi olarak dönmek **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)() **ch**). Bunu çeşitli yöntemlerle yapabilirsiniz:

- Okuma konumu varsa, sürdüğünü **ch** öğe okuma konumunda depolanan ve giriş arabelleği için sonraki işaretçisi ilerler.

- Bir veya daha fazla öğe türü okuyabilirsiniz `char`, art arda gelen çağrıları formun gibi tarafından `fgetc`(**fp**) ve bunları bir öğeye Dönüştür **ch** türü **Elem**çağırmak için dosya dönüştürme modeli fac kullanarak **fac.in** gerektiğinde. Herhangi bir okuma veya dönüştürme başarısız olursa, işlevi başarılı olmaz.

## <a name="see-also"></a>Ayrıca bkz.

[\<fstream >](../standard-library/fstream.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
