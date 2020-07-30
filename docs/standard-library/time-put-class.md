---
title: time_put Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_put
- locale/std::time_put::char_type
- locale/std::time_put::iter_type
- locale/std::time_put::do_put
- locale/std::time_put::put
helpviewer_keywords:
- std::time_put [C++]
- std::time_put [C++], char_type
- std::time_put [C++], iter_type
- std::time_put [C++], do_put
- std::time_put [C++], put
ms.assetid: df79493e-3331-48d2-97c3-ac3a745f0791
ms.openlocfilehash: 4f7b609493e16d3d1c0a9ab6274ed6f5bfd7b033
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212117"
---
# <a name="time_put-class"></a>time_put Sınıfı

Sınıf şablonu, zaman değerlerinin tür dizileriyle dönüştürmelerini denetlemek için bir yerel ayar modeli olarak işlev görebilecek bir nesne tanımlar `CharType` .

## <a name="syntax"></a>Söz dizimi

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class time_put : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType*\
Bir program içindeki karakterleri kodlamak için kullanılan tür.

*OutputIterator*\
Saat koyma işlevlerinin kendi çıktılarının yazılacağı yineleyici türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim, kimlik içinde benzersiz bir pozitif değer depolar **.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Description|
|-|-|
|[time_put](#time_put)|Türündeki nesneler için Oluşturucu `time_put` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Description|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir çıkış yineleyiciyi açıklayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Description|
|-|-|
|[do_put](#do_put)|Zaman ve tarih bilgilerini bir dizi olarak veren bir sanal işlev `CharType` .|
|[konur](#put)|Zaman ve tarih bilgilerini s dizisi olarak verir `CharType` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="time_putchar_type"></a><a name="char_type"></a>time_put:: char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `CharType` .

## <a name="time_putdo_put"></a><a name="do_put"></a>time_put::d o_put

Zaman ve tarih bilgilerini bir dizi olarak veren bir sanal işlev `CharType` .

```cpp
virtual iter_type do_put(
    iter_type next,
    ios_base& _Iosbase,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;
```

### <a name="parameters"></a>Parametreler

*ileri*\
Saati ve tarihi temsil eden karakter dizisinin ekleneceği çıkış yineleyicisi.

*_Iosbase*\
Kullanılmıyor.

*_Pt*\
Çıkış zamanı ve tarih bilgileri.

*_Fmt*\
Çıkışın biçimi. Geçerli değerler için bkz. [strftime, wcsftime, _strftime_l _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

*_Mod*\
Biçim için bir değiştirici. Geçerli değerler için bkz. [strftime, wcsftime, _strftime_l _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici, son öğeden sonraki ilk konuma ekleniyor.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye işlevi, `next` türünde nesnesinde depolanan zaman değerlerinden başlayarak ardışık öğeleri oluşturur \* `_Pt` `tm` . İşlevi, oluşturulan çıkışın ötesinde bir öğe eklemek için sonraki yeri tanımlayarak bir yineleyici döndürür.

Çıktı, bir `strftime` dizi öğe oluşturmak için *_Pt*son bağımsız değişkeniyle, tarafından kullanılan kurallar tarafından oluşturulur **`char`** . Bu tür her **`char`** öğe `CharType` , basit, bire bir eşleme ile türünde eşdeğer bir öğeyle eşlenecek varsayılır. *_Mod* sıfır eşitse, etkin biçim "% F" olur ve burada F, *_Fmt*ile değiştirilmiştir. Aksi takdirde, etkin biçim "% MF" olur; burada, b *_mod*ile değiştirilmiştir.

### <a name="example"></a>Örnek

Öğesini çağıran [PUT](#put)için örneğe bakın `do_put` .

## <a name="time_putiter_type"></a><a name="iter_type"></a>time_put:: iter_type

Bir çıkış yineleyiciyi açıklayan tür.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `OutputIterator` .

## <a name="time_putput"></a><a name="put"></a>time_put::p UT

Zaman ve tarih bilgilerini s dizisi olarak verir `CharType` .

```cpp
iter_type put(iter_type next,
    ios_base& _Iosbase,
    char_type _Fill,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;

iter_type put(iter_type next,
    ios_base& _Iosbase,
    char_type _Fill,
    const tm* _Pt,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*ileri*\
Saati ve tarihi temsil eden karakter dizisinin ekleneceği çıkış yineleyicisi.

*_Iosbase*\
Kullanılmıyor.

*_Fill*\
`CharType`Boşluk için kullanılan karakter türü.

*_Pt*\
Çıkış zamanı ve tarih bilgileri.

*_Fmt*\
Çıkışın biçimi. Geçerli değerler için bkz. [strftime, wcsftime, _strftime_l _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

*_Mod*\
Biçim için bir değiştirici. Geçerli değerler için bkz. [strftime, wcsftime, _strftime_l _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

*adı*\
Çıkışın biçimlendirme dizesinin başlangıcı. Geçerli değerler için bkz. [strftime, wcsftime, _strftime_l _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

*soyadına*\
Çıkışın biçimlendirme dizesinin sonu. Geçerli değerler için bkz. [strftime, wcsftime, _strftime_l _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici, son öğeden sonraki ilk konuma ekleniyor.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi [do_put](#do_put)döndürür (,,,, `next` `_Iosbase` `_Fill` `_Pt` `_Fmt` , `_Mod` ). İkinci üye işlevi, \* `next` yüzde (%) dışında [,) aralığında + + herhangi bir öğeye kopyalar `first` `last` . Bir yüzde için, [,) aralığındaki bir karakter *C* tarafından `first` `last` , işlev `next`  =  `do_put` ( `next` ,,,, `_Iosbase` `_Fill` `_Pt` *C*, 0) değerlendirir ve geçmiş *C*'yi atlar. Ancak, *C* , EOQ # kümesindeki bir niteleyici karakteri ve ardından [,) aralığındaki bir karakter ile, bu `C2` işlev (,,,, `first` `last` `next`  =  `do_put` `next` `_Iosbase` `_Fill` `_Pt` `C2` , *C*) `C2` öğesini değerlendirir ve daha sonra atlar.

### <a name="example"></a>Örnek

```cpp
// time_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc;
   basic_stringstream<char> pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   t.tm_hour = 5;
   t.tm_min = 30;
   t.tm_sec = 40;
   t.tm_year = 00;
   t.tm_mday = 4;
   t.tm_mon = 6;

   pszPutI.imbue( loc );
   char *pattern = "x: %X %x";
   use_facet <time_put <char> >
   (loc).put(basic_ostream<char>::_Iter(pszPutI.rdbuf( )),
          pszPutI, ' ', &t, pattern, pattern+strlen(pattern));

      cout << "num_put( ) = " << pszPutI.rdbuf( )->str( ) << endl;

      char strftimebuf[255];
      strftime(&strftimebuf[0], 255, pattern, &t);
      cout << "strftime( ) = " << &strftimebuf[0] << endl;
}
```

```Output
num_put( ) = x: 05:30:40 07/04/00
strftime( ) = x: 05:30:40 07/04/00
```

## <a name="time_puttime_put"></a><a name="time_put"></a>time_put:: time_put

Türündeki nesneler için Oluşturucu `time_put` .

```cpp
explicit time_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs*\
Nesnenin bellek yönetimi türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve bunların önemi şunlardır:

- 0: nesnenin ömrü, kendisini içeren yerel ayarlara göre yönetilir.

- 1: nesnenin ömrü el ile yönetilmelidir.

- \>1: Bu değerler tanımlı değil.

Oluşturucu kendi temel nesnesini [locale:: model](../standard-library/locale-class.md#facet_class)(*_Refs*) ile başlatır.

## <a name="see-also"></a>Ayrıca bkz.

[\<locale>](../standard-library/locale.md)\
[time_base sınıfı](../standard-library/time-base-class.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
