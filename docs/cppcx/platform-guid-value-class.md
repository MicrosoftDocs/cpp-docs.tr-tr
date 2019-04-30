---
title: Platform::Guid değer sınıfı
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: 64c70b619380d7c2ed4aaaecad3ee01a1d0f79c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383327"
---
# <a name="platformguid-value-class"></a>Platform::Guid değer sınıfı

Temsil eden bir [GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931) Windows çalışma zamanı tür sisteminde türü.

## <a name="syntax"></a>Sözdizimi

```cpp
public value struct Guid
```

### <a name="members"></a>Üyeler

`Platform::Guid` sahip `Equals()`, `GetHashCode()`, ve `ToString()` yöntemleri türetilen [Platform::Object sınıfı](../cppcx/platform-object-class.md)ve `GetTypeCode()` yöntemi türetilen [Platform::Type sınıfı](../cppcx/platform-type-class.md). `Platform::Guid` Ayrıca aşağıdaki üyeleri içerir.

|Üye|Açıklama|
|------------|-----------------|
|[GUID](#ctor)|Yeni bir örneğini başlatır bir `Platform::Guid`.|
|[operator==](#operator-equality)|Eşittir işleci.|
|[operator!=](#operator-inequality)|Eşit değil işleci.|
|[İşleci&lt;](#operator-less)|Küçüktür ya işleci.|
|[operator()](#operator-call)|Dönüştürür bir `Platform::Guid` için bir `GUID`.|

### <a name="remarks"></a>Açıklamalar

Yeni bir `Platform::Guid`, kullanın [Windows::Foundation::GuidHelper::CreateNewGuid](/uwp/api/windows.foundation.guidhelper.createnewguid#Windows_Foundation_GuidHelper_CreateNewGuid) statik yöntem.

### <a name="requirements"></a>Gereksinimler

**En düşük desteklenen istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** Platform

**Meta veri:** platform.winmd

## <a name="ctor"></a> Guid::guid oluşturucular

Yeni bir örneğini başlatır bir `Platform::Guid`.

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
İlk 4 baytı `GUID`.

*b*<br/>
Öğesinin sonraki 2 baytı `GUID`.

*c*<br/>
Öğesinin sonraki 2 baytı `GUID`.

*d*<br/>
Öğesinin sonraki baytı `GUID`.

*e*<br/>
Öğesinin sonraki baytı `GUID`.

*f*<br/>
Öğesinin sonraki baytı `GUID`.

*g*<br/>
Öğesinin sonraki baytı `GUID`.

*h*<br/>
Öğesinin sonraki baytı `GUID`.

*i*<br/>
Öğesinin sonraki baytı `GUID`.

*j*<br/>
Öğesinin sonraki baytı `GUID`.

*k*<br/>
Öğesinin sonraki baytı `GUID`.

*m*<br/>
A `GUID` biçiminde bir [GUID yapısı](https://msdn.microsoft.com/library/windows/desktop/aa373931).

*n*<br/>
Kalan 8 bayt `GUID`.

## <a name="operator-equality"></a> Guid::operator == işleci

İki karşılaştırır `Platform::Guid` örneği eşitlik.

### <a name="syntax"></a>Sözdizimi

```cpp
static bool Platform::Guid::operator==(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parametreler

*guid1*<br/>
İlk `Platform::Guid` karşılaştırmak için.

*guid2*<br/>
İkinci `Platform::Guid` karşılaştırmak için.

### <a name="return-value"></a>Dönüş Değeri

TRUE ise iki `Platform::Guid` örnekleri eşit.

### <a name="remarks"></a>Açıklamalar

Kullanmayı tercih `==` yerine işleci [Windows::Foundation::GuidHelper::Equals](/uwp/api/windows.foundation.guidhelper.equals) statik yöntem.

## <a name="operator-inequality"></a> Guid::operator! = işleci

İki karşılaştırır `Platform::Guid` örneği eşitsizlik açısından.

### <a name="syntax"></a>Sözdizimi

```cpp
static bool Platform::Guid::operator!=(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parametreler

*guid1*<br/>
İlk `Platform::Guid` karşılaştırmak için.

*guid2*<br/>
İkinci `Platform::Guid` karşılaştırmak için.

### <a name="return-value"></a>Dönüş Değeri

TRUE ise iki `Platform::Guid` örnekleri eşit değildir.

## <a name="operator-less"></a> Guid::operator&lt; işleci

İki karşılaştırır `Platform::Guid` sıralama için örnekleri.

### <a name="syntax"></a>Sözdizimi

```cpp
static bool Platform::Guid::operator<(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parametreler

*guid1*<br/>
İlk `Platform::Guid` karşılaştırmak için.

*guid2*<br/>
İkinci `Platform::Guid` karşılaştırmak için.

### <a name="return-value"></a>Dönüş Değeri

TRUE ise *guid1* önceyse *guid2*. Her değerlendirmesini sonra lexicographic sıralamadır `Platform::Guid` dört 32-bit işeritsiz değerler dizisi ise gibi. Bu SQL Server veya .NET Framework tarafından kullanılan sıralama değil veya lexicographical dize gösterimi göre sıralama ile aynı değil.

Bu işleç sağlanan böylece `Guid` nesneleri C++ Standart Kitaplığı tarafından daha kolay da kullanılabilir.

## <a name="operator-call"></a> Guid::operator() Operator

Örtük olarak dönüştürür bir `Platform::Guid` için bir [GUID yapısı](https://msdn.microsoft.com/library/windows/desktop/aa373931).

### <a name="syntax"></a>Sözdizimi

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>Dönüş Değeri

A [GUID yapısı](https://msdn.microsoft.com/library/windows/desktop/aa373931).

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
