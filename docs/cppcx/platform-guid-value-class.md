---
title: Platform::Guid değer sınıfı
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: 7c3b89ff238b1cb5ee9fbb71e83d20f571e656a3
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82031543"
---
# <a name="platformguid-value-class"></a>Platform::Guid değer sınıfı

Windows Runtime türü sisteminde [GUID](/windows/win32/api/guiddef/ns-guiddef-guidtype türünü temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
public value struct Guid
```

### <a name="members"></a>Üyeler

`Platform::Guid`, `Equals()`, `GetHashCode()`ve `ToString()` Platform'dan türetilen [yöntemler::Object Class](../cppcx/platform-object-class.md), ve Platform'dan türetilen `GetTypeCode()` [yöntem::Tür Sınıfı](../cppcx/platform-type-class.md). `Platform::Guid`ayrıca aşağıdaki üyelere sahiptir.

|Üye|Açıklama|
|------------|-----------------|
|[Guıd](#ctor)|Yeni bir örneğini başolarak `Platform::Guid`karşılar.|
|[işleç==](#operator-equality)|Eşittir işleci.|
|[işleç!=](#operator-inequality)|Eşit değil işleç.|
|[Işleç&lt;](#operator-less)|Operatörden daha az.|
|[işleç()](#operator-call)|A'yı `Platform::Guid` bir'e `GUID`dönüştürür.|

### <a name="remarks"></a>Açıklamalar

Yeni `Platform::Guid`bir oluşturmak [için, Windows kullanın::Foundation::GuidHelper::CreateNewGuid](/uwp/api/windows.foundation.guidhelper.createnewguid) statik yöntemi.

### <a name="requirements"></a>Gereksinimler

**Minimum desteklenen istemci:** Windows 8

**Minimum desteklenen sunucu:** Windows Server 2012

**Ad alanı:** Platform

**Meta veriler:** platform.winmd

## <a name="guidguid-constructors"></a><a name="ctor"></a>Yol gösterici::Yol Gösterici

Yeni bir örneğini başolarak `Platform::Guid`karşılar.

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

*A*<br/>
İlk 4 `GUID`bayt.

*B*<br/>
Sonraki 2 `GUID`bayt.

*C*<br/>
Sonraki 2 `GUID`bayt.

*D*<br/>
Bir sonraki `GUID`bayt.

*E*<br/>
Bir sonraki `GUID`bayt.

*F*<br/>
Bir sonraki `GUID`bayt.

*G*<br/>
Bir sonraki `GUID`bayt.

*H*<br/>
Bir sonraki `GUID`bayt.

*Ⅰ*<br/>
Bir sonraki `GUID`bayt.

*J*<br/>
Bir sonraki `GUID`bayt.

*Kahraman*<br/>
Bir sonraki `GUID`bayt.

*M*<br/>
A `GUID` şeklinde bir [GUID yapısı](/windows/win32/api/guiddef/ns-guiddef-guid).

*n*<br/>
Kalan 8 `GUID`bayt.

## <a name="guidoperator-operator"></a><a name="operator-equality"></a>Kılavuz::operator== Operatör

Eşitlik için `Platform::Guid` iki örneği karşılaştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
static bool Platform::Guid::operator==(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parametreler

*yol gösterici1*<br/>
İlk `Platform::Guid` karşılaştırılanın.

*yol gösterici2*<br/>
Karşılaştırmak `Platform::Guid` için ikinci.

### <a name="return-value"></a>Dönüş Değeri

İki `Platform::Guid` örnek eşitse doğrudur.

### <a name="remarks"></a>Açıklamalar

Windows yerine `==` işleci kullanmayı tercih edin::Temel::GuidHelper::Eşittir statik yöntem. [Windows::Foundation::GuidHelper::Equals](/uwp/api/windows.foundation.guidhelper.equals)

## <a name="guidoperator-operator"></a><a name="operator-inequality"></a>Kılavuz::operator!= Operatör

Eşitsizlik için `Platform::Guid` iki örneği karşılaştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
static bool Platform::Guid::operator!=(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parametreler

*yol gösterici1*<br/>
İlk `Platform::Guid` karşılaştırılanın.

*yol gösterici2*<br/>
Karşılaştırmak `Platform::Guid` için ikinci.

### <a name="return-value"></a>Dönüş Değeri

İki `Platform::Guid` örnek eşit değilse doğrudur.

## <a name="guidoperatorlt-operator"></a><a name="operator-less"></a>Kılavuz::operatör&lt; Operatörü

Sipariş için `Platform::Guid` iki örneği karşılaştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
static bool Platform::Guid::operator<(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parametreler

*yol gösterici1*<br/>
İlk `Platform::Guid` karşılaştırılanın.

*yol gösterici2*<br/>
Karşılaştırmak `Platform::Guid` için ikinci.

### <a name="return-value"></a>Dönüş Değeri

*Guid1* *guid2'den*önce sipariş edilirse doğru. Sıralama, her birine `Platform::Guid` dört adet 32 bit imzasız değerden oluşan bir dizi gibi davrandıktan sonra lexicographic'dir. Bu, SQL Server veya .NET Framework tarafından kullanılan sıralama değildir ve dize gösterimi ile lexicographical ordering ile aynı değildir.

Bu işleç, `Guid` nesnelerin C++ standart kitaplığı tarafından daha kolay tüketilebilmeleri için sağlanır.

## <a name="guidoperator-operator"></a><a name="operator-call"></a>Kılavuz::operator() Operatör

Örtük olarak `Platform::Guid` bir [GUID yapısına](/windows/win32/api/guiddef/ns-guiddef-guid)dönüştürür.

### <a name="syntax"></a>Sözdizimi

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>Dönüş Değeri

Bir [GUID yapısı](/windows/win32/api/guiddef/ns-guiddef-guid).

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
