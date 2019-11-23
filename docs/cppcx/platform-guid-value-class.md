---
title: Platform::Guid değer sınıfı
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: f63b2bb4fd5f809861622a4f6b255ee3725564b6
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816587"
---
# <a name="platformguid-value-class"></a>Platform::Guid değer sınıfı

Windows Çalışma Zamanı tür sisteminde bir [GUID](/previous-versions/cc317743(v%3dmsdn.10)) türü temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
public value struct Guid
```

### <a name="members"></a>Üyeleri

`Platform::Guid` [Platform:: Object sınıfından](../cppcx/platform-object-class.md)türetilmiş `Equals()`, `GetHashCode()`ve `ToString()` yöntemlere ve [Platform:: Type sınıfından](../cppcx/platform-type-class.md)türetilmiş `GetTypeCode()` yönteminden sahiptir. `Platform::Guid` Ayrıca aşağıdaki üyelere sahiptir.

|Üye|Açıklama|
|------------|-----------------|
|['İni](#ctor)|`Platform::Guid`yeni bir örneğini başlatır.|
|[operator==](#operator-equality)|Equals işleci.|
|[operator!=](#operator-inequality)|Eşit değildir işleci.|
|[işleç&lt;](#operator-less)|Küçüktür işleci.|
|[operator()](#operator-call)|Bir `Platform::Guid` `GUID`dönüştürür.|

### <a name="remarks"></a>Açıklamalar

Yeni bir `Platform::Guid`oluşturmak için [Windows:: Foundation:: GuidHelper:: CreateNewGuid](/uwp/api/windows.foundation.guidhelper.createnewguid#Windows_Foundation_GuidHelper_CreateNewGuid) statik yöntemini kullanın.

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Meta veri:** platform. winmd

## <a name="ctor"></a>Guid:: Guid oluşturucuları

`Platform::Guid`yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    unsigned char d,
    unsigned char e,
    unsigned char f,
    unsigned char g,
    unsigned char h,
    unsigned char i,
    unsigned char j,
    unsigned char k );

Guid(GUID m);

Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    Array<unsigned char>^ n );
```

### <a name="parameters"></a>Parametreler

*a*<br/>
`GUID`ilk 4 baytı.

*b*<br/>
`GUID`sonraki 2 baytı.

*c*<br/>
`GUID`sonraki 2 baytı.

*d*<br/>
`GUID`sonraki baytı.

*e*<br/>
`GUID`sonraki baytı.

*f*<br/>
`GUID`sonraki baytı.

*g*<br/>
`GUID`sonraki baytı.

*h*<br/>
`GUID`sonraki baytı.

*i*<br/>
`GUID`sonraki baytı.

*uygulanmaz*<br/>
`GUID`sonraki baytı.

*k*<br/>
`GUID`sonraki baytı.

*m*<br/>
Bir [GUID yapısı](/previous-versions/cc317743(v%3dmsdn.10))biçimindeki `GUID`.

*n*<br/>
`GUID`kalan 8 baytı.

## <a name="operator-equality"></a>Guid:: operator = = Işleci

, Eşitlik için iki `Platform::Guid` örneğini karşılaştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
static bool Platform::Guid::operator==(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parametreler

*guid1*<br/>
Karşılaştırılacak ilk `Platform::Guid`.

*guid2*<br/>
Karşılaştırılacak ikinci `Platform::Guid`.

### <a name="return-value"></a>Dönüş Değeri

İki `Platform::Guid` örneği eşitse true.

### <a name="remarks"></a>Açıklamalar

[Windows:: Foundation:: GuidHelper:: Equals](/uwp/api/windows.foundation.guidhelper.equals) static yöntemi yerine `==` işlecinin kullanılmasını tercih edin.

## <a name="operator-inequality"></a>Guid:: operator! = Işleci

Eşitsizlik için iki `Platform::Guid` örneğini karşılaştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
static bool Platform::Guid::operator!=(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parametreler

*guid1*<br/>
Karşılaştırılacak ilk `Platform::Guid`.

*guid2*<br/>
Karşılaştırılacak ikinci `Platform::Guid`.

### <a name="return-value"></a>Dönüş Değeri

İki `Platform::Guid` örneği eşitse true.

## <a name="operator-less"></a>Guid:: operator&lt; Işleci

Sıralama için iki `Platform::Guid` örneğini karşılaştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
static bool Platform::Guid::operator<(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parametreler

*guid1*<br/>
Karşılaştırılacak ilk `Platform::Guid`.

*guid2*<br/>
Karşılaştırılacak ikinci `Platform::Guid`.

### <a name="return-value"></a>Dönüş Değeri

*Guid1* , *guid2*'den önce sipariş alıyorsa true. Sıralama, her `Platform::Guid` 4 32 bitlik işaretsiz değerler dizisi gibi davrandıktan sonra lexicographic 'dir. Bu, SQL Server veya .NET Framework tarafından kullanılan sıralama değildir ve dize gösterimine göre lexıgraf sıralaması ile aynı değildir.

Bu işleç, `Guid` nesnelerinin C++ standart kitaplık tarafından daha kolay bir şekilde tüketilebilmesi için sağlanır.

## <a name="operator-call"></a>Guid:: operator () Işleci

Bir `Platform::Guid` bir [GUID yapısına](/previous-versions/cc317743(v%3dmsdn.10))örtülü olarak dönüştürür.

### <a name="syntax"></a>Sözdizimi

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>Dönüş Değeri

Bir [GUID yapısı](/previous-versions/cc317743(v%3dmsdn.10)).

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
