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
ms.openlocfilehash: 796bf1b3ac41a4b5a6ab5bc16239d50616f554df
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224623"
---
# <a name="strstream-class"></a>strstream Sınıfı

[Strstreambuffer](../standard-library/strstreambuf-class.md)sınıfının akış arabelleğini kullanarak öğelerin ve ayıklamanın ve kodlanmış nesnelerin eklenmesini ve ayıklanmasını denetleyen bir nesne tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class strstream : public iostream
```

## <a name="remarks"></a>Açıklamalar

Nesnesi, sınıfının bir nesnesini depolar `strstreambuf` .

> [!NOTE]
> Bu sınıf kullanım dışıdır. Bunun yerine [stringstream](../standard-library/sstream-typedefs.md#stringstream) veya [wstringstream](../standard-library/sstream-typedefs.md#wstringstream) kullanmayı düşünün.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[strstream](#strstream)|Türünde bir nesne oluşturur `strstream` .|

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

## <a name="strstreamfreeze"></a><a name="freeze"></a>strstream:: Freeze

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

Tarafından kullanılan bir örnek için bkz. [strstreamarabelleğe:: Freeze](../standard-library/strstreambuf-class.md#freeze) `freeze` .

## <a name="strstreampcount"></a><a name="pcount"></a>strstream::p sayısı

Denetlenen diziye yazılan öğe sayısının sayısını döndürür.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen diziye yazılan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf)  ->  [pcount](../standard-library/strstreambuf-class.md#pcount)döndürür.

### <a name="example"></a>Örnek

Pcount kullanımı örneği için bkz. [strstreamarabelleğe::p Count](../standard-library/strstreambuf-class.md#pcount) .

## <a name="strstreamrdbuf"></a><a name="rdbuf"></a>strstream:: rdarabelleğe

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

## <a name="strstreamstr"></a><a name="str"></a>strstream:: Str

Çağırır [ve](../standard-library/strstreambuf-class.md#freeze)sonra denetlenen sıranın başlangıcına bir işaretçi döndürür.

```cpp
char *str();
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen dizinin başlangıcına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf)  ->  [Str](../standard-library/strstreambuf-class.md#str)döndürür.

### <a name="example"></a>Örnek

Tarafından kullanılan bir örnek için bkz. [strstreamarabelleğe:: Str](../standard-library/strstreambuf-class.md#str) `str` .

## <a name="strstreamstrstream"></a><a name="strstream"></a>strstream:: strstream

Türünde bir nesne oluşturur `strstream` .

```cpp
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Arabelleğin boyutu.

*_Mode*\
Arabelleğin giriş ve çıkış modu. Daha fazla bilgi için bkz. [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode) .

*kaydetmeye*\
Arabellek.

### <a name="remarks"></a>Açıklamalar

Her iki Oluşturucu, **sb**strstreamarabellek sınıfının saklı nesnesi olan [streamarabelleğe](../standard-library/streambuf-typedefs.md#streambuf)(SB) çağırarak temel sınıfı başlatır `sb` . [strstreambuf](../standard-library/strstreambuf-class.md) İlk Oluşturucu, `sb` [strstreamarabelleğe](../standard-library/strstreambuf-class.md#strstreambuf)çağırarak da başlatılır. İkinci Oluşturucu, temel sınıfı iki yönden birini başlatır:

- `_Mode`  &  **İos_base:: App**= = 0 ise, *PTR* bir öğe dizisinin ilk öğesini `count` ve Oluşturucu çağırır `strstreambuf` ( `ptr` , `count` , `ptr` ).

- Aksi halde, *PTR* , ilk öğesi *PTR*tarafından atanan bir C dizesi içeren Count öğeleri dizisinin ilk öğesini belirlemelidir ve Oluşturucu `strstreambuf` ( `ptr` , `count` , `ptr`  +  `strlen` ( `ptr` )) çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[iostream](../standard-library/istream-typedefs.md#iostream)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
