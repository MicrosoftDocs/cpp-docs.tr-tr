---
title: strstream Sınıfı
ms.date: 11/04/2016
f1_keywords:
- strstream/std::strstream::freeze
- strstream/std::strstream::pcount
- strstream/std::strstream::rdbuf
- strstream/std::strstream::str
helpviewer_keywords:
- std::strstream [C++], freeze
- std::strstream [C++], pcount
- std::strstream [C++], rdbuf
- std::strstream [C++], str
ms.assetid: 63f3be31-9e36-42b1-9715-a474a5997e2a
ms.openlocfilehash: 047b7e9d7fdece75137980b013d43abf1d5e3ec3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376626"
---
# <a name="strstream-class"></a>strstream Sınıfı

Sınıf [strstreambuf](../standard-library/strstreambuf-class.md)bir akış arabelleği kullanarak öğeleri ve kodlanmış nesnelerin ekleme ve ayıklama kontrol eden bir nesne açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class strstream : public iostream
```

## <a name="remarks"></a>Açıklamalar

Nesne sınıfın `strstreambuf`bir nesnesini depolar.

> [!NOTE]
> Bu sınıf amortismana uğradı. Bunun yerine [stringstream](../standard-library/sstream-typedefs.md#stringstream) veya [wstringstream](../standard-library/sstream-typedefs.md#wstringstream) kullanmayı düşünün.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[strstream](#strstream)|Türünde `strstream`bir nesne oluşturuyor.|

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

## <a name="strstreamfreeze"></a><a name="freeze"></a>strstream::dondurma

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

Bkz. [strstreambuf::kullanan](../standard-library/strstreambuf-class.md#freeze) `freeze`bir örnek için dondurma .

## <a name="strstreampcount"></a><a name="pcount"></a>strstream::p sayısı

Denetlenmeye nisken diziye yazılan öğe sayısının sayısını döndürür.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenmeyen sıraya yazılan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlev [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount)döndürür.

### <a name="example"></a>Örnek

Bkz. [strstreambuf::ppcount](../standard-library/strstreambuf-class.md#pcount) kullanarak bir örnek için saymak.

## <a name="strstreamrdbuf"></a><a name="rdbuf"></a>strstream::rdbuf

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

## <a name="strstreamstr"></a><a name="str"></a>strstream::str

Çağrılar [donuyor](../standard-library/strstreambuf-class.md#freeze)ve ardından bir işaretçiyi denetitilen dizinin başına döndürür.

```cpp
char *str();
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen dizinin başına bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlev [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str)döndürür.

### <a name="example"></a>Örnek

Bkz. [strstreambuf::str](../standard-library/strstreambuf-class.md#str) kullanan `str`bir örnek için .

## <a name="strstreamstrstream"></a><a name="strstream"></a>strstream::strstream

Türünde `strstream`bir nesne oluşturuyor.

```cpp
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*Sayısı*\
Arabelleğe in boyutu.

*_Mode*\
Arabelleğe giriş ve çıkış modu. Bkz. [ios_base::daha](../standard-library/ios-base-class.md#openmode) fazla bilgi için openmode.

*Ptr*\
Tampon.

### <a name="remarks"></a>Açıklamalar

Her iki kurucu da [streambuf](../standard-library/streambuf-typedefs.md#streambuf)( **sb)** çağırarak taban sınıfı devreye sokmak , sınıf `sb` [strstreambuf](../standard-library/strstreambuf-class.md)depolanan nesne nerede . İlk yapıcı da `sb` [strstreambuf](../standard-library/strstreambuf-class.md#strstreambuf)çağırarak başlar. İkinci oluşturucu, taban sınıfını iki şekilde n içinden birini başlarar:

- `_Mode`  &  **eğer ios_base::app**== 0 ise, *ptr* `count` bir dizi öğenin ilk öğesini belirlemeli ve oluşturucu çağırır `strstreambuf`( `ptr`, `count`, . `ptr`

- Aksi takdirde, *ptr* ilk *öğeptr*tarafından belirlenmiş bir C dizeiçeren sayım elemanları dizisinin ilk `strstreambuf` `ptr`öğesini belirlemeli ve oluşturucu çağırır `count`( , , `ptr`  +  `strlen`( `ptr`) .

## <a name="see-also"></a>Ayrıca bkz.

[Iostream](../standard-library/istream-typedefs.md#iostream)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
