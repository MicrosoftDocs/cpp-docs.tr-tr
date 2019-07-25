---
title: istrstream Sınıfı
ms.date: 11/04/2016
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
helpviewer_keywords:
- istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
ms.openlocfilehash: 59b69d3f862715840e1557a10d6087350488a3c9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448081"
---
# <a name="istrstream-class"></a>istrstream Sınıfı

[Strstreambuffer](../standard-library/strstreambuf-class.md)sınıfının Akış arabelleğindeki öğelerin ve kodlanmış nesnelerin ayıklanmasını denetleyen bir nesne tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class istrstream : public istream
```

## <a name="remarks"></a>Açıklamalar

Nesnesi, sınıfının `strstreambuf`bir nesnesini depolar.

> [!NOTE]
> Bu sınıf kullanım dışıdır. Bunun yerine [istringstream](../standard-library/sstream-typedefs.md#istringstream) veya [wıtringstream](../standard-library/sstream-typedefs.md#wistringstream) kullanmayı düşünün.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[istrstream](#istrstream)|Türünde `istrstream`bir nesne oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|Akışın ilişkili `strstreambuf` nesnesine bir işaretçi döndürür.|
|[üstbilgisine](#str)|Çağırır [ve](../standard-library/strstreambuf-class.md#freeze)sonra denetlenen sıranın başlangıcına bir işaretçi döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<strstream >

**Ad alanı:** std

## <a name="istrstream"></a>istrstream:: ıstrstream

Türünde `istrstream`bir nesne oluşturur.

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

Tüm oluşturucular [IStream](../standard-library/istream-typedefs.md#istream)(**SB** `sb` ) çağırarak, [strstreamarabelleğe](../standard-library/strstreambuf-class.md)ait saklı nesne olduğu için temel sınıfı başlatır. İlk iki Oluşturucu (( `sb` **const** `char` `strstreambuf` \*) ,0)çağırarakdabaşlatılıyor.`ptr` Bunun yerine kalan iki Oluşturucu ( `strstreambuf`( **const** `char` *) `ptr`, `count` ) çağrısı.

## <a name="rdbuf"></a>istrstream:: rdarabelleğe

Akışın ilişkili strstreamsize nesnesine bir işaretçi döndürür.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Akışın ilişkilendirildiği strstreamarabelleğe yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, bir [strstreambuffer](../standard-library/strstreambuf-class.md)işaretçisi türünde depolanan akış arabelleğinin adresini döndürür.

### <a name="example"></a>Örnek

Tarafından kullanılan `rdbuf`bir örnek için bkz. [strstreamarabelleğe::p Count](../standard-library/strstreambuf-class.md#pcount) .

## <a name="str"></a>istrstream:: Str

Çağırır [ve](../standard-library/strstreambuf-class.md#freeze)sonra denetlenen sıranın başlangıcına bir işaretçi döndürür.

```cpp
char *str();
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen dizinin başlangıcına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) -> [Str](../standard-library/strstreambuf-class.md#str)döndürür.

### <a name="example"></a>Örnek

Tarafından kullanılan `str`bir örnek için bkz. [strstream:: Str](../standard-library/strstreambuf-class.md#str) .

## <a name="see-also"></a>Ayrıca bkz.

[istream](../standard-library/istream-typedefs.md#istream)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
