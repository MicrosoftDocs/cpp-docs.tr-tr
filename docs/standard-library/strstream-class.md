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
ms.openlocfilehash: 53baa350121796d5198211e1fdb08f4341df6b80
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459096"
---
# <a name="strstream-class"></a>strstream Sınıfı

[Strstreambuffer](../standard-library/strstreambuf-class.md)sınıfının akış arabelleğini kullanarak öğelerin ve ayıklamanın ve kodlanmış nesnelerin eklenmesini ve ayıklanmasını denetleyen bir nesne tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class strstream : public iostream
```

## <a name="remarks"></a>Açıklamalar

Nesnesi, sınıfının `strstreambuf`bir nesnesini depolar.

> [!NOTE]
> Bu sınıf kullanım dışıdır. Bunun yerine [stringstream](../standard-library/sstream-typedefs.md#stringstream) veya [wstringstream](../standard-library/sstream-typedefs.md#wstringstream) kullanmayı düşünün.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[strstream](#strstream)|Türünde `strstream`bir nesne oluşturur.|

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

## <a name="freeze"></a>strstream:: Freeze

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

Tarafından kullanılan `freeze`bir örnek için bkz. [strstreamarabelleğe:: Freeze](../standard-library/strstreambuf-class.md#freeze) .

## <a name="pcount"></a>strstream::p sayısı

Denetlenen diziye yazılan öğe sayısının sayısını döndürür.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen diziye yazılan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount)döndürür.

### <a name="example"></a>Örnek

Pcount kullanımı örneği için bkz. [strstreamarabelleğe::p Count](../standard-library/strstreambuf-class.md#pcount) .

## <a name="rdbuf"></a>strstream:: rdarabelleğe

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

## <a name="str"></a>strstream:: Str

Çağırır [ve](../standard-library/strstreambuf-class.md#freeze)sonra denetlenen sıranın başlangıcına bir işaretçi döndürür.

```cpp
char *str();
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen dizinin başlangıcına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [rdarabelleğe](#rdbuf) -> [Str](../standard-library/strstreambuf-class.md#str)döndürür.

### <a name="example"></a>Örnek

Tarafından kullanılan `str`bir örnek için bkz. [strstreamarabelleğe:: Str](../standard-library/strstreambuf-class.md#str) .

## <a name="strstream"></a>strstream:: strstream

Türünde `strstream`bir nesne oluşturur.

```cpp
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Arabelleğin boyutu.

*_Mod*\
Arabelleğin giriş ve çıkış modu. Daha fazla bilgi için bkz. [ios_base:: OpenMode](../standard-library/ios-base-class.md#openmode) .

*kaydetmeye*\
Arabellek.

### <a name="remarks"></a>Açıklamalar

Her iki Oluşturucu, [strstreamarabellek](../standard-library/strstreambuf-class.md)sınıfının saklı nesnesi `sb` olan [streamarabelleğe](../standard-library/streambuf-typedefs.md#streambuf)( **SB**) çağırarak temel sınıfı başlatır. İlk Oluşturucu, `sb` [strstreamarabelleğe](../standard-library/strstreambuf-class.md#strstreambuf)çağırarak da başlatılır. İkinci Oluşturucu, temel sınıfı iki yönden birini başlatır:

- `_Mode` **İos_base:: App**= = 0 ise  & , *PTR* bir `count` öğe dizisinin ilk öğesini ve Oluşturucu çağırır `strstreambuf`( `ptr`, `count`, `ptr`) .

- Aksi halde *, PTR* , ilk öğesi *PTR*tarafından atanan bir C dizesi içeren Count öğeleri dizisinin ilk öğesini belirlemelidir ve Oluşturucu çağırır `strstreambuf`( `ptr`,, `ptr` `count`  +  `strlen`( `ptr`) ).

## <a name="see-also"></a>Ayrıca bkz.

[iostream](../standard-library/istream-typedefs.md#iostream)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
