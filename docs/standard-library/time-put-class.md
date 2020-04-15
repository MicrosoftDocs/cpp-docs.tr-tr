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
ms.openlocfilehash: 10691de0a583dc7d5a66c319968d90978bf59480
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368007"
---
# <a name="time_put-class"></a>time_put Sınıfı

Sınıf şablonu, zaman değerlerinin tür `CharType`dizilerine dönüşümlerini denetlemek için yerel bir yönü olarak hizmet verebilen bir nesneyi açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class time_put : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*Chartype*\
Bir program içindeki karakterleri kodlamak için kullanılan tür.

*OutputIterator*\
Saat koyma işlevlerinin kendi çıktılarının yazılacağı yineleyici türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için ilk **girişim, kimlikte** benzersiz bir pozitif değer depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[time_put](#time_put)|Tür `time_put`nesneleri için oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir çıkış yineleyiciyi açıklayan tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[do_put](#do_put)|Zaman ve tarih bilgilerini `CharType`s dizisi olarak oluşturan sanal bir işlev.|
|[Koymak](#put)|S dizisi `CharType`olarak saat ve tarih bilgilerini çıkar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yerel>

**Ad alanı:** std

## <a name="time_putchar_type"></a><a name="char_type"></a>time_put:char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `CharType`ile eş anlamlıdır.

## <a name="time_putdo_put"></a><a name="do_put"></a>time_put::do_put

Zaman ve tarih bilgilerini `CharType`s dizisi olarak oluşturan sanal bir işlev.

```cpp
virtual iter_type do_put(
    iter_type next,
    ios_base& _Iosbase,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;
```

### <a name="parameters"></a>Parametreler

*Sonraki*\
Zamanı ve tarihi temsil eden karakter dizisinin eklendiği bir çıktı yineleyicisi.

*_Iosbase*\
Kullanılmıyor.

*_Pt*\
Saat ve tarih bilgisi çıktısı.

*_Fmt*\
Çıktının biçimi. Geçerli değerler için [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) bakın.

*_Mod*\
Biçim için bir değiştirici. Geçerli değerler için [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) bakın.

### <a name="return-value"></a>Dönüş Değeri

Son öğe takıldıktan sonra ilk konuma bir yineleyici.

### <a name="remarks"></a>Açıklamalar

`next` Sanal korumalı üye işlevi, nesnede \* `_Pt` `tm`depolanan zaman değerlerinden başlayarak sıralı elemanlar oluşturur. İşlev, oluşturulan çıktının ötesine bir öğe eklemek için bir sonraki yeri atayan bir yineleyici döndürür.

Çıktı, bir dizi **char** öğesi `strftime`oluşturmak *için, _Pt*son bir bağımsız değişkeni ile kullanılan aynı kurallar tarafından oluşturulur. Bu tür **char** öğesi basit, bire `CharType` bir eşleme ile eşdeğer bir tür öğesi için eşleme varsayılır. *_Mod* sıfıra eşitse, etkili biçim "%F"dir ve F _Fmt ile *değiştirilir.* Aksi takdirde, etkili biçim "%MF", M *_Mod*ile değiştirilir.

### <a name="example"></a>Örnek

[Koymak](#put)için örneğe bakın `do_put`, hangi çağırır .

## <a name="time_putiter_type"></a><a name="iter_type"></a>time_put:iter_type

Bir çıkış yineleyiciyi açıklayan tür.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `OutputIterator`ile eş anlamlıdır.

## <a name="time_putput"></a><a name="put"></a>time_put::put

S dizisi `CharType`olarak saat ve tarih bilgilerini çıkar.

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

*Sonraki*\
Zamanı ve tarihi temsil eden karakter dizisinin eklendiği bir çıktı yineleyicisi.

*_Iosbase*\
Kullanılmıyor.

*_Fill*\
Boşluk için `CharType` kullanılan tür karakteri.

*_Pt*\
Saat ve tarih bilgisi çıktısı.

*_Fmt*\
Çıktının biçimi. Geçerli değerler için [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) bakın.

*_Mod*\
Biçim için bir değiştirici. Geçerli değerler için [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) bakın.

*Ilk*\
Çıktı için biçimlendirme dizesinin başlangıcı. Geçerli değerler için [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) bakın.

*Son*\
Çıktı için biçimlendirme dizesinin sonu. Geçerli değerler için [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) bakın.

### <a name="return-value"></a>Dönüş Değeri

Son öğe takıldıktan sonra ilk konuma bir yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk üye işlev [do_put](#do_put)do_put`next` `_Iosbase`döndürür ( , `_Fill`, `_Pt`, , `_Fmt`, . `_Mod` İkinci üye işlev, \* `next` aralıktaki herhangi bir `first`öğeyi ++ 'ya kopyalar [ , `last`) yüzde (%) dışında. Bir yüzde için aralıkta bir karakter `first` `last` *C* takip [ , `_Iosbase`), `_Fill` `_Pt`işlev yerine değerlendirir `next`  =  `do_put`( `next`, , , *C*, 0) ve geçmiş *C*atlar . Ancak, *C* kümesi EOQ #bir niteleyici karakter ise, `C2` aralıkta `first`bir `last`karakter takip [ `next`  =  `do_put` `next`, `_Iosbase` `_Fill`), `_Pt` `C2`işlevi yerine değerlendirir ( `C2`, , , , , , *C*) ve geçmiş atlar .

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

## <a name="time_puttime_put"></a><a name="time_put"></a>time_put:time_put

Tür `time_put`nesneleri için oluşturucu.

```cpp
explicit time_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_refs*\
Nesneiçin bellek yönetimi türünü belirtmek için kullanılan eden arameger değeri.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve önemi şunlardır:

- 0: Nesnenin ömrü, onu içeren yerel nesneler tarafından yönetilir.

- 1: Nesnenin ömrü el ile yönetilmelidir.

- \>1: Bu değerler tanımlı değildir.

Kurucu, temel nesnesini yerel olarak [başlaşır::fason](../standard-library/locale-class.md#facet_class)(*_Refs).*

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel>](../standard-library/locale.md)\
[time_base Sınıfı](../standard-library/time-base-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
