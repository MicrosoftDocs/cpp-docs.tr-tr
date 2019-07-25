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
ms.openlocfilehash: c73ab13d3cb2531ff3d741766bc86f8354a0be9d
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458058"
---
# <a name="ostrstream-class"></a>ostrstream Sınıfı

Öğelerin ve kodlanmış nesnelerin, [strstreambuffer](../standard-library/strstreambuf-class.md)sınıfının Akış arabelleğine eklenmesini denetleyen bir nesne tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class ostrstream : public ostream
```

## <a name="remarks"></a>Açıklamalar

Nesnesi, sınıfının `strstreambuf`bir nesnesini depolar.

> [!NOTE]
> Bu sınıf kullanım dışıdır. Bunun yerine [ostringstream](../standard-library/sstream-typedefs.md#ostringstream) veya [wostringstream](../standard-library/sstream-typedefs.md#wostringstream) kullanmayı düşünün.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[ostrstream](#ostrstream)|Türünde `ostrstream`bir nesne oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[amazsınız](#freeze)|Akış arabelleği işlemleri aracılığıyla akış arabelleğinin kullanılamamasına neden olur.|
|[pcount](#pcount)|Denetlenen diziye yazılan öğe sayısının sayısını döndürür.|
|[rdbuf](#rdbuf)|Akışın ilişkili `strstreambuf` nesnesine bir işaretçi döndürür.|
|[üstbilgisine](#str)|Çağırır [ve](../standard-library/strstreambuf-class.md#freeze)sonra denetlenen sıranın başlangıcına bir işaretçi döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<strstream >

**Ad alanı:** std

## <a name="freeze"></a>ostrstream:: Freeze

Akış arabelleği işlemleri aracılığıyla akış arabelleğinin kullanılamamasına neden olur.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Parametreler

*_Freezeit*\
Akışın dondurulmuş olmasını isteyip istemediğinizi belirten bir **bool** .

### <a name="remarks"></a>Açıklamalar

Üye işlevi, [rdarabelleğe](#rdbuf) -> [dondurma](../standard-library/strstreambuf-class.md#freeze)(_ *freezeit*) yöntemini çağırır.

### <a name="example"></a>Örnek

Tarafından kullanılan `freeze`bir örnek için bkz. [strstream:: Freeze](../standard-library/strstreambuf-class.md#freeze) .

## <a name="ostrstream"></a>ostrstream:: ostrstream

Türünde `ostrstream`bir nesne oluşturur.

```cpp
ostrstream();

ostrstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Arabellek.

*biriktirme*\
Arabelleğin bayt cinsinden boyutu.

*_Mod*\
Arabelleğin giriş ve çıkış modu. Daha fazla bilgi için bkz. [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode) .

### <a name="remarks"></a>Açıklamalar

Her iki Oluşturucu da, [strstreamarabelleğe](../standard-library/strstreambuf-class.md)sınıfının saklı nesnesi `sb` olan [ostream](../standard-library/ostream-typedefs.md#ostream)(SB) öğesini çağırarak temel sınıfı başlatır. İlk Oluşturucu çağırarak `strstreambuf`da başlatılır `sb` . İkinci Oluşturucu, temel sınıfı iki yönden birini başlatır:

- İos_base `_Mode` `count`  &  `strstreambuf``ptr` `count` **::** App = = 0 ise, biröğedizisininilköğesiveOluşturucuçağırır(,,`ptr` `ptr`).

- Aksi takdirde `ptr` , ilk öğesi tarafından `ptr`atanan bir C dizesi içeren bir Count öğeleri dizisinin ilk öğesini belirlemelidir ve Oluşturucu çağırır `strstreambuf`(`ptr`, `count`, `ptr` + `strlen`( `ptr`) ).

## <a name="pcount"></a>ostrstream::p sayısı

Denetlenen diziye yazılan öğe sayısının sayısını döndürür.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen diziye yazılan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount)döndürür.

### <a name="example"></a>Örnek

Tarafından kullanılan `pcount`bir örnek için bkz. [strstream::p Count](../standard-library/strstreambuf-class.md#pcount) .

## <a name="rdbuf"></a>ostrstream:: rdarabelleğe

Akışın ilişkili strstreamsize nesnesine bir işaretçi döndürür.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Akışın ilişkilendirildiği strstreamarabelleğe yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, türünde `pointer` depolanan akış arabelleğinin adresini [strstreambuffer](../standard-library/strstreambuf-class.md)olarak döndürür.

### <a name="example"></a>Örnek

Tarafından kullanılan `rdbuf`bir örnek için bkz. [strstreamarabelleğe::p Count](../standard-library/strstreambuf-class.md#pcount) .

## <a name="str"></a>ostrstream:: Str

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

[ostream](../standard-library/ostream-typedefs.md#ostream)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
