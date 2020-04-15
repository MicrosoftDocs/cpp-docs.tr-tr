---
title: Platform::Özel Durum Sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception::Exception
- VCCORLIB/Platform::Exception::CreateException
- VCCORLIB/Platform::Exception::HResult
- VCCORLIB/Platform::Exception::Message
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: ca1d5a67-3a5a-48fe-8099-f9c38a2d2dce
ms.openlocfilehash: 4604769d9d1bc5fa848d15459327dc87d82f7016
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363775"
---
# <a name="platformexception-class"></a>Platform::Özel Durum Sınıfı

Uygulama yürütme sırasında oluşan hataları temsil eder. Özel özel durum sınıfları' `Platform::Exception`dan türetedilemez. Özel bir özel durum gerektiriyorsanız, uygulamaya özgü bir HRESULT kullanabilir `Platform::COMException` ve belirtebilirsiniz.

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class Exception : Object,    IException,    IPrintable,    IEquatable
```

### <a name="members"></a>Üyeler

`Object` Sınıf, `Exception` sınıf ve `IException`, `IPrintable`ve `IEquatable` arabirimlerden devralır.

Sınıfın `Exception` da aşağıdaki tür üyeleri vardır.

### <a name="constructors"></a>Oluşturucular

|Üye|Açıklama|
|------------|-----------------|
|[Özel Durum::Özel Durum](#ctor)|`Exception` sınıfının yeni bir örneğini başlatır.|

### <a name="methods"></a>Yöntemler

`Exception` Sınıf, `Equals()`, `Finalize()`,`GetHashCode()``GetType()`,`MemberwiseClose()`, `ToString()` ve yöntemleri [Platformdan devralır::Nesne Sınıfı](../cppcx/platform-object-class.md). Sınıf `Exception` da aşağıdaki yönteme sahiptir.

|Üye|Açıklama|
|------------|-----------------|
|[Özel Durum::Create Exception](#createexception)|Belirtilen HRESULT değerini temsil eden bir özel durum oluşturur.|

### <a name="properties"></a>Özellikler

Özel Durum sınıfı da aşağıdaki özelliklere sahiptir.

|Üye|Açıklama|
|------------|-----------------|
|[Özel Durum::HResult](#hresult)|Özel durum karşılık gelen HRESULT.|
|[Özel Durum::İleti](#message)|Özel durumu açıklayan bir ileti. Bu değer salt okunur ve oluşturulduktan `Exception` sonra değiştirilemez.|

### <a name="requirements"></a>Gereksinimler

**Minimum desteklenen istemci:** Windows 8

**Minimum desteklenen sunucu:** Windows Server 2012

**Ad alanı:** Platform

**Meta veriler:** platform.winmd

## <a name="exceptioncreateexception-method"></a><a name="createexception"></a>Özel Durum::Create Exception Yöntemi

Belirli bir HRESULT değerinden bir Platform::Özel Durum^ oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
Exception^ CreateException(int32 hr);
Exception^ CreateException(int32 hr, Platform::String^ message);
```

### <a name="parameters"></a>Parametreler

*Hr*<br/>
Genellikle bir çağrıdan COM yöntemine aldığınız bir HRESULT değeri. Değer S_OK eşit olan 0 ise, bu yöntem [Platform atar::GeçersizArgumentException](../cppcx/platform-invalidargumentexception-class.md) Çünkü başarılı COM yöntemleri özel durumlar atmamalıdır.

*İleti*<br/>
Hatayı açıklayan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Hata HRESULT temsil eden bir özel durum.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi, örneğin bir çağrıdan COM arabirimi yöntemine döndürülen bir HRESULT'dan bir özel durum oluşturmak için kullanın. Özel bir ileti sağlamak için String^ parametresi alan aşırı yüklemeyi kullanabilirsiniz.

Yalnızca HRESULT içeren bir [Platform::COMException](../cppcx/platform-comexception-class.md) oluşturmak yerine güçlü bir şekilde yazılan bir özel durum oluşturmak için CreateException'ı kullanmanız önerilir.

## <a name="exceptionexception-constructor"></a><a name="ctor"></a>Özel Durum::Özel Durum Oluşturucusu

Özel Durum sınıfının yeni bir örneğini intialize eder.

### <a name="syntax"></a>Sözdizimi

```cpp
Exception(int32 hresult);
Exception(int32 hresult, ::Platform::String^ message);
```

### <a name="parameters"></a>Parametreler

*Hresult*<br/>
Özel durum tarafından temsil edilen hata HRESULT.

*İleti*<br/>
Özel durumla ilişkili, önceden yazılmış metin gibi kullanıcı tarafından belirtilen ileti. Genel olarak, hatanın nasıl ve neden oluştuğu hakkında mümkün olduğunca spesifik açıklayıcı bir ileti sağlamak için ikinci aşırı yüklemeyi tercih etmeniz gerekir.

## <a name="exceptionhresult-property"></a><a name="hresult"></a>Özel Durum::HResult Özelliği

Özel durum karşılık gelen HRESULT.

### <a name="syntax"></a>Sözdizimi

```cpp
public:
    property int HResult { int get(); }
```

## <a name="property-value"></a>Özellik Değeri

Bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Çoğu özel durum, HRESULT değerleri olarak döndürülen COM hataları olarak başlar. C++/CX bu değerleri Platform::Exception^ nesnelerine dönüştürür ve bu özellik özgün hata kodunun değerini depolar.

## <a name="exceptionmessage-property"></a><a name="message"></a>Özel Durum::İleti Özelliği

Hatayı açıklayan ileti.

### <a name="syntax"></a>Sözdizimi

```cpp
public:property String^ Message;
```

## <a name="property-value"></a>Özellik Değeri

Windows Runtime kaynaklanan özel durumlar, bu hatanın sistem tarafından sağlanan bir açıklamasıdır.

### <a name="remarks"></a>Açıklamalar

Windows 8'de, Windows Runtime'ın bu sürümündeki özel durumlar ABI'de yalnızca HRESULTS olarak taşındığı için bu özellik salt okunur. Windows 8.1'de, daha zengin özel durum bilgileri ABI genelinde taşınır ve diğer bileşenlerin programlı olarak erişebileceği özel bir ileti sağlayabilirsiniz. Daha fazla bilgi için özel [durumlar (C++/CX)](../cppcx/exceptions-c-cx.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
