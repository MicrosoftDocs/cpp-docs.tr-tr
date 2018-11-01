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
ms.openlocfilehash: df3b003289dcd86e8033521d8cb0cacdbb7dfbd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636962"
---
# <a name="wstringconvert-class"></a>wstring_convert Sınıfı

Şablon sınıfı `wstring_convert` bir bayt dizesini bir geniş dize arasındaki dönüştürmeleri gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Codecvt, class Elem = wchar_t>
class wstring_convert
```

### <a name="parameters"></a>Parametreler

*codecvt*<br/>
[Yerel ayar](../standard-library/locale-class.md) dönüştürme nesneyi temsil eden bir model.

*Elem*<br/>
Geniş karakter öğe türü.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı sınıfın geniş dize nesneleri arasında dönüştürmeler denetleyen bir nesneyi tanımlayan `std::basic_string<Elem>` ve sınıfın bayt dizesi nesneleri `std::basic_string<char>` (olarak da bilinen `std::string`). Şablon sınıfı türlerini tanımlar `wide_string` ve `byte_string` bu iki tür için eş anlamlı sözcükler olarak. Arasında bir dizi dönüştürme `Elem` değerleri (depolanan bir `wide_string` nesne) ve çok baytlı dizilerini (depolanan bir `byte_string` nesne) sınıfın bir nesnesi tarafından gerçekleştirilen `Codecvt<Elem, char, std::mbstate_t>`, standart gereksinimlerini karşılar dönüştürme kodu modeli `std::codecvt<Elem, char, std::mbstate_t>`.

Bu şablon sınıfının bir nesnesi depolar:

- Bir bayt dizesini hataları görüntülemek için

- Hataları görüntülemek için bir geniş dize

- (Wbuffer_convert nesnesi yok edildiğinde serbest bırakılır) ayrılmış dönüştürme nesneye bir işaretçi

- Tür dönüştürme durum nesnesi [state_type](#state_type)

- Bir dönüştürme sayısı

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[wstring_convert](#wstring_convert)|Türünde bir nesne oluşturur `wstring_convert`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[byte_string](#byte_string)|Bir bayt dizesini temsil eden tür.|
|[wide_string](#wide_string)|Bir geniş dize temsil eden tür.|
|[state_type](#state_type)|Dönüştürme durumunu temsil eden tür.|
|[int_type](#int_type)|Bir tamsayı temsil eden tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[from_bytes](#from_bytes)|Bir bayt dizesini geniş dizeye dönüştürür.|
|[to_bytes](#to_bytes)|Bir geniş dize bir bayt dizeye dönüştürür.|
|[Dönüştürülen](#converted)|Başarılı dönüştürmeler sayısını döndürür.|
|[durumu](#state)|Dönüştürme durumunu temsil eden bir nesne döndürür.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="byte_string"></a>  wstring_convert::byte_string

Bir bayt dizesini temsil eden tür.

```cpp
typedef std::basic_string<char> byte_string;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `std::basic_string<char>`.

## <a name="converted"></a>  wstring_convert::Converted

Başarılı dönüştürmeler sayısını döndürür.

