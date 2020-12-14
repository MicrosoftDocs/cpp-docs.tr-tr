---
description: 'Daha fazla bilgi edinin: Platform:: Guid değer sınıfı'
title: Platform::Guid değer sınıfı
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: 4c2ffc5096e6b40266fef0934acc562edf721c24
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195196"
---
# <a name="platformguid-value-class"></a>Platform::Guid değer sınıfı

Windows Çalışma Zamanı tür sisteminde bir [GUID] (/Windows/Win32/api/Guiddef/NS-Guiddef-Guid türü) temsil eder.

## <a name="syntax"></a>Syntax

```cpp
public value struct Guid
```

### <a name="members"></a>Üyeler

`Platform::Guid` Platform: `Equals()` `GetHashCode()` `ToString()` [: Object sınıfından](../cppcx/platform-object-class.md)türetilmiş, ve yöntemleri ve `GetTypeCode()` [Platform:: Type sınıfından](../cppcx/platform-type-class.md)türetilmiş yöntemi vardır. `Platform::Guid` Ayrıca aşağıdaki üyelere sahiptir.

|Üye|Açıklama|
|------------|-----------------|
|['İni](#ctor)|Yeni bir örneğini başlatır `Platform::Guid` .|
|[işleç = =](#operator-equality)|Equals işleci.|
|[işleç! =](#operator-inequality)|Eşit değildir işleci.|
|[işlecinde&lt;](#operator-less)|Küçüktür işleci.|
|[operator ()](#operator-call)|Bir `Platform::Guid` öğesine dönüştürür `GUID` .|

### <a name="remarks"></a>Açıklamalar

Yeni bir oluşturmak için `Platform::Guid` [Windows:: Foundation:: guidhelper:: createnewguıd](/uwp/api/windows.foundation.guidhelper.createnewguid) static metodunu kullanın.

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Meta veri:** platform. winmd

## <a name="guidguid-constructors"></a><a name="ctor"></a> Guid:: Guid oluşturucuları

Yeni bir örneğini başlatır `Platform::Guid` .

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
Öğesinin ilk 4 baytı `GUID` .

*kenarı*<br/>
Sonraki 2 baytı `GUID` .

*,*<br/>
Sonraki 2 baytı `GUID` .

*d*<br/>
Öğesinin sonraki baytı `GUID` .

*a*<br/>
Öğesinin sonraki baytı `GUID` .

*vadeli*<br/>
Öğesinin sonraki baytı `GUID` .

*Acil*<br/>
Öğesinin sonraki baytı `GUID` .

*h*<br/>
Öğesinin sonraki baytı `GUID` .

*i*<br/>
Öğesinin sonraki baytı `GUID` .

*uygulanmaz*<br/>
Öğesinin sonraki baytı `GUID` .

*ek*<br/>
Öğesinin sonraki baytı `GUID` .

*m*<br/>
Bir `GUID` [GUID yapısı](/windows/win32/api/guiddef/ns-guiddef-guid)biçimindeki bir.

*n*<br/>
Öğesinin kalan 8 baytı `GUID` .

## <a name="guidoperator-operator"></a><a name="operator-equality"></a> Guid:: operator = = Işleci

, `Platform::Guid` Eşitlik için iki örneği karşılaştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
static bool Platform::Guid::operator==(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parametreler

*guid1*<br/>
Karşılaştırılacak ilk `Platform::Guid` .

*guid2*<br/>
Karşılaştırılacak ikinci `Platform::Guid` .

### <a name="return-value"></a>Dönüş Değeri

İki `Platform::Guid` örnek eşitse true.

### <a name="remarks"></a>Açıklamalar

`==` [Windows:: Foundation:: guidhelper:: Equals](/uwp/api/windows.foundation.guidhelper.equals) statik yöntemi yerine işleci kullanmayı tercih edin.

## <a name="guidoperator-operator"></a><a name="operator-inequality"></a> Guid:: operator! = Işleci

`Platform::Guid`Eşitsizlik için iki örneği karşılaştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
static bool Platform::Guid::operator!=(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parametreler

*guid1*<br/>
Karşılaştırılacak ilk `Platform::Guid` .

*guid2*<br/>
Karşılaştırılacak ikinci `Platform::Guid` .

### <a name="return-value"></a>Dönüş Değeri

İki `Platform::Guid` örnek eşitse true.

## <a name="guidoperatorlt-operator"></a><a name="operator-less"></a> Guid:: operator &lt; işleci

`Platform::Guid`Sıralama için iki örneği karşılaştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
static bool Platform::Guid::operator<(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parametreler

*guid1*<br/>
Karşılaştırılacak ilk `Platform::Guid` .

*guid2*<br/>
Karşılaştırılacak ikinci `Platform::Guid` .

### <a name="return-value"></a>Dönüş Değeri

*Guid1* , *guid2*'den önce sipariş alıyorsa true. Sıralama, her biri `Platform::Guid` 4 32 bitlik işaretsiz değerlerden oluşan bir dizi gibi davrandıktan sonra lexicographic 'dir. Bu, SQL Server veya .NET Framework tarafından kullanılan sıralama değildir ve dize gösterimine göre lexıgraf sıralaması ile aynı değildir.

Bu işleç, `Guid` nesnelerin C++ standart kitaplığı tarafından daha kolay tüketilebilmesi için sağlanır.

## <a name="guidoperator-operator"></a><a name="operator-call"></a> Guid:: operator () Işleci

Örtük olarak bir `Platform::Guid` [GUID yapısına](/windows/win32/api/guiddef/ns-guiddef-guid)dönüştürür.

### <a name="syntax"></a>Syntax

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>Dönüş Değeri

Bir [GUID yapısı](/windows/win32/api/guiddef/ns-guiddef-guid).

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
