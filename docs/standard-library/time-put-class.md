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
ms.openlocfilehash: 2c0ae501693a8abffc72a23be9c427f31bad65b6
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78867319"
---
# <a name="time_put-class"></a>time_put Sınıfı

Sınıf şablonu, zaman değerlerinin `CharType`türlerine dönüştürmelerini denetlemek için bir yerel ayar modeli olarak işlev görebilecek bir nesne tanımlar.

## <a name="syntax"></a>Sözdizimi

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

|Oluşturucu|Açıklama|
|-|-|
|[time_put](#time_put)|`time_put`türündeki nesneler için Oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir çıkış yineleyiciyi açıklayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_put](#do_put)|Zaman ve tarih bilgilerini `CharType`s dizisi olarak veren bir sanal işlev.|
|[konur](#put)|Zaman ve tarih bilgilerini `CharType`s dizisi olarak verir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="char_type"></a>time_put:: char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `CharType`şablon parametresi için bir eş anlamlı.

## <a name="do_put"></a>time_put::d o_put

Zaman ve tarih bilgilerini `CharType`s dizisi olarak veren bir sanal işlev.

```cpp
virtual iter_type do_put(
    iter_type next,
    ios_base& _Iosbase,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;
```

### <a name="parameters"></a>Parametreler

*sonraki*\
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

Sanal korumalı üye işlevi, `tm`türünde `_Pt`nesne \* depolanan zaman değerlerinden `next` başlayarak ardışık öğeleri oluşturur. İşlevi, oluşturulan çıkışın ötesinde bir öğe eklemek için sonraki yeri tanımlayarak bir yineleyici döndürür.

Çıktı, `strftime`tarafından kullanılan kuralların, bir dizi **karakter** öğesi oluşturmak için *_Pt*son bağımsız değişkeniyle oluşturulur. Her bir **char** öğesi, basit, bire bir eşleme tarafından `CharType` türünde eşdeğer bir öğeyle eşlenecek varsayılır. *_Mod* sıfır eşitse, etkin biçim "% F" olur ve burada F, *_Fmt*ile değiştirilmiştir. Aksi takdirde, etkin biçim "% MF" olur; burada, b *_mod*ile değiştirilmiştir.

### <a name="example"></a>Örnek

`do_put`çağıran [PUT](#put)örneğine bakın.

## <a name="iter_type"></a>time_put:: iter_type

Bir çıkış yineleyiciyi açıklayan tür.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `OutputIterator`şablon parametresi için bir eş anlamlı.

## <a name="put"></a>time_put::p UT

Zaman ve tarih bilgilerini `CharType`s dizisi olarak verir.

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

*sonraki*\
Saati ve tarihi temsil eden karakter dizisinin ekleneceği çıkış yineleyicisi.

*_Iosbase*\
Kullanılmıyor.

*_Fill*\
`CharType` boşluk için kullanılan karakter türü.

*_Pt*\
Çıkış zamanı ve tarih bilgileri.

*_Fmt*\
Çıkışın biçimi. Geçerli değerler için bkz. [strftime, wcsftime, _strftime_l _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

*_Mod*\
Biçim için bir değiştirici. Geçerli değerler için bkz. [strftime, wcsftime, _strftime_l _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

*ilk*\
Çıkışın biçimlendirme dizesinin başlangıcı. Geçerli değerler için bkz. [strftime, wcsftime, _strftime_l _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

*son*\
Çıkışın biçimlendirme dizesinin sonu. Geçerli değerler için bkz. [strftime, wcsftime, _strftime_l _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici, son öğeden sonraki ilk konuma ekleniyor.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi [do_put](#do_put)döndürür (`next`, `_Iosbase`, `_Fill`, `_Pt`, `_Fmt`, `_Mod`). İkinci üye işlevi, bir yüzde (%) dışında [`first`, `last`) Aralık içindeki herhangi bir öğeye \* `next` + + ' a kopyalar. Bir yüzde için, [`first`, `last`) aralığındaki bir karakter *C* tarafından, bunun yerine işlev `next` = `do_put`(`next`, `_Iosbase`, `_Fill`, `_Pt`, *C*, 0) değerlendirir ve geçmiş *C*'yi atlar. Ancak, *C* , EOQ # kümesindeki bir niteleyici karakteri ve ardından [`first`, `last`) aralığındaki bir karakter `C2`, bunun yerine işlev `next` = `do_put`(`next`, `_Iosbase`, `_Fill`, `_Pt`, `C2`, *C*) değerlendirir ve geçmiş `C2`atlar.

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

## <a name="time_put"></a>time_put:: time_put

`time_put`türündeki nesneler için Oluşturucu.

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

- \> 1: Bu değerler tanımlı değil.

Oluşturucu kendi temel nesnesini [locale:: model](../standard-library/locale-class.md#facet_class)( *_Refs*) ile başlatır.

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel ayar >](../standard-library/locale.md)\
[Time_base sınıfı](../standard-library/time-base-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
