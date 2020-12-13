---
description: 'Hakkında daha fazla bilgi edinin: wstring_convert sınıfı'
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
ms.openlocfilehash: 53c3e311967295294d158bb0342d365d45f5e031
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187747"
---
# <a name="wstring_convert-class"></a>wstring_convert Sınıfı

Sınıf şablonu, `wstring_convert` geniş bir dize ve bir bayt dizesi arasında dönüşümler gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Codecvt, class Elem = wchar_t>
class wstring_convert
```

### <a name="parameters"></a>Parametreler

*Codecvt*\
Dönüştürme nesnesini temsil eden [yerel ayar](../standard-library/locale-class.md) modeli.

*Elem*\
Geniş karakterli öğe türü.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, sınıfının geniş dize nesneleri ve sınıfının bayt dizesi nesneleri arasındaki dönüştürmeleri denetleyen bir nesne tanımlar `std::basic_string<Elem>` `std::basic_string<char>` (olarak da bilinir `std::string` ). Sınıf şablonu, `wide_string` `byte_string` Bu iki tür için türleri ve Eşanlamlı sözcükleri tanımlar. Bir `Elem` değerler dizisi (bir `wide_string` nesnede depolanan) ve çok baytlı diziler (bir nesnede depolanan) arasında dönüştürme, `byte_string` `Codecvt<Elem, char, std::mbstate_t>` standart kod dönüştürme modelinin gereksinimlerini karşılayan sınıfının bir nesnesi tarafından gerçekleştirilir `std::codecvt<Elem, char, std::mbstate_t>` .

Bu sınıf şablonunun bir nesnesi şunları depolar:

- Hatalarda görüntülenecek bir bayt dizesi

- Hatalarda görüntülenecek geniş bir dize

- Ayrılmış dönüştürme nesnesine yönelik bir işaretçi (wbuffer_convert nesnesi yok edildiğinde serbest bırakılır)

- [State_type](#state_type) türünde bir dönüştürme durumu nesnesi

- Dönüştürme sayısı

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[wstring_convert](#wstring_convert)|Türünde bir nesne oluşturur `wstring_convert` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[byte_string](#byte_string)|Bir bayt dizesini temsil eden bir tür.|
|[wide_string](#wide_string)|Geniş bir dizeyi temsil eden bir tür.|
|[state_type](#state_type)|Dönüştürme durumunu temsil eden bir tür.|
|[int_type](#int_type)|Bir tamsayıyı temsil eden tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[from_bytes](#from_bytes)|Bir bayt dizesini geniş bir dizeye dönüştürür.|
|[to_bytes](#to_bytes)|Geniş bir dizeyi bayt dizesine dönüştürür.|
|[dönüştürdüğünüzde](#converted)|Başarılı dönüştürme sayısını döndürür.|
|[durumunda](#state)|Dönüştürmenin durumunu temsil eden bir nesne döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="wstring_convertbyte_string"></a><a name="byte_string"></a> wstring_convert:: byte_string

Bir bayt dizesini temsil eden bir tür.

```cpp
typedef std::basic_string<char> byte_string;
```

### <a name="remarks"></a>Açıklamalar

Tür için bir eş anlamlı `std::basic_string<char>` .

## <a name="wstring_convertconverted"></a><a name="converted"></a> wstring_convert:: dönüştürüldü

Başarılı dönüştürme sayısını döndürür.

```cpp
size_t converted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı dönüştürme sayısı.

### <a name="remarks"></a>Açıklamalar

Başarılı dönüştürme sayısı dönüştürme sayısı nesnesinde depolanır.

## <a name="wstring_convertfrom_bytes"></a><a name="from_bytes"></a> wstring_convert:: from_bytes

Bir bayt dizesini geniş bir dizeye dönüştürür.

```cpp
wide_string from_bytes(char Byte);
wide_string from_bytes(const char* ptr);
wide_string from_bytes(const byte_string& Bstr);
wide_string from_bytes(const char* first, const char* last);
```

### <a name="parameters"></a>Parametreler

*Bayt*\
Dönüştürülecek tek öğeli bayt dizisi.

*kaydetmeye*\
Dönüştürülecek karakterlerin C stili, null ile sonlandırılmış dizi.

