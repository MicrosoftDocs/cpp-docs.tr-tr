---
title: wstring_convert Sınıfı
ms.date: 11/04/2016
f1_keywords:
- wstring/stdext::cvt::wstring_convert
- locale/std::wstring_convert::byte_string
- locale/std::wstring_convert::wide_string
- locale/std::wstring_convert::state_type
- locale/std::wstring_convert::int_type
- locale/std::wstring_convert::from_bytes
- locale/std::wstring_convert::to_bytes
- locale/std::wstring_convert::converted
- locale/std::wstring_convert::state
helpviewer_keywords:
- stdext::cvt [C++], wstring_convert
- std::wstring_convert [C++], byte_string
- std::wstring_convert [C++], wide_string
- std::wstring_convert [C++], state_type
- std::wstring_convert [C++], int_type
- std::wstring_convert [C++], from_bytes
- std::wstring_convert [C++], to_bytes
- std::wstring_convert [C++], converted
- std::wstring_convert [C++], state
ms.assetid: e34f5b65-d572-4bdc-ac69-20778712e376
ms.openlocfilehash: f09f12d9100e9faad849de608a9124f457da23df
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366361"
---
# <a name="wstring_convert-class"></a>wstring_convert Sınıfı

Sınıf şablonu, `wstring_convert` geniş bir dize ve bayt dizesi arasında dönüşümler gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Codecvt, class Elem = wchar_t>
class wstring_convert
```

### <a name="parameters"></a>Parametreler

*Codecvt*\
Dönüşüm nesnesini temsil eden [yerel](../standard-library/locale-class.md) yüz.

*Elem*\
Geniş karakteröğesi türü.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, sınıfın `std::basic_string<Elem>` geniş dize nesneleri ile sınıfın `std::basic_string<char>` bayt dize nesneleri (diğer `std::string`adıyla da bilinir) arasındaki dönüşümleri denetleyen bir nesneyi açıklar. Sınıf şablonu, bu `wide_string` `byte_string` iki tür için türleri ve eşanlamlıolarak tanımlar. `Elem` Değerler `wide_string` dizisi (bir nesnede depolanan) ve çok bayt dizileri `byte_string` (bir nesnede depolanan) `Codecvt<Elem, char, std::mbstate_t>`arasında dönüştürme, standart kod dönüştürme falı gereksinimlerini karşılayan bir sınıf nesnesi tarafından `std::codecvt<Elem, char, std::mbstate_t>`gerçekleştirilir.

Bu sınıfın bir nesnesi şablon upolar:

- Hatalarüzerinde görüntülenecek bayt dizesi

- Hatalarüzerinde görüntülenecek geniş bir dize

- Ayrılan dönüştürme nesnesi için bir işaretçi (wbuffer_convert nesnesi yok edildiğinde serbest bırakılır)

- Tür [state_type](#state_type) bir dönüşüm durumu nesnesi

- Dönüşüm sayısı

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[wstring_convert](#wstring_convert)|Türünde `wstring_convert`bir nesne oluşturuyor.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[byte_string](#byte_string)|Bayt dizesini temsil eden bir tür.|
|[wide_string](#wide_string)|Geniş bir dizeyi temsil eden bir tür.|
|[state_type](#state_type)|Dönüşüm durumunu temsil eden bir tür.|
|[Int_type](#int_type)|Tamsayıyı temsil eden bir tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[from_bytes](#from_bytes)|Bayt dizesini geniş bir dize dönüştürür.|
|[to_bytes](#to_bytes)|Geniş bir dizeyi bayt dizesine dönüştürür.|
|[Dönüştürülmüş](#converted)|Başarılı dönüşüm lerin sayısını verir.|
|[durum](#state)|Dönüştürme durumunu temsil eden bir nesne döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yerel>

**Ad alanı:** std

## <a name="wstring_convertbyte_string"></a><a name="byte_string"></a>wstring_convert:byte_string

Bayt dizesini temsil eden bir tür.

```cpp
typedef std::basic_string<char> byte_string;
```

### <a name="remarks"></a>Açıklamalar

Türü için `std::basic_string<char>`eşanlamlıdır.

## <a name="wstring_convertconverted"></a><a name="converted"></a>wstring_convert::dönüştürülmüş

Başarılı dönüşüm lerin sayısını verir.

```cpp
size_t converted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı dönüşümlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Başarılı dönüşüm sayısı dönüşüm sayısı nesnesinde depolanır.

## <a name="wstring_convertfrom_bytes"></a><a name="from_bytes"></a>wstring_convert:from_bytes

Bayt dizesini geniş bir dize dönüştürür.