```cpp
size_t converted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı dönüştürme sayısı.

### <a name="remarks"></a>Açıklamalar

Başarılı dönüştürme sayısı dönüştürme sayısı nesnesinde depolanır.

## <a name="from_bytes"></a>  wstring_convert::from_bytes

Bir bayt dizesini geniş dizeye dönüştürür.

```cpp
wide_string from_bytes(char Byte);
wide_string from_bytes(const char* ptr);
wide_string from_bytes(const byte_string& Bstr);
wide_string from_bytes(const char* first, const char* last);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Bayt*|Dönüştürülecek tek öğe bayt dizisi.|
|*ptr*|C null ile sonlandırılmış stili, dönüştürülecek karakter dizisi.|
|*BSTR*|[Byte_string](#byte_string) dönüştürülecek.|
|*ilk*|Dönüştürülecek karakter, bir aralıktaki ilk karakteri.|
|*Son*|Dönüştürülecek karakter aralığı son karakter.|

### <a name="return-value"></a>Dönüş Değeri

Dönüştürme kaynaklanan bir geniş dize nesnesi.

### <a name="remarks"></a>Açıklamalar

Varsa [dönüştürme durumu](../standard-library/wstring-convert-class.md) nesne *değil* açık bir değer ile oluşturulmuş, (ilk dönüştürme durumunu) varsayılan değerine ayarlanır dönüştürme başlamadan önce. Aksi halde sol değişmez.

Başarıyla dönüştürülen giriş öğe sayısı dönüştürme sayısı nesnesinde depolanır. Hiçbir dönüştürme hatası meydana gelirse, üye işlev dönüştürülmüş geniş dize döndürür. Aksi takdirde geniş dize hata iletisi için Başlatıcı ile nesne oluşturulmuşsa, üye işlevi geniş dize hata iletisi nesnesi döndürür. Aksi takdirde, üye işlevi sınıfın bir nesnesi atar [range_error](../standard-library/range-error-class.md).

## <a name="int_type"></a>  wstring_convert::int_type

Bir tamsayı temsil eden tür.

```cpp
typedef typename wide_string::traits_type::int_type int_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `wide_string::traits_type::int_type`.

## <a name="state"></a>  wstring_convert::State

Dönüştürme durumunu temsil eden bir nesne döndürür.

```cpp
state_type state() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Dönüştürme durumu](../standard-library/wstring-convert-class.md) dönüştürme durumunu temsil eden nesne.

### <a name="remarks"></a>Açıklamalar

## <a name="state_type"></a>  wstring_convert::state_type

Dönüştürme durumunu temsil eden tür.

```cpp
typedef typename Codecvt::state_type state_type;
```

### <a name="remarks"></a>Açıklamalar

Dönüştürme durumunu temsil edebilen bir nesneyi tanımlayan bir tür. Türü eşanlamlıdır `Codecvt::state_type`.

## <a name="to_bytes"></a>  wstring_convert::to_bytes

Bir geniş dize bir bayt dizeye dönüştürür.

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
|*Wptr*|C null ile sonlandırılmış stili, başlangıç dizisi, `wptr`, dönüştürülecek.|
|*WSTR*|[Wide_string](#wide_string) dönüştürülecek.|
|*ilk*|Dönüştürülecek öğelerin bir aralıktaki ilk öğeyi.|
|*Son*|Dönüştürülecek öğelerin bir aralığını içerisindeki son öğe.|

### <a name="remarks"></a>Açıklamalar

Varsa [dönüştürme durumu](../standard-library/wstring-convert-class.md) nesne *değil* açık bir değer ile oluşturulmuş, (ilk dönüştürme durumunu) varsayılan değerine ayarlanır dönüştürme başlamadan önce. Aksi halde sol değişmez.

Başarıyla dönüştürülen giriş öğe sayısı dönüştürme sayısı nesnesinde depolanır. Hiçbir dönüştürme hatası meydana gelirse, üye işlevi dönüştürülmüş byte dizeyi döndürür. Aksi takdirde, nesne Başlatıcı bayt dizesinden hata iletisi ile oluşturulmuşsa, üye işlevi bayt dizesinden hata iletisi nesnesi döndürür. Aksi takdirde, üye işlevi sınıfın bir nesnesi atar [range_error](../standard-library/range-error-class.md).

## <a name="wide_string"></a>  wstring_convert::wide_string

Bir geniş dize temsil eden tür.

```cpp
typedef std::basic_string<Elem> wide_string;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `std::basic_string<Elem>`.

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
|*\*Pcvt*|Nesne türü `Codecvt` dönüştürme gerçekleştirmek için.|
|*Duru_m*|Nesne türü [state_type](#state_type) dönüştürme durumunu temsil eden.|
|*_Berr*|[Byte_string](#byte_string) hataları görüntülemek için.|
|*Werr*|[Wide_string](#wide_string) hataları görüntülemek için.|

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu depoları *Pcvt_arg* içinde [dönüştürme nesnesi](../standard-library/wstring-convert-class.md)
