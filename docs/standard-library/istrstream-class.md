---
title: istrstream sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
dev_langs:
- C++
helpviewer_keywords:
- istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6484d70488da834d0acea79cbe9b02968e0e2a35
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957291"
---
# <a name="istrstream-class"></a>istrstream Sınıfı

Öğelerin ayıklama denetleyen bir nesne ve bir akış arabelleğinin sınıfın kodlanmış nesnelerden açıklar [strstreambuf](../standard-library/strstreambuf-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class istrstream : public istream
```

## <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi nesneyi depolar `strstreambuf`.

> [!NOTE]
> Bu sınıf kullanımdan kaldırılmıştır. Kullanmayı [istringstream](../standard-library/sstream-typedefs.md#istringstream) veya [wistringstream](../standard-library/sstream-typedefs.md#wistringstream) yerine.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[istrstream](#istrstream)|Türünde bir nesne oluşturur `istrstream`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|Akış için bir işaretçi ilişkili döndürür `strstreambuf` nesne.|
|[str](#str)|Çağrıları [dondurma](../standard-library/strstreambuf-class.md#freeze)ve denetlenen dizinin başlangıcı için bir işaretçi döndürür.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<strstream >

**Namespace:** std

## <a name="istrstream"></a>  istrstream::istrstream

Türünde bir nesne oluşturur `istrstream`.

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

*sayısı* arabellek uzunluğu (*ptr*).

*PTR* içeriği ile arabellek başlatılır.

### <a name="remarks"></a>Açıklamalar

Çağırarak temel sınıf oluşturucuları başlatmak [istream](../standard-library/istream-typedefs.md#istream)(**sb**), burada `sb` depolanan nesne sınıfının [strstreambuf](../standard-library/strstreambuf-class.md). İlk iki Oluşturucu ayrıca başlatmak `sb` çağırarak `strstreambuf`(( **const** `char` \*) `ptr`, 0). Kalan iki Oluşturucu bunun yerine çağrı `strstreambuf`(( **const** `char` *) `ptr`, `count` ).

## <a name="rdbuf"></a>  istrstream::rdbuf

Akışın ilişkili strstreambuf nesnesine bir işaretçi döndürür.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Akış için bir işaretçi strstreambuf nesne yükleyicidir.

### <a name="remarks"></a>Açıklamalar

Üye işlev işaretçi türüne saklı akış arabelleğini adresini döndürür [strstreambuf](../standard-library/strstreambuf-class.md).

### <a name="example"></a>Örnek

Bkz: [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) kullanan bir örnek için `rdbuf`.

## <a name="str"></a>  istrstream::Str

Çağrıları [dondurma](../standard-library/strstreambuf-class.md#freeze)ve denetlenen dizinin başlangıcı için bir işaretçi döndürür.

```cpp
char *str();
```

### <a name="return-value"></a>Dönüş Değeri

Denetlenen dizinin başlangıcına bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str).

### <a name="example"></a>Örnek

Bkz: [strstream::str](../standard-library/strstreambuf-class.md#str) kullanan bir örnek için `str`.

## <a name="see-also"></a>Ayrıca bkz.

[istream](../standard-library/istream-typedefs.md#istream)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
