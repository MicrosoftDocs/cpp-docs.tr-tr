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
ms.openlocfilehash: e48e6fcd7da3b1e1c91b4aecb640c02ae4068bf9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="istrstream-class"></a>istrstream Sınıfı

Ayıklama öğelerinin denetleyen bir nesne ve akış arabellek sınıfının kodlanmış nesnelerden açıklar [strstreambuf](../standard-library/strstreambuf-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class istrstream : public istream
```

## <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi nesne depolar `strstreambuf`.

> [!NOTE]
> Bu sınıf kullanım dışıdır. Kullanmayı [istringstream](../standard-library/sstream-typedefs.md#istringstream) veya [wistringstream](../standard-library/sstream-typedefs.md#wistringstream) yerine.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[istrstream](#istrstream)|Türünde bir nesne oluşturur `istrstream`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[rdbuf](#rdbuf)|Bir işaretçi akışa ilişkili döndürür `strstreambuf` nesnesi.|
|[str](#str)|Çağrıları [Dondur](../standard-library/strstreambuf-class.md#freeze)ve ardından bir işaretçi denetimli sıranın başına döndürür.|

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

`count` Arabelleğin uzunluğu ( `ptr`).

`ptr` Arabellek başlatıldığı içeriğini.

### <a name="remarks"></a>Açıklamalar

Çağırarak tüm oluşturucular temel sınıfı başlatma [IStream](../standard-library/istream-typedefs.md#istream)( **sb**), burada **sb** saklı nesne sınıfının [strstreambuf](../standard-library/strstreambuf-class.md) . İlk iki oluşturucular ayrıca başlatma **sb** çağırarak `strstreambuf`(( **const** `char` \*) `ptr`, 0). Kalan iki oluşturucular yerine çağırın `strstreambuf`(( **const** `char` *) `ptr`, `count` ).

## <a name="rdbuf"></a>  istrstream::rdbuf

Bir işaretçi akışın ilişkili strstreambuf nesnesi döndürür.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Dönüş Değeri

Akış için bir işaretçi strstreambuf nesne ilişkili.

### <a name="remarks"></a>Açıklamalar

Üye işlevi türü işaretçinin saklı Akış Arabellek adresini döndürür [strstreambuf](../standard-library/strstreambuf-class.md).

### <a name="example"></a>Örnek

Bkz: [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) kullanan bir örnek için `rdbuf`.

## <a name="str"></a>  istrstream::Str

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

[istream](../standard-library/istream-typedefs.md#istream)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
