---
title: time_put sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5eb3e868280b254a8f7583a4fa5408710f604005
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="timeput-class"></a>time_put Sınıfı

Saat değerleri denetim dönüşümleri dizilerini türü için bir yerel ayar model olarak hizmet verebilir bir nesne şablonu sınıf tanımlar `CharType`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class time_put : public locale::facet;
```

### <a name="parameters"></a>Parametreler

`CharType` Bir program içinden karakterlerin kodlanması için kullanılan türü.

`OutputIterator` Yineleyici içine saat işlevleri koyun türünü çıktılarını yazma.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Benzersiz bir pozitif değer saklı değerini erişmek için ilk deneme depolar **kimliği.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[time_put](#time_put)|Nesne türü Oluşturucusu `time_put`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir çıkış yineleyiciyi açıklayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_put](#do_put)|Bir dizi olarak saat ve tarih bilgilerini çıkarır sanal bir işlev `CharType`s.|
|[PUT](#put)|Bir dizi olarak saat ve tarih bilgilerini çıkarır `CharType`s.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="char_type"></a>  time_put::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür **CharType**.

## <a name="do_put"></a>  time_put::do_put

Bir dizi olarak saat ve tarih bilgilerini çıkarır sanal bir işlev **CharType**s.

```cpp
virtual iter_type do_put(
    iter_type next,
    ios_base& _Iosbase,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;
```

### <a name="parameters"></a>Parametreler

`next` Çıktı yineleyici burada dizisini temsil eden saat ve tarih karakter olan eklenecek.

`_Iosbase` Kullanılmayan.

`_Pt` Çıkış olan saat ve tarih bilgileri.

`_Fmt` Çıktı biçimi. Bkz: [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) yönelik geçerli değerler.

`_Mod` Biçim için değiştiricisi. Bkz: [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) yönelik geçerli değerler.

### <a name="return-value"></a>Dönüş Değeri

Yineleyici eklenen son öğesinden sonra ilk konumuna.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye fonksiyonu başlangıç sıralı öğeleri oluşturur `next` nesnesinde depolanan zaman değerlerinden \* `_Pt`, türü **tm**. Oluşturulan çıktı dışında bir öğe eklemek için sonraki yer belirleme yineleyici işlevi döndürür.

Çıktı tarafından kullanılan aynı kurallar tarafından oluşturulan `strftime`, bir son bağımsız değişkeni ile `_Pt`, bir dizi oluşturmak için `char` bir dizi elemanlara. Her gibi `char` öğe türü eşdeğer bir öğeye eşlemek için varsayılır **CharType** basit, bire bir eşleme tarafından. Varsa `_Mod` eşittir sıfır, "%F" nerede F ile değiştirilir, etkili biçimidir `_Fmt`. Aksi takdirde, etkili "Burada M ile değiştirilir % MF" biçimidir `_Mod`.

### <a name="example"></a>Örnek

Örneğin bkz [put](#put), çağıran `do_put`.

## <a name="iter_type"></a>  time_put::iter_type

Bir çıkış yineleyiciyi açıklayan tür.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür **OutputIterator**.

## <a name="put"></a>  time_put::Put

Bir dizi olarak saat ve tarih bilgilerini çıkarır **CharType**s.

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

`next` Çıktı yineleyici burada dizisini temsil eden saat ve tarih karakter olan eklenecek.

`_Iosbase` Kullanılmayan.

`_Fill` Karakter türü **CharType** aralığı için kullanılan.

`_Pt` Çıkış olan saat ve tarih bilgileri.

`_Fmt` Çıktı biçimi. Bkz: [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) yönelik geçerli değerler.

`_Mod` Biçim için değiştiricisi. Bkz: [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) yönelik geçerli değerler.

`first` Biçimlendirme dizesi çıktısı için başlangıcı. Bkz: [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) yönelik geçerli değerler.

`last` Çıkış için biçimlendirme dize sonu. Bkz: [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) yönelik geçerli değerler.

### <a name="return-value"></a>Dönüş Değeri

Yineleyici eklenen son öğesinden sonra ilk konumuna.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevinin döndürdüğü [do_put](#do_put)( `next`, `_Iosbase`, `_Fill`, `_Pt`, `_Fmt`, `_Mod`). İkinci üye işlevi kopyalar \* `next` ++ aralığında herhangi bir öğe [ `first`, `last`) dışında bir yüzde (%). Bir karakterin ardından yüzde için *C* aralığında [ `first`, `last`), bunun yerine işlevi değerlendirir `next`  =  `do_put`( `next`, `_Iosbase`, `_Fill`, `_Pt`, *C*, 0) ve geçmiş atlar *C*. Eğer, ancak *C* niteleyicisi karakter kümesinden EOQ #'ta, bir karakterin ardından `C2` aralığında [ `first`, `last`), işlevi yerine değerlendirir `next`  =  `do_put` ( `next`, `_Iosbase`, `_Fill`, `_Pt`, `C2`, *C*) ve geçmiş atlar `C2`.

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

Nesne türü için oluşturucu `time_put`.

```cpp
explicit time_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

`_Refs` Bellek yönetimi nesnesinin türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Olası değerler için `_Refs` parametre ve bunların anlamlı:

- 0: nesne ömrü onu içeren yerel ayarları tarafından yönetilir.

- 1: nesne ömrü el ile yönetilmesi gerekir.

- \> 1: Bu değerleri tanımlanmamış.

Oluşturucu temel nesnesiyle başlatır [locale::facet](../standard-library/locale-class.md#facet_class)(*_Refs*).

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel ayar >](../standard-library/locale.md)<br/>
[time_base Sınıfı](../standard-library/time-base-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
