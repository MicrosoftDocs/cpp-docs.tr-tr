---
title: wstring_convert sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c6cddc3925e3558c14ca18ee2a06de33b41efd9
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="wstringconvert-class"></a>wstring_convert Sınıfı

Şablon sınıfı `wstring_convert` geniş bir dize ve bir bayt dizesini arasında dönüştürmeler gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Codecvt, class Elem = wchar_t>
class wstring_convert
```

### <a name="parameters"></a>Parametreler

`Codecvt` [Yerel](../standard-library/locale-class.md) dönüştürme nesneyi temsil eden modeli.

`Elem` Joker karakter öğe türü.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı sınıfın geniş dize nesneleri arasında dönüştürme denetleyen bir nesneyi tanımlayan `std::basic_string<Elem>` ve sınıfın bayt dizesi nesneleri `std::basic_string<char>` (olarak da bilinen `std::string`). Şablon sınıfı türlerini tanımlar `wide_string` ve `byte_string` bu iki tür için eş anlamlı sözcükleri olarak. Bir dizi arasında dönüştürme `Elem` değerleri (depolanan bir `wide_string` nesnesi) ve çok baytlı dizilerinin (depolanan bir `byte_string` nesnesi) sınıfın bir nesnesi tarafından gerçekleştirilen `Codecvt<Elem, char, std::mbstate_t>`, standart gereksinimlerini karşılayan kod dönüştürme modeli `std::codecvt<Elem, char, std::mbstate_t>`.

Bu şablon sınıfın bir nesnesi depolar:

- Bir bayt dizesini hataları görüntülemek için

- Hataları görüntülemek için geniş bir dize

- (Wbuffer_convert nesne bozulduğunda serbest bırakılır) ayrılmış dönüştürme bir nesne için bir işaretçi

- Bir dönüştürme durumu nesne türü [state_type](#state_type)

- Bir dönüştürme sayısı

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[wstring_convert](#wstring_convert)|Türünde bir nesne oluşturur `wstring_convert`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[byte_string](#byte_string)|Bir bayt dizesini temsil eden tür.|
|[wide_string](#wide_string)|Geniş bir dizeyi temsil eden tür.|
|[state_type](#state_type)|Dönüştürme durumu temsil eden tür.|
|[int_type](#int_type)|Tamsayı temsil eden tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[from_bytes](#from_bytes)|Bir bayt dizesini geniş bir dizeye dönüştürür.|
|[to_bytes](#to_bytes)|Geniş bir dize bayt dizeye dönüştürür.|
|[Dönüştürülen](#converted)|Başarılı dönüşümleri sayısını döndürür.|
|[Durumu](#state)|Dönüştürme durumunu temsil eden bir nesne döndürür.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="byte_string"></a>  wstring_convert::byte_string

Bir bayt dizesini temsil eden tür.

```cpp
typedef std::basic_string<char> byte_string;
```

### <a name="remarks"></a>Açıklamalar

Eşanlamlısı türüdür `std::basic_string<char>`.

## <a name="converted"></a>  wstring_convert::Converted

Başarılı dönüşümleri sayısını döndürür.

```cpp
size_t converted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı dönüştürme sayısı.

### <a name="remarks"></a>Açıklamalar

Başarılı dönüştürülme sayısı dönüştürme sayısı nesnesinde depolanır.

## <a name="from_bytes"></a>  wstring_convert::from_bytes

Bir bayt dizesini geniş bir dizeye dönüştürür.

