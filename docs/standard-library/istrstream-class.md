---
title: istrstream Sınıfı
ms.date: 11/04/2016
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
helpviewer_keywords:
- istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
ms.openlocfilehash: d548a8c2c47a5a345be725afdedb47524344f720
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337520"
---
# <a name="istrstream-class"></a>istrstream Sınıfı

[Strstreambuf](../standard-library/strstreambuf-class.md)sınıfının bir akış arabelleği öğeleri ve kodlanmış nesnelerin ayıklama denetimi bir nesne açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class istrstream : public istream
```

## <a name="remarks"></a>Açıklamalar

Nesne sınıfın `strstreambuf`bir nesnesini depolar.

> [!NOTE]
> Bu sınıf amortismana uğradı. Bunun yerine [istringstream](../standard-library/sstream-typedefs.md#istringstream) veya [wistringstream](../standard-library/sstream-typedefs.md#wistringstream) kullanmayı düşünün.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[istrstream](#istrstream)|Türünde `istrstream`bir nesne oluşturuyor.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Rdbuf](#rdbuf)|Bir işaretçiyi akış ilişkili `strstreambuf` nesneye döndürür.|
|[Str](#str)|Çağrılar [donuyor](../standard-library/strstreambuf-class.md#freeze)ve ardından bir işaretçiyi denetitilen dizinin başına döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<strstream>

**Ad alanı:** std

## <a name="istrstreamistrstream"></a><a name="istrstream"></a>istrstream::istrstream

Türünde `istrstream`bir nesne oluşturuyor.

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

*Sayısı*\
Arabelleğe in uzunluğu (*ptr*).

*Ptr*\
Arabellek ile başharfe sahip içeriği.

### <a name="remarks"></a>Açıklamalar

Tüm yapıcılar [istream](../standard-library/istream-typedefs.md#istream)**(sb)** çağırarak taban sınıf `sb` ı sinifa, sınıfın [strstreambuf](../standard-library/strstreambuf-class.md)depolanan nesnesi nerede. İlk iki yapıcı da arayarak `strstreambuf`(( **const** `char` \*) `ptr`, 0 ) olarak adlandırır. `sb` Geri kalan iki yapıcı `strstreambuf`yerine çağrı ( `ptr`( `count` **const** `char` *) , ).

## <a name="istrstreamrdbuf"></a><a name="rdbuf"></a>istrstream::rdbuf

Bir işaretçiyi akışın ilişkili strstreambuf nesnesine döndürür.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Akışın ilişkili strstreambuf nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlev, [strstreambuf](../standard-library/strstreambuf-class.md)türü işaretçisi depolanan akış arabelleği adresini döndürür.

### <a name="example"></a>Örnek

Bkz. [strstreambuf::p](../standard-library/strstreambuf-class.md#pcount) kullanan `rdbuf`bir örnek için sayım.

## <a name="istrstreamstr"></a><a name="str"></a>istrstream::str

Çağrılar [donuyor](../standard-library/strstreambuf-class.md#freeze)ve ardından bir işaretçiyi denetitilen dizinin başına döndürür.

```cpp
char *str();
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen dizinin başına bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlev [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str)döndürür.

### <a name="example"></a>Örnek

Bkz. [strstream::str](../standard-library/strstreambuf-class.md#str) kullanan `str`bir örnek için .

## <a name="see-also"></a>Ayrıca bkz.

[ıstream](../standard-library/istream-typedefs.md#istream)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
