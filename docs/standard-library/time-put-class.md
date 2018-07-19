---
title: time_put sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xloctime/std::time_put
- locale/std::time_put::char_type
- locale/std::time_put::iter_type
- locale/std::time_put::do_put
- locale/std::time_put::put
dev_langs:
- C++
helpviewer_keywords:
- std::time_put [C++]
- std::time_put [C++], char_type
- std::time_put [C++], iter_type
- std::time_put [C++], do_put
- std::time_put [C++], put
ms.assetid: df79493e-3331-48d2-97c3-ac3a745f0791
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b6c1c11a9c81123c518e3a0da3e56cc81d4cd5c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958935"
---
# <a name="timeput-class"></a>time_put Sınıfı

Şablon sınıfı türü dizilerin tarih değerlerinin denetim dönüştürme bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan `CharType`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class time_put : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType*  
 Bir program içindeki karakterleri kodlamak için kullanılan tür.

*Outputıterator*  
 Saat koyma işlevlerinin kendi çıktılarının yazılacağı yineleyici türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim içinde benzersiz bir pozitif değer depolar **kimliği.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[time_put](#time_put)|Türündeki nesneler için oluşturucu `time_put`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir çıkış yineleyiciyi açıklayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_put](#do_put)|Öğesinin bir dizisi olarak saat ve tarih bilgilerinin çıktısını alır, sanal bir işlev `CharType`s.|
|[yerleştirme](#put)|Öğesinin bir dizisi olarak saat ve tarih bilgilerinin çıktısını alır `CharType`s.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="char_type"></a>  time_put::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `CharType`.

## <a name="do_put"></a>  time_put::do_put

Öğesinin bir dizisi olarak saat ve tarih bilgilerinin çıktısını alır, sanal bir işlev `CharType`s.

```cpp
virtual iter_type do_put(
    iter_type next,
    ios_base& _Iosbase,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;
```

### <a name="parameters"></a>Parametreler

*Sonraki*  
 Çıktı yineleyicisini temsil eden saat ve tarih dizisi nerede karakter olan eklenecek.

*_Iosbase*  
 Kullanılmayan.

*_Pt*  
 Çıktı olan saat ve tarih bilgilerinin.

*_Fmt*  
 Çıkış biçimi. Bkz: [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) geçerli değerleri.

*_Mod*  
 Biçim için bir değiştirici. Bkz: [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) geçerli değerleri.

### <a name="return-value"></a>Dönüş Değeri

Eklenen son öğeden sonra ilk konumu için bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi konumunda başlayan ardışık öğeleri oluşturur `next` nesnesinde depolanan saat değerlerinin \* `_Pt`, türü `tm`. İşlevi, oluşturulan çıktı dışında bir öğe eklemek için sonraki yeri belirleme bir yineleyici döndürür.

Tarafından kullanılan aynı kuralları tarafından oluşturulan çıkış `strftime`, son bir bağımsız değişkeni ile *_Pt*, bir dizi oluşturmak için **char** dizisine öğeleri. Her örneğin **char** öğesi türünde eşdeğer bir öğe eşlemek için varsayılır `CharType` ile basit, bire bir eşleştirerek. Varsa *_Mod* sıfıra eşittir, "%F" nerede F ile değiştirilir, etkili biçimidir *_Fmt*. Aksi takdirde, etkili "nerede M ile değiştirilir % MF" biçimidir *_Mod*.

### <a name="example"></a>Örnek

Örneğin bakın [put](#put), çağıran `do_put`.

## <a name="iter_type"></a>  time_put::iter_type

Bir çıkış yineleyiciyi açıklayan tür.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `OutputIterator`.

## <a name="put"></a>  time_put::Put

Öğesinin bir dizisi olarak saat ve tarih bilgilerinin çıktısını alır `CharType`s.

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

*Sonraki*  
 Çıktı yineleyicisini temsil eden saat ve tarih dizisi nerede karakter olan eklenecek.

*_Iosbase*  
 Kullanılmayan.

*_Fill*  
 Karakter türü `CharType` aralığı için kullanılan.

*_Pt*  
 Çıktı olan saat ve tarih bilgilerinin.

*_Fmt*  
 Çıkış biçimi. Bkz: [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) geçerli değerleri.

*_Mod*  
 Biçim için bir değiştirici. Bkz: [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) geçerli değerleri.

*ilk*  
 Çıktı biçimlendirme dizesi başlangıcı. Bkz: [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) geçerli değerleri.

*Son*  
 Çıktı biçimlendirme dizesi sonu. Bkz: [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) geçerli değerleri.

### <a name="return-value"></a>Dönüş Değeri

Eklenen son öğeden sonra ilk konumu için bir yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi döndürür [do_put](#do_put)(`next`, `_Iosbase`, `_Fill`, `_Pt`, `_Fmt`, `_Mod`). İkinci üye işlevi kopyalar \* `next` ++ aralığındaki herhangi bir öğe [ `first`, `last`) dışında bir yüzde (%). Ardından bir karakter gelen bir yüzde için *C* aralığında [ `first`, `last`), bunun yerine işlevi değerlendirir `next`  =  `do_put`( `next`, `_Iosbase`, `_Fill`, `_Pt`, *C*, 0) ve geçmiş atlar *C*. Eğer, ancak *C* bir niteleyici karakter kümesinden EOQ #'ta, bir karakter `C2` aralığında [ `first`, `last`), işlevi yerine değerlendirir `next`  =  `do_put` ( `next`, `_Iosbase`, `_Fill`, `_Pt`, `C2`, *C*) ve geçmiş atlar `C2`.

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

## <a name="time_put"></a>  time_put::time_put

Türündeki nesneler için oluşturucu `time_put`.

```cpp
explicit time_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs* nesne için bellek yönetimi türünü belirtmek için kullanılan bir tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Olası değerler için *_Refs* parametresi ve bunların önemi:

- 0: nesne ömrü onu içeren yerel ayarlar tarafından yönetilir.

- 1: nesne ömrü el ile yönetilmesi gerekir.

- \> 1: Bu değerler tanımlanmadı.

Oluşturucu, temel nesnesiyle başlatır [locale::facet](../standard-library/locale-class.md#facet_class)(*_Refs*).

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel ayar >](../standard-library/locale.md)<br/>
[time_base Sınıfı](../standard-library/time-base-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
