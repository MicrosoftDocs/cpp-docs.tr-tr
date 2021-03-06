---
description: 'Daha fazla bilgi edinin: istrstream sınıfı'
title: istrstream Sınıfı
ms.date: 11/04/2016
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
helpviewer_keywords:
- istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
ms.openlocfilehash: 45e60878c63c30daca85924a9d0091e202387b55
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306657"
---
# <a name="istrstream-class"></a>istrstream Sınıfı

[Strstreambuffer](../standard-library/strstreambuf-class.md)sınıfının Akış arabelleğindeki öğelerin ve kodlanmış nesnelerin ayıklanmasını denetleyen bir nesne tanımlar.

## <a name="syntax"></a>Syntax

```cpp
class istrstream : public istream
```

## <a name="remarks"></a>Açıklamalar

Nesnesi, sınıfının bir nesnesini depolar `strstreambuf` .

> [!NOTE]
> Bu sınıf kullanım dışıdır. Bunun yerine [istringstream](../standard-library/sstream-typedefs.md#istringstream) veya [wıtringstream](../standard-library/sstream-typedefs.md#wistringstream) kullanmayı düşünün.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[istrstream](#istrstream)|Türünde bir nesne oluşturur `istrstream` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|Akışın ilişkili nesnesine bir işaretçi döndürür `strstreambuf` .|
|[üstbilgisine](#str)|Çağırır [ve](../standard-library/strstreambuf-class.md#freeze)sonra denetlenen sıranın başlangıcına bir işaretçi döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<strstream>

**Ad alanı:** std

## <a name="istrstreamistrstream"></a><a name="istrstream"></a> istrstream:: ıstrstream

Türünde bir nesne oluşturur `istrstream` .

```cpp
explicit istrstream(
    const char* ptr);

explicit istrstream(
    char* ptr);

istrstream(
    const char* ptr,
    streamsize count);

istrstream(
    char* ptr,
    int count);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Arabellek uzunluğu (*PTR*).

*kaydetmeye*\
Arabelleğin başlatıldığı içerik.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturucular [IStream](../standard-library/istream-typedefs.md#istream)(**SB**) çağırarak, `sb` [strstreamarabelleğe](../standard-library/strstreambuf-class.md)ait saklı nesne olduğu için temel sınıfı başlatır. İlk iki Oluşturucu çağırarak da başlatılıyor `sb` `strstreambuf( ( const char *) ptr, 0 )` . Bunun yerine kalan iki Oluşturucu çağrısı `strstreambuf( ( const char *) ptr, count )` .

## <a name="istrstreamrdbuf"></a><a name="rdbuf"></a> istrstream:: rdarabelleğe

Akışın ilişkili strstreamsize nesnesine bir işaretçi döndürür.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Akışın ilişkilendirildiği strstreamarabelleğe yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, bir [strstreambuffer](../standard-library/strstreambuf-class.md)işaretçisi türünde depolanan akış arabelleğinin adresini döndürür.

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için bkz. [strstreamarabelleğe::p Count](../standard-library/strstreambuf-class.md#pcount) `rdbuf` .

## <a name="istrstreamstr"></a><a name="str"></a> istrstream:: Str

Çağırır [ve](../standard-library/strstreambuf-class.md#freeze)sonra denetlenen sıranın başlangıcına bir işaretçi döndürür.

```cpp
char *str();
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen dizinin başlangıcına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf)  ->  [Str](../standard-library/strstreambuf-class.md#str)döndürür.

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için bkz. [strstream:: Str](../standard-library/strstreambuf-class.md#str) `str` .

## <a name="see-also"></a>Ayrıca bkz.

[istream](../standard-library/istream-typedefs.md#istream)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
