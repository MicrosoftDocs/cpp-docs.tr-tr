---
title: ostrstream sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- strstream/std::ostrstream::freeze
- strstream/std::ostrstream::pcount
- strstream/std::ostrstream::rdbuf
- strstream/std::ostrstream::str
dev_langs:
- C++
helpviewer_keywords:
- std::ostrstream [C++], freeze
- std::ostrstream [C++], pcount
- std::ostrstream [C++], rdbuf
- std::ostrstream [C++], str
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d268b9cd2ba7d83f44b5e0ebd516208d17ee726
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858113"
---
# <a name="ostrstream-class"></a>ostrstream Sınıfı

Öğeler ekleme denetimlerini bir nesne ve kodlanmış nesneleri bir sınıf akışı arabelleğe açıklar [strstreambuf](../standard-library/strstreambuf-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class ostrstream : public ostream
```

## <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi nesne depolar `strstreambuf`.

> [!NOTE]
> Bu sınıf kullanım dışıdır. Kullanmayı [ostringstream](../standard-library/sstream-typedefs.md#ostringstream) veya [wostringstream](../standard-library/sstream-typedefs.md#wostringstream) yerine.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[ostrstream](#ostrstream)|Türünde bir nesne oluşturur `ostrstream`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Dondurma](#freeze)|Bir Akış Arabellek Akış Arabellek işlemleri kullanılamaz hale gelmesine neden olur.|
|[pcount](#pcount)|Denetimli sıraya yazılan öğeleri sayısını döndürür.|
|[rdbuf](#rdbuf)|Bir işaretçi akışa ilişkili döndürür `strstreambuf` nesnesi.|
|[str](#str)|Çağrıları [Dondur](../standard-library/strstreambuf-class.md#freeze)ve ardından bir işaretçi denetimli sıranın başına döndürür.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<strstream >

**Namespace:** std

## <a name="freeze"></a>  ostrstream::Freeze

Bir Akış Arabellek Akış Arabellek işlemleri kullanılamaz hale gelmesine neden olur.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Parametreler

`_Freezeit` A `bool` donabilir akış isteyip istemediğinizi belirten.

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrılarını [rdbuf](#rdbuf) -> [Dondur](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*).

### <a name="example"></a>Örnek

Bkz: [strstream::freeze](../standard-library/strstreambuf-class.md#freeze) kullanan bir örnek **Dondur**.

## <a name="ostrstream"></a>  ostrstream::ostrstream

Türünde bir nesne oluşturur `ostrstream`.

```cpp
ostrstream();

ostrstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>Parametreler

`ptr` Arabellek.

`count` Arabelleğinin bayt cinsinden boyutu.

`_Mode` Giriş ve çıkış modu arabellek. Bkz: [ios_base::openmode](../standard-library/ios-base-class.md#openmode) daha fazla bilgi için.

### <a name="remarks"></a>Açıklamalar

Çağırarak temel sınıfını hem oluşturucular başlatmak [ostream](../standard-library/ostream-typedefs.md#ostream)( **sb**), burada **sb** saklı nesne sınıfının [strstreambuf](../standard-library/strstreambuf-class.md). İlk Oluşturucu ayrıca başlatır **sb** çağırarak `strstreambuf`. İkinci Oluşturucu, temel sınıf iki yoldan biriyle başlatır:

- Varsa `_Mode`  &  **ios_base::app**0, ardından == `ptr` dizisinin ilk öğesi belirlemelisiniz `count` öğeleri ve oluşturucu çağrıları `strstreambuf`( `ptr`, `count`, `ptr`).

- Aksi takdirde, `ptr` dizisinin ilk öğesi, ilk öğe olarak tasarlanmış bir C dize içeren bir sayım öğelerinin belirlemelisiniz `ptr`ve oluşturucu çağrıları `strstreambuf`( `ptr`, `count`, `ptr` + `strlen`( `ptr`) ).

## <a name="pcount"></a>  ostrstream::pcount

Denetimli sıraya yazılan öğeleri sayısını döndürür.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetimli sıraya yazılan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount).

### <a name="example"></a>Örnek

Bkz: [strstream::pcount](../standard-library/strstreambuf-class.md#pcount) kullanan bir örnek için `pcount`.

## <a name="rdbuf"></a>  ostrstream::rdbuf

Bir işaretçi akışın ilişkili strstreambuf nesnesi döndürür.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Akış için bir işaretçi strstreambuf nesne ilişkili.

### <a name="remarks"></a>Açıklamalar

Üye işlevi türü saklı Akış Arabellek adresini döndürür **işaretçi** için [strstreambuf](../standard-library/strstreambuf-class.md).

### <a name="example"></a>Örnek

Bkz: [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) kullanan bir örnek için `rdbuf`.

## <a name="str"></a>  ostrstream::Str

Çağrıları [Dondur](../standard-library/strstreambuf-class.md#freeze)ve ardından bir işaretçi denetimli sıranın başına döndürür.

```cpp
char *str();
```

### <a name="return-value"></a>Dönüş Değeri

Denetimli dizisi başına bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str).

### <a name="example"></a>Örnek

Bkz: [strstream::str](../standard-library/strstreambuf-class.md#str) kullanan bir örnek için **str**.

## <a name="see-also"></a>Ayrıca bkz.

[ostream](../standard-library/ostream-typedefs.md#ostream)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