```cpp
wide_string from_bytes(char Byte);
wide_string from_bytes(const char* ptr);
wide_string from_bytes(const byte_string& Bstr);
wide_string from_bytes(const char* first, const char* last);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Byte`|Dönüştürülecek tek öğe bayt dizisi.|
|`ptr`|C null ile sonlandırılmış stili, dönüştürülecek bir karakter dizisi.|
|`Bstr`|[Byte_string](#byte_string) dönüştürülecek.|
|`first`|İlk karakter, dönüştürülecek karakter aralığı.|
|`last`|Dönüştürülecek karakter aralığı son karakter.|

### <a name="return-value"></a>Dönüş Değeri

Dönüştürme işlemi elde edilen geniş dize nesnesi.

### <a name="remarks"></a>Açıklamalar

Varsa [dönüştürme durumu](../standard-library/wstring-convert-class.md) nesne `not` açık bir değer ile oluşturulan, onu varsayılan değer (ilk dönüştürme durumu) olarak ayarlanır dönüştürme başlamadan önce. Aksi halde sol değişmez.

Başarıyla dönüştürüldü giriş öğe sayısını dönüştürme sayısı nesnesinde depolanır. Hiçbir dönüştürme hatası oluşursa, üye fonksiyonu dönüştürülen geniş dize döndürür. Aksi takdirde, nesne wide dize hata iletisi için bir başlatıcı örnekleriyle kurulduğundan, üye işlevi wide dize hata iletisi nesnesi döndürür. Aksi takdirde, üye fonksiyonu sınıfın bir nesnesi oluşturur [range_error](../standard-library/range-error-class.md).

## <a name="int_type"></a>  wstring_convert::int_type

Tamsayı temsil eden tür.

```cpp
typedef typename wide_string::traits_type::int_type int_type;
```

### <a name="remarks"></a>Açıklamalar

Eşanlamlısı türüdür `wide_string::traits_type::int_type`.

## <a name="state"></a>  wstring_convert::State

Dönüştürme durumunu temsil eden bir nesne döndürür.

```cpp
state_type state() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Dönüştürme durumu](../standard-library/wstring-convert-class.md) dönüştürme durumunu temsil eden nesne.

### <a name="remarks"></a>Açıklamalar

## <a name="state_type"></a>  wstring_convert::state_type

Dönüştürme durumu temsil eden tür.

```cpp
typedef typename Codecvt::state_type state_type;
```

### <a name="remarks"></a>Açıklamalar

Tür dönüştürme durumu temsil eden bir nesne açıklar. Eşanlamlısı türüdür `Codecvt::state_type`.

## <a name="to_bytes"></a>  wstring_convert::to_bytes

Geniş bir dize bayt dizeye dönüştürür.

```cpp
byte_string to_bytes(Elem Char);
byte_string to_bytes(const Elem* Wptr);
byte_string to_bytes(const wide_string& Wstr);
byte_string to_bytes(const Elem* first, const Elem* last);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Char`|Dönüştürülecek geniş karakter.|
|`Wptr`|C null ile sonlandırılmış stili, başlangıç dizisi `wptr`, dönüştürülecek.|
|`Wstr`|[Wide_string](#wide_string) dönüştürülecek.|
|`first`|Dönüştürülecek öğe aralığını ilk öğe.|
|`last`|Dönüştürülecek öğe aralığını son öğesi.|

### <a name="remarks"></a>Açıklamalar

Varsa [dönüştürme durumu](../standard-library/wstring-convert-class.md) nesne `not` açık bir değer ile oluşturulan, onu varsayılan değer (ilk dönüştürme durumu) olarak ayarlanır dönüştürme başlamadan önce. Aksi halde sol değişmez.

Başarıyla dönüştürüldü giriş öğe sayısını dönüştürme sayısı nesnesinde depolanır. Hiçbir dönüştürme hatası oluşursa, üye fonksiyonu dönüştürülen bayt dizesi döndürür. Aksi takdirde, nesne bayt dizesi hata iletisi için bir başlatıcı örnekleriyle kurulduğundan, üye işlevi bayt dizesi hata iletisi nesnesi döndürür. Aksi takdirde, üye fonksiyonu sınıfın bir nesnesi oluşturur [range_error](../standard-library/range-error-class.md).

## <a name="wide_string"></a>  wstring_convert::wide_string

Geniş bir dizeyi temsil eden tür.

```cpp
typedef std::basic_string<Elem> wide_string;
```

### <a name="remarks"></a>Açıklamalar

Eşanlamlısı türüdür `std::basic_string<Elem>`.

## <a name="wstring_convert"></a>  wstring_convert::wstring_convert

Türünde bir nesne oluşturur `wstring_convert`.

```cpp
wstring_convert(Codecvt *Pcvt = new Codecvt);
wstring_convert(Codecvt *Pcvt, state_type _State);
wstring_convert(const byte_string& _Berr, const wide_string& Werr = wide_string());
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`*Pcvt`|Nesne türünün `Codecvt` dönüştürme gerçekleştirmek için.|
|`_State`|Nesne türünün [state_type](#state_type) dönüştürme durumunu temsil eden.|
|`_Berr`|[Byte_string](#byte_string) hataları görüntülemek için.|
|`Werr`|[Wide_string](#wide_string) hataları görüntülemek için.|

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucusu depoları *Pcvt_arg* içinde [dönüştürme nesnesi](../standard-library/wstring-convert-class.md)
