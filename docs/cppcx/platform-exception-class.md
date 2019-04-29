---
title: Platform::Exception sınıfı
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
ms.openlocfilehash: d37d55c56e3c23d8d9129c985cb4272d2e3ee47a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368740"
---
# <a name="platformexception-class"></a>Platform::Exception sınıfı

Uygulama yürütme sırasında oluşan hataları temsil eder. Özel durum sınıfları öğesinden türetilemez `Platform::Exception`. Bir özel durum gerektiriyorsa, kullanabileceğiniz `Platform::COMException` ve uygulamaya özel HRESULT'ı belirtin.

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class Exception : Object,    IException,    IPrintable,    IEquatable
```

### <a name="members"></a>Üyeler

`Exception` Sınıfının devraldığı `Object` sınıfı ve `IException`, `IPrintable`, ve `IEquatable` arabirimleri.

`Exception` Sınıfı üyelerinin aşağıdaki türleri de vardır.

### <a name="constructors"></a>Oluşturucular

|Üye|Açıklama|
|------------|-----------------|
|[Exception::Exception](#ctor)|Yeni bir örneğini başlatır `Exception` sınıfı.|

### <a name="methods"></a>Yöntemler

`Exception` Sınıfından devralan `Equals()`, `Finalize()`,`GetHashCode()`,`GetType()`,`MemberwiseClose()`, ve `ToString()` yöntemlerinden [Platform::Object sınıfı](../cppcx/platform-object-class.md). `Exception` Sınıfında aşağıdaki yöntemi de vardır.

|Üye|Açıklama|
|------------|-----------------|
|[Exception::CreateException](#createexception)|Belirtilen HRESULT değerini temsil eden bir özel durum oluşturur.|

### <a name="properties"></a>Özellikler

Özel durum sınıfı ayrıca aşağıdaki özelliklere sahiptir.

|Üye|Açıklama|
|------------|-----------------|
|[Exception::HResult](#hresult)|Özel duruma karşılık gelen HRESULT.|
|[Exception::Message](#message)|Özel durumu açıklayan bir ileti. Bu değer salt okunur ve sonra değiştirilemez `Exception` oluşturulur.|

### <a name="requirements"></a>Gereksinimler

**En düşük desteklenen istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** Platform

**Meta veri:** platform.winmd

## <a name="createexception"></a> Exception::CreateException yöntemi

Bir Platform::Exception oluşturur ^ belirtilen bir HRESULT değerinden.

### <a name="syntax"></a>Sözdizimi

```cpp
Exception^ CreateException(int32 hr);
Exception^ CreateException(int32 hr, Platform::String^ message);
```

### <a name="parameters"></a>Parametreler

*İK*<br/>
Normalde bir COM yöntem çağrısından alabilirsiniz HRESULT değerini. Değer için S_OK eşit olan 0 ise bu yöntemin oluşturduğu [Platform::ınvalidargumentexception](../cppcx/platform-invalidargumentexception-class.md) çünkü başarılı COM yöntemleri özel durum oluşturmamalıdır.

*message*<br/>
Hatayı açıklayan bir dize.

### <a name="return-value"></a>Dönüş Değeri

HRESULT hatası temsil eden bir özel durum.

### <a name="remarks"></a>Açıklamalar

Bir özel durum dışında Örneğin, bir COM arabirimi yöntemini çağrısından döndürülen HRESULT oluşturmak için bu yöntemi kullanın. Bir dizeyi alan aşırı yüklemesini kullanabilirsiniz ^ parametresini kullanarak özel bir ileti sağlayın.

Kesin türü kesin belirlenmiş bir özel durum oluşturmak için CreateException kullanılacak önerilen yerine oluşturma bir [Platform::COMException](../cppcx/platform-comexception-class.md) yalnızca HRESULT'ı içerir.

## <a name="ctor"></a>  Exception::Exception Oluşturucusu

Özel durum sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
Exception(int32 hresult);
Exception(int32 hresult, ::Platform::String^ message);
```

### <a name="parameters"></a>Parametreler

*HRESULT*<br/>
Özel durum tarafından temsil edilen HRESULT hatası.

*message*<br/>
Düzenleyici metin gibi kullanıcı tanımlı bir ileti, şu özel durum ile ilişkilidir. Genel hata oluştu, nasıl ve neden hakkında mümkün olduğunca açıklayıcı bir iletisi sağlamak için ikinci aşırı yükleme tercih etmelisiniz.

## <a name="hresult"></a>  Exception::HResult özelliği

Özel duruma karşılık gelen HRESULT.

### <a name="syntax"></a>Sözdizimi

```cpp
public:
    property int HResult { int get(); }
```

## <a name="property-value"></a>Özellik Değeri

HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Çoğu özel durumlar HRESULT değerleri döndüren COM hata olarak başlar. C++/CX Platform::Exception bu değerleri dönüştürür ^ nesneleri ve bu özellik, özgün hata kodu değerini depolar.

## <a name="message"></a> Exception::Message özelliği

Hatayı açıklayan ileti.

### <a name="syntax"></a>Sözdizimi

```cpp
public:property String^ Message;
```

## <a name="property-value"></a>Özellik Değeri

Windows çalışma zamanı'nda kaynaklanan özel durumları, sistem tarafından sağlanmış bir hatanın açıklamasını budur.

### <a name="remarks"></a>Açıklamalar

Bu sürüm Windows çalışma zamanı özel durumları HRESULTS olarak yalnızca ABI üzerinden taşınan çünkü Windows 8'de, bu özellik salt okunur. Windows 8.1, daha zengin özel durum bilgilerini ABI arasında taşınır ve diğer bileşenleri programlı olarak erişmek için özel bir ileti sağlayabilir. Daha fazla bilgi için [özel durumlar (C++/CX)](../cppcx/exceptions-c-cx.md).

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