*BSTR*\
Dönüştürülecek [byte_string](#byte_string) .

*adı*\
Dönüştürülecek karakter aralığındaki ilk karakter.

*soyadına*\
Dönüştürülecek karakter aralığındaki son karakter.

### <a name="return-value"></a>Dönüş Değeri

Dönüşümden kaynaklanan geniş bir dize nesnesi.

### <a name="remarks"></a>Açıklamalar

[Dönüştürme durumu](../standard-library/wstring-convert-class.md) nesnesi açık bir değer *ile oluşturulduysa,* dönüştürme başlamadan önce varsayılan değeri (ilk dönüştürme durumu) olarak ayarlanır. Aksi halde değiştirilmemiş olarak kalır.

Başarıyla dönüştürülen giriş öğelerinin sayısı dönüştürme sayısı nesnesinde depolanır. Hiçbir dönüştürme hatası oluşmazsa, üye işlevi dönüştürülen geniş dizeyi döndürür. Aksi takdirde, nesne geniş dize hata iletisi için bir başlatıcı ile oluşturulduysa, üye işlevi geniş dize hata iletisi nesnesini döndürür. Aksi takdirde, üye işlevi [range_error](../standard-library/range-error-class.md)sınıfından bir nesne oluşturur.

## <a name="wstring_convertint_type"></a><a name="int_type"></a> wstring_convert:: int_type

Bir tamsayıyı temsil eden tür.

```cpp
typedef typename wide_string::traits_type::int_type int_type;
```

### <a name="remarks"></a>Açıklamalar

Tür için bir eş anlamlı `wide_string::traits_type::int_type` .

## <a name="wstring_convertstate"></a><a name="state"></a> wstring_convert:: State

Dönüştürmenin durumunu temsil eden bir nesne döndürür.

```cpp
state_type state() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dönüştürmenin durumunu temsil eden [dönüştürme durumu](../standard-library/wstring-convert-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

## <a name="wstring_convertstate_type"></a><a name="state_type"></a> wstring_convert:: state_type

Dönüştürme durumunu temsil eden bir tür.

```cpp
typedef typename Codecvt::state_type state_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, bir dönüştürme durumunu temsil eden bir nesneyi tanımlar. Tür için bir eş anlamlı `Codecvt::state_type` .

## <a name="wstring_convertto_bytes"></a><a name="to_bytes"></a> wstring_convert:: to_bytes

Geniş bir dizeyi bayt dizesine dönüştürür.

```cpp
byte_string to_bytes(Elem Char);
byte_string to_bytes(const Elem* Wptr);
byte_string to_bytes(const wide_string& Wstr);
byte_string to_bytes(const Elem* first, const Elem* last);
```

### <a name="parameters"></a>Parametreler

*Char*\
Dönüştürülecek geniş karakter.

*Wptr*\
Dönüştürülecek olan C stili, null ile sonlandırılmış sıra `wptr` .

*Wstr*\
Dönüştürülecek [wide_string](#wide_string) .

*adı*\
Dönüştürülecek öğe aralığındaki ilk öğe.

*soyadına*\
Dönüştürülecek öğe aralığındaki son öğe.

### <a name="remarks"></a>Açıklamalar

[Dönüştürme durumu](../standard-library/wstring-convert-class.md) nesnesi açık bir değer *ile oluşturulduysa,* dönüştürme başlamadan önce varsayılan değeri (ilk dönüştürme durumu) olarak ayarlanır. Aksi halde değiştirilmemiş olarak kalır.

Başarıyla dönüştürülen giriş öğelerinin sayısı dönüştürme sayısı nesnesinde depolanır. Hiçbir dönüştürme hatası oluşmazsa, üye işlevi dönüştürülen bayt dizesini döndürür. Aksi takdirde, nesne, Byte dize hata iletisi için bir başlatıcı ile oluşturulduysa, üye işlevi Byte dize hata iletisi nesnesini döndürür. Aksi takdirde, üye işlevi [range_error](../standard-library/range-error-class.md)sınıfından bir nesne oluşturur.

## <a name="wstring_convertwide_string"></a><a name="wide_string"></a> wstring_convert:: wide_string

Geniş bir dizeyi temsil eden bir tür.

```cpp
typedef std::basic_string<Elem> wide_string;
```

### <a name="remarks"></a>Açıklamalar

Tür için bir eş anlamlı `std::basic_string<Elem>` .

## <a name="wstring_convertwstring_convert"></a><a name="wstring_convert"></a> wstring_convert:: wstring_convert

Türünde bir nesne oluşturur `wstring_convert` .

```cpp
wstring_convert(Codecvt *Pcvt = new Codecvt);
wstring_convert(Codecvt *Pcvt, state_type _State);
wstring_convert(const byte_string& _Berr, const wide_string& Werr = wide_string());
```

### <a name="parameters"></a>Parametreler

*\*Pcvt*\
`Codecvt`Dönüştürmeyi gerçekleştirmek için türü nesne.

*_State*\
Dönüştürme durumunu temsil eden [state_type](#state_type) türü nesne.

*_Berr*\
Hatalarda görüntülenecek [byte_string](#byte_string) .

*Werr*\
Hatalarda görüntülenecek [wide_string](#wide_string) .

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu [dönüştürme nesnesinde](../standard-library/wstring-convert-class.md) *Pcvt_arg* depolar
