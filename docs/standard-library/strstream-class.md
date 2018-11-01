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
ms.openlocfilehash: 9494f7ee2508df1971d56c94b929a7212bedb254
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562116"
---
# <a name="strstream-class"></a>strstream Sınıfı

Ekleme ve çıkarma öğelerin denetleyen bir nesne ve bir akış arabelleğinin sınıfı kullanarak kodlanmış nesne açıklar [strstreambuf](../standard-library/strstreambuf-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class strstream : public iostream
```

## <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi nesneyi depolar `strstreambuf`.

> [!NOTE]
> Bu sınıf kullanımdan kaldırılmıştır. Kullanmayı [stringstream](../standard-library/sstream-typedefs.md#stringstream) veya [wstringstream](../standard-library/sstream-typedefs.md#wstringstream) yerine.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[strstream](#strstream)|Türünde bir nesne oluşturur `strstream`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Dondurma](#freeze)|Akış Arabellek işlemleri kullanılabilir olması bir akış arabelleğinin neden olur.|
|[pcount](#pcount)|Denetlenen dizi için yazılan öğelerin sayısını döndürür.|
|[rdbuf](#rdbuf)|Akış için bir işaretçi ilişkili döndürür `strstreambuf` nesne.|
|[str](#str)|Çağrıları [dondurma](../standard-library/strstreambuf-class.md#freeze)ve denetlenen dizinin başlangıcı için bir işaretçi döndürür.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<strstream >

**Namespace:** std

## <a name="freeze"></a>  strstream::Freeze

Akış Arabellek işlemleri kullanılabilir olması bir akış arabelleğinin neden olur.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Parametreler

*_Freezeit*<br/>
A **bool** donabilir akış isteyip istemediğinizi belirten.

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrıları [rdbuf](#rdbuf) -> [dondurma](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*).

### <a name="example"></a>Örnek

Bkz: [strstreambuf::freeze](../standard-library/strstreambuf-class.md#freeze) kullanan bir örnek için `freeze`.

## <a name="pcount"></a>  strstream::pcount

Denetlenen dizi için yazılan öğelerin sayısını döndürür.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen dizi için yazılan öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount).

### <a name="example"></a>Örnek

Bkz: [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) pcount kullanımının bir örneği için.

## <a name="rdbuf"></a>  strstream::rdbuf

Akışın ilişkili strstreambuf nesnesine bir işaretçi döndürür.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Akış için bir işaretçi strstreambuf nesne yükleyicidir.

### <a name="remarks"></a>Açıklamalar

Üye işlevi türünde depolanmış bir akış arabelleğinin adresini döndürür `pointer` için [strstreambuf](../standard-library/strstreambuf-class.md).

### <a name="example"></a>Örnek

Bkz: [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) kullanan bir örnek için `rdbuf`.

## <a name="str"></a>  strstream::Str

Çağrıları [dondurma](../standard-library/strstreambuf-class.md#freeze)ve denetlenen dizinin başlangıcı için bir işaretçi döndürür.

```cpp
char *str();
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen dizinin başlangıcına bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str).

### <a name="example"></a>Örnek

Bkz: [strstreambuf::str](../standard-library/strstreambuf-class.md#str) kullanan bir örnek için `str`.

## <a name="strstream"></a>  strstream::strstream

Türünde bir nesne oluşturur `strstream`.

```cpp
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Parametreler

*Sayısı*<br/>
Arabellek boyutu.

*_Modu*<br/>
Giriş ve çıkış modu arabellek. Bkz: [ios_base::openmode](../standard-library/ios-base-class.md#openmode) daha fazla bilgi için.

*ptr*<br/>
Arabellek.

### <a name="remarks"></a>Açıklamalar

Her iki Oluşturucu çağırarak temel sınıf başlatmak [streambuf](../standard-library/streambuf-typedefs.md#streambuf)( **sb**), burada `sb` depolanan nesne sınıfının [strstreambuf](../standard-library/strstreambuf-class.md). İlk Oluşturucu ayrıca başlatır `sb` çağırarak [strstreambuf](../standard-library/strstreambuf-class.md#strstreambuf). İkinci Oluşturucu, temel sınıf iki yoldan biriyle başlatır:

- Varsa `_Mode`  &  **ios_base::app**== 0, ardından *ptr* içeren bir dizinin ilk öğesi tanımlamalısınız `count` öğeleri ve oluşturucu çağrıları `strstreambuf`( `ptr`, `count`, `ptr`).

- Aksi takdirde, *ptr* ilk öğesi, ilk öğe olarak tasarlanmış bir C dizesi içeren bir dizi count öğelerini tanımlamalısınız *ptr*ve oluşturucu çağrıları `strstreambuf`( `ptr`, `count`, `ptr` + `strlen`( `ptr`) ).

## <a name="see-also"></a>Ayrıca bkz.

[iostream](../standard-library/istream-typedefs.md#iostream)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
