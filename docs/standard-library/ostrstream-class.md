---
description: 'Daha fazla bilgi edinin: ostrstream sınıfı'
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
ms.openlocfilehash: 9966f044d48aa762d681bafcfc22441f7124c9a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305149"
---
# <a name="ostrstream-class"></a>ostrstream Sınıfı

Öğelerin ve kodlanmış nesnelerin, [strstreambuffer](../standard-library/strstreambuf-class.md)sınıfının Akış arabelleğine eklenmesini denetleyen bir nesne tanımlar.

## <a name="syntax"></a>Syntax

```cpp
class ostrstream : public ostream
```

## <a name="remarks"></a>Açıklamalar

Nesnesi, sınıfının bir nesnesini depolar `strstreambuf` .

> [!NOTE]
> Bu sınıf kullanım dışıdır. Bunun yerine [ostringstream](../standard-library/sstream-typedefs.md#ostringstream) veya [wostringstream](../standard-library/sstream-typedefs.md#wostringstream) kullanmayı düşünün.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[ostrstream](#ostrstream)|Türünde bir nesne oluşturur `ostrstream` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[amazsınız](#freeze)|Akış arabelleği işlemleri aracılığıyla akış arabelleğinin kullanılamamasına neden olur.|
|[pcount](#pcount)|Denetlenen diziye yazılan öğe sayısının sayısını döndürür.|
|[rdbuf](#rdbuf)|Akışın ilişkili nesnesine bir işaretçi döndürür `strstreambuf` .|
|[üstbilgisine](#str)|Çağırır [ve](../standard-library/strstreambuf-class.md#freeze)sonra denetlenen sıranın başlangıcına bir işaretçi döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<strstream>

**Ad alanı:** std

## <a name="ostrstreamfreeze"></a><a name="freeze"></a> ostrstream:: Freeze

Akış arabelleği işlemleri aracılığıyla akış arabelleğinin kullanılamamasına neden olur.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Parametreler

*_Freezeit*\
**`bool`** Akışın dondurulmuş olmasını isteyip istemediğinizi belirten bir.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, [rdarabelleğe](#rdbuf)  ->  [dondurma](../standard-library/strstreambuf-class.md#freeze)(_ *freezeit*) yöntemini çağırır.

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için bkz. [strstream:: Freeze](../standard-library/strstreambuf-class.md#freeze) `freeze` .

## <a name="ostrstreamostrstream"></a><a name="ostrstream"></a> ostrstream:: ostrstream

Türünde bir nesne oluşturur `ostrstream` .

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

*_Mode*\
Arabelleğin giriş ve çıkış modu. Daha fazla bilgi için bkz. [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode) .

### <a name="remarks"></a>Açıklamalar

Her iki Oluşturucu da,strstreamarabelleğe sınıfının saklı nesnesi olan [ostream](../standard-library/ostream-typedefs.md#ostream)(SB) öğesini çağırarak temel sınıfı başlatır `sb` . [](../standard-library/strstreambuf-class.md) İlk Oluşturucu çağırarak da başlatılır `sb` `strstreambuf` . İkinci Oluşturucu, temel sınıfı iki yönden birini başlatır:

- `_Mode`  &  **İos_base:: App**= = 0 ise, `ptr` bir öğe dizisinin ilk öğesini `count` ve Oluşturucu çağrılarını `strstreambuf` ( `ptr` , `count` , `ptr` ) belirlemelidir.

- Aksi takdirde, `ptr` ilk öğesi tarafından atanan bir C dizesi içeren bir Count öğeleri dizisinin ilk öğesi `ptr` ve Oluşturucu `strstreambuf` ( `ptr` , `count` , `ptr`  +  `strlen` ( `ptr` )) çağırır.

## <a name="ostrstreampcount"></a><a name="pcount"></a> ostrstream::p sayısı

Denetlenen diziye yazılan öğe sayısının sayısını döndürür.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen diziye yazılan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf)  ->  [pcount](../standard-library/strstreambuf-class.md#pcount)döndürür.

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için bkz. [strstream::p Count](../standard-library/strstreambuf-class.md#pcount) `pcount` .

## <a name="ostrstreamrdbuf"></a><a name="rdbuf"></a> ostrstream:: rdarabelleğe

Akışın ilişkili strstreamsize nesnesine bir işaretçi döndürür.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Akışın ilişkilendirildiği strstreamarabelleğe yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, türünde depolanan akış arabelleğinin adresini `pointer` [strstreambuffer](../standard-library/strstreambuf-class.md)olarak döndürür.

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için bkz. [strstreamarabelleğe::p Count](../standard-library/strstreambuf-class.md#pcount) `rdbuf` .

## <a name="ostrstreamstr"></a><a name="str"></a> ostrstream:: Str

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

[ostream](../standard-library/ostream-typedefs.md#ostream)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
