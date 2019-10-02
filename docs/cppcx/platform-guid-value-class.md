---
title: 'Platform:: Guid değer sınıfı'
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
# <a name="platformguid-value-class"></a>Platform:: Guid değer sınıfı

Windows Çalışma Zamanı tür sisteminde bir [GUID](/previous-versions/cc317743(v%3dmsdn.10)) türü temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
public value struct Guid
```

### <a name="members"></a>Üyeleri

`Platform::Guid`, [Platform:: Object sınıfından](../cppcx/platform-object-class.md)türetilmiş `Equals()`, `GetHashCode()` ve `ToString()` yöntemlerine sahiptir ve [Platform:: Type sınıfından](../cppcx/platform-type-class.md)türetilmiş `GetTypeCode()` yöntemi vardır. `Platform::Guid` ' da aşağıdaki Üyeler de vardır.

|Üye|Açıklama|
|------------|-----------------|
|['İni](#ctor)|@No__t yeni bir örneğini başlatır-0.|
|[işleç = =](#operator-equality)|Equals işleci.|
|[işleç! =](#operator-inequality)|Eşit değildir işleci.|
|[işleç @ no__t-1](#operator-less)|Küçüktür işleci.|
|[operator ()](#operator-call)|@No__t-0 ' a bir `GUID` dönüştürür.|

### <a name="remarks"></a>Açıklamalar

Yeni bir @no__t oluşturmak için, [Windows:: Foundation:: GuidHelper:: Createnewguıd](/uwp/api/windows.foundation.guidhelper.createnewguid#Windows_Foundation_GuidHelper_CreateNewGuid) static metodunu kullanın.

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Meta veri:** platform. winmd

## <a name="ctor"></a>Guid:: Guid oluşturucuları

@No__t yeni bir örneğini başlatır-0.

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
@No__t-0 ' ın ilk 4 baytı.

*kenarı*<br/>
@No__t 0 ' ın sonraki 2 baytı.

*,*<br/>
@No__t 0 ' ın sonraki 2 baytı.

*TID*<br/>
@No__t sonraki baytı-0.

*a*<br/>
@No__t sonraki baytı-0.

*vadeli*<br/>
@No__t sonraki baytı-0.

*Acil*<br/>
@No__t sonraki baytı-0.

*olsun*<br/>
@No__t sonraki baytı-0.

*kaydedemiyorum*<br/>
@No__t sonraki baytı-0.

*uygulanmaz*<br/>
@No__t sonraki baytı-0.

*ek*<br/>
@No__t sonraki baytı-0.

*m*<br/>
Bir [GUID yapısı](/previous-versions/cc317743(v%3dmsdn.10))biçimindeki `GUID`.

*No*<br/>
@No__t 0 ' ın kalan 8 baytı.

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

### <a name="return-value"></a>Dönüş değeri

İki `Platform::Guid` örneği eşitse true.

### <a name="remarks"></a>Açıklamalar

[Windows:: Foundation:: GuidHelper:: Equals](/uwp/api/windows.foundation.guidhelper.equals) static yöntemi yerine `==` işlecini kullanmayı tercih edin.

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

### <a name="return-value"></a>Dönüş değeri

İki `Platform::Guid` örneği eşitse true.

## <a name="operator-less"></a>Guid:: operator @ no__t-1 Işleci

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

### <a name="return-value"></a>Dönüş değeri

*Guid1* , *guid2*'den önce sipariş alıyorsa true. Sıralama, 4 32 bitlik işaretsiz değerler dizisi gibi her `Platform::Guid` ' a davrandıktan sonra lexicographic olur. Bu, SQL Server veya .NET Framework tarafından kullanılan sıralama değildir ve dize gösterimine göre lexıgraf sıralaması ile aynı değildir.

Bu işleç, `Guid` nesnelerinin C++ standart kitaplık tarafından daha kolay bir şekilde tüketilebilmesi için sağlanır.

## <a name="operator-call"></a>Guid:: operator () Işleci

@No__t-0 ' i örtük olarak bir [GUID yapısına](/previous-versions/cc317743(v%3dmsdn.10))dönüştürür.

### <a name="syntax"></a>Sözdizimi

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>Dönüş değeri

Bir [GUID yapısı](/previous-versions/cc317743(v%3dmsdn.10)).

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