```cpp
wide_string from_bytes(char Byte);
wide_string from_bytes(const char* ptr);
wide_string from_bytes(const byte_string& Bstr);
wide_string from_bytes(const char* first, const char* last);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Bayt*|Dönüştürülecek tek elemanlı bayt sırası.|
|*Ptr*|Dönüştürülecek C stili, null-sonlandırılan karakter dizisi.|
|*Bstr*|Dönüştürülecek [byte_string.](#byte_string)|
|*Ilk*|Dönüştürülecek karakter aralığındaki ilk karakter.|
|*Son*|Dönüştürülecek karakter aralığındaki son karakter.|

### <a name="return-value"></a>Dönüş Değeri

Dönüştürmeden kaynaklanan geniş bir dize nesnesi.

### <a name="remarks"></a>Açıklamalar

Dönüştürme [durumu](../standard-library/wstring-convert-class.md) nesnesi açık bir değerle *oluşturulmadıysa,* dönüştürme başlamadan önce varsayılan değerine (ilk dönüşüm durumu) ayarlanır. Aksi takdirde değişmeden bırakılır.

Başarıyla dönüştürülen giriş öğelerinin sayısı dönüşüm sayımı nesnesinde depolanır. Dönüşüm hatası oluşursa, üye işlev dönüştürülen geniş dizeyi döndürür. Aksi takdirde, nesne geniş dize hata iletisi için bir baş harfile oluşturulmuşsa, üye işlev geniş dize hata iletisi nesnesini döndürür. Aksi takdirde, üye işlev sınıf [range_error](../standard-library/range-error-class.md)bir nesne atar.

## <a name="wstring_convertint_type"></a><a name="int_type"></a>wstring_convert::int_type

Tamsayıyı temsil eden bir tür.

```cpp
typedef typename wide_string::traits_type::int_type int_type;
```

### <a name="remarks"></a>Açıklamalar

Türü için `wide_string::traits_type::int_type`eşanlamlıdır.

## <a name="wstring_convertstate"></a><a name="state"></a>wstring_convert::devlet

Dönüştürme durumunu temsil eden bir nesne döndürür.

```cpp
state_type state() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dönüştürme durumunu temsil eden [dönüşüm durumu](../standard-library/wstring-convert-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

## <a name="wstring_convertstate_type"></a><a name="state_type"></a>wstring_convert:state_type

Dönüşüm durumunu temsil eden bir tür.

```cpp
typedef typename Codecvt::state_type state_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, dönüşüm durumunu temsil eden bir nesneyi açıklar. Türü için `Codecvt::state_type`eşanlamlıdır.

## <a name="wstring_convertto_bytes"></a><a name="to_bytes"></a>wstring_convert:to_bytes

Geniş bir dizeyi bayt dizesine dönüştürür.

```cpp
byte_string to_bytes(Elem Char);
byte_string to_bytes(const Elem* Wptr);
byte_string to_bytes(const wide_string& Wstr);
byte_string to_bytes(const Elem* first, const Elem* last);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Char*|Dönüştürülecek geniş karakter.|
|*Wptr*|C stili, null-terminated sırası, `wptr`başlayarak , dönüştürülecek.|
|*Wstr*|Dönüştürülecek [wide_string.](#wide_string)|
|*Ilk*|Dönüştürülecek bir dizi öğedeki ilk öğe.|
|*Son*|Dönüştürülecek bir dizi öğedeki son öğe.|

### <a name="remarks"></a>Açıklamalar

Dönüştürme [durumu](../standard-library/wstring-convert-class.md) nesnesi açık bir değerle *oluşturulmadıysa,* dönüştürme başlamadan önce varsayılan değerine (ilk dönüşüm durumu) ayarlanır. Aksi takdirde değişmeden bırakılır.

Başarıyla dönüştürülen giriş öğelerinin sayısı dönüşüm sayımı nesnesinde depolanır. Dönüşüm hatası oluşursa, üye işlev dönüştürülen bayt dizesini döndürür. Aksi takdirde, nesne bayt dize hata iletisi için bir baş harfile oluşturulmuşsa, üye işlev bayt dizesi hata iletisi nesnesini döndürür. Aksi takdirde, üye işlev sınıf [range_error](../standard-library/range-error-class.md)bir nesne atar.

## <a name="wstring_convertwide_string"></a><a name="wide_string"></a>wstring_convert::wide_string

Geniş bir dizeyi temsil eden bir tür.

```cpp
typedef std::basic_string<Elem> wide_string;
```

### <a name="remarks"></a>Açıklamalar

Türü için `std::basic_string<Elem>`eşanlamlıdır.

## <a name="wstring_convertwstring_convert"></a><a name="wstring_convert"></a>wstring_convert:wstring_convert

Türünde `wstring_convert`bir nesne oluşturuyor.

```cpp
wstring_convert(Codecvt *Pcvt = new Codecvt);
wstring_convert(Codecvt *Pcvt, state_type _State);
wstring_convert(const byte_string& _Berr, const wide_string& Werr = wide_string());
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*\*Pcvt*|Dönüştürme gerçekleştirmek `Codecvt` için tür nesnesi.|
|*_state*|Dönüştürme durumunu temsil eden tür [state_type](#state_type) nesnesi.|
|*_Berr*|Hataları görüntülemek için [byte_string.](#byte_string)|
|*Werr*|Hataları görüntülemek için [wide_string.](#wide_string)|

### <a name="remarks"></a>Açıklamalar

İlk *oluşturucu, dönüşüm* [nesnesinde](../standard-library/wstring-convert-class.md) Pcvt_arg depolar
