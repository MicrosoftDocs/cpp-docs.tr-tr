---
title: ostrstream Sınıfı
ms.date: 11/04/2016
f1_keywords:
- strstream/std::ostrstream::freeze
- strstream/std::ostrstream::pcount
- strstream/std::ostrstream::rdbuf
- strstream/std::ostrstream::str
helpviewer_keywords:
- std::ostrstream [C++], freeze
- std::ostrstream [C++], pcount
- std::ostrstream [C++], rdbuf
- std::ostrstream [C++], str
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
ms.openlocfilehash: b52ba70607a5214a6aa28f04cdded0b19a56b2f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373540"
---
# <a name="ostrstream-class"></a>ostrstream Sınıfı

Öğelerin ve kodlanmış nesnelerin eklenmesini denetleyen bir nesneyi [açıklar.](../standard-library/strstreambuf-class.md)

## <a name="syntax"></a>Sözdizimi

```cpp
class ostrstream : public ostream
```

## <a name="remarks"></a>Açıklamalar

Nesne sınıfın `strstreambuf`bir nesnesini depolar.

> [!NOTE]
> Bu sınıf amortismana uğradı. Bunun yerine [ostringstream](../standard-library/sstream-typedefs.md#ostringstream) veya [wostringstream](../standard-library/sstream-typedefs.md#wostringstream) kullanmayı düşünün.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[ostrstream](#ostrstream)|Türünde `ostrstream`bir nesne oluşturuyor.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Dondurmak](#freeze)|Akış arabelleği akışı arabellek işlemleri nde kullanılamamasına neden olur.|
|[pcount](#pcount)|Denetlenmeye nisken diziye yazılan öğe sayısının sayısını döndürür.|
|[Rdbuf](#rdbuf)|Bir işaretçiyi akış ilişkili `strstreambuf` nesneye döndürür.|
|[Str](#str)|Çağrılar [donuyor](../standard-library/strstreambuf-class.md#freeze)ve ardından bir işaretçiyi denetitilen dizinin başına döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<strstream>

**Ad alanı:** std

## <a name="ostrstreamfreeze"></a><a name="freeze"></a>ostrstream::dondurma

Akış arabelleği akışı arabellek işlemleri nde kullanılamamasına neden olur.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Parametreler

*_Freezeit*\
Derenin dondurulmasını isteyip istemediğini gösteren **bir bool.**

### <a name="remarks"></a>Açıklamalar

Üye işlev [rdbuf](#rdbuf) -> [donma](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit)* çağırır.

### <a name="example"></a>Örnek

Bkz. [strstream::kullanan](../standard-library/strstreambuf-class.md#freeze) `freeze`bir örnek için dondurma .

## <a name="ostrstreamostrstream"></a><a name="ostrstream"></a>ostrstream::ostrstream

Türünde `ostrstream`bir nesne oluşturuyor.

```cpp
ostrstream();

ostrstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>Parametreler

*Ptr*\
Tampon.

*Sayısı*\
Baytlarda arabelleğen boyutu.

*_Mode*\
Arabelleğe giriş ve çıkış modu. Bkz. [ios_base::daha](../standard-library/ios-base-class.md#openmode) fazla bilgi için openmode.

### <a name="remarks"></a>Açıklamalar

Her iki kurucu da [ostream](../standard-library/ostream-typedefs.md#ostream)**(sb)** çağırarak `sb` taban sınıfı devreye sokarak, sınıfın [strstreambuf'unun](../standard-library/strstreambuf-class.md)depolanan nesnesi dir. İlk oluşturucu da `sb` arayarak `strstreambuf`baş harfe başlar. İkinci oluşturucu, taban sınıfını iki şekilde n içinden birini başlarar:

- `_Mode`  &  **eğer ios_base::app**== `ptr` 0 ise, bir dizi `count` öğenin ilk öğesini `strstreambuf``ptr`belirlemeli ve oluşturucu çağırır ( , `count`, . `ptr`

- Aksi `ptr` `ptr`takdirde, ilk öğe tarafından belirlenmiş bir C dizesi içeren bir sayı öğesi dizisinin ilk öğesini belirlemeniz gerekir ve oluşturucu çağırır `strstreambuf`(`ptr`, `count`, `ptr`  +  `strlen`( `ptr`) .

## <a name="ostrstreampcount"></a><a name="pcount"></a>ostrstream::p sayısı

Denetlenmeye nisken diziye yazılan öğe sayısının sayısını döndürür.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenmeyen sıraya yazılan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlev [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount)döndürür.

### <a name="example"></a>Örnek

Bkz. [strstream::pkullanan](../standard-library/strstreambuf-class.md#pcount) `pcount`bir örnek için sayım.

## <a name="ostrstreamrdbuf"></a><a name="rdbuf"></a>ostrstream::rdbuf

Bir işaretçiyi akışın ilişkili strstreambuf nesnesine döndürür.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Akışın ilişkili strstreambuf nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlev `pointer` [strstreambuf](../standard-library/strstreambuf-class.md)türünde depolanan akış arabelleği adresini döndürür.

### <a name="example"></a>Örnek

Bkz. [strstreambuf::p](../standard-library/strstreambuf-class.md#pcount) kullanan `rdbuf`bir örnek için sayım.

## <a name="ostrstreamstr"></a><a name="str"></a>ostrstream::str

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

[Ostream](../standard-library/ostream-typedefs.md#ostream)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
