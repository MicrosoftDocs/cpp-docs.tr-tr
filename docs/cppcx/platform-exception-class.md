---
title: 'Platform:: Exception sınıfı'
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
ms.openlocfilehash: bfdd8b3df720073e6b4a19cdb5b34db23e659fd0
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90741976"
---
# <a name="platformexception-class"></a>Platform:: Exception sınıfı

Uygulama yürütme sırasında oluşan hataları temsil eder. Özel özel durum sınıfları öğesinden türetilemez `Platform::Exception` . Özel bir özel durum gerekiyorsa, `Platform::COMException` uygulamasını kullanabilir ve uygulamaya özel bır HRESULT belirtebilirsiniz.

## <a name="syntax"></a>Syntax

```cpp
public ref class Exception : Object,    IException,    IPrintable,    IEquatable
```

### <a name="members"></a>Üyeler

`Exception`Sınıfı sınıfından `Object` ve `IException` , `IPrintable` , ve `IEquatable` arabirimlerinden devralır.

`Exception`Sınıfı ayrıca aşağıdaki üye türlerine sahiptir.

### <a name="constructors"></a>Oluşturucular

|Üye|Description|
|------------|-----------------|
|[Özel durum:: Exception](#ctor)|`Exception` sınıfının yeni bir örneğini başlatır.|

### <a name="methods"></a>Yöntemler

`Exception`Sınıfı `Equals()` , `Finalize()` `GetHashCode()` `GetType()` `MemberwiseClose()` `ToString()` [Platform:: Object sınıfından](../cppcx/platform-object-class.md),,,, ve yöntemlerini devralır. `Exception`Sınıfında Ayrıca aşağıdaki yöntem de bulunur.

|Üye|Description|
|------------|-----------------|
|[Özel durum:: CreateException](#createexception)|Belirtilen HRESULT değerini temsil eden bir özel durum oluşturur.|

### <a name="properties"></a>Özellikler

Özel durum sınıfı aşağıdaki özelliklere de sahiptir.

|Üye|Description|
|------------|-----------------|
|[Özel durum:: HResult](#hresult)|Özel duruma karşılık gelen HRESULT.|
|[Özel durum:: Ileti](#message)|Özel durumu açıklayan bir ileti. Bu değer salt okunurdur ve oluşturulduktan sonra değiştirilemez `Exception` .|

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Meta veri:** platform. winmd

## <a name="exceptioncreateexception-method"></a><a name="createexception"></a> Exception:: CreateException yöntemi

Belirtilen HRESULT değerinden Platform:: Exception ^ oluşturur.

### <a name="syntax"></a>Söz dizimi

```cpp
Exception^ CreateException(int32 hr);
Exception^ CreateException(int32 hr, Platform::String^ message);
```

### <a name="parameters"></a>Parametreler

*sa*<br/>
Genellikle COM yöntemine yapılan çağrıdan alacağınız bir HRESULT değeri. Değer, S_OK eşittir 0 ise, bu yöntem [Platform:: InvalidArgumentException](../cppcx/platform-invalidargumentexception-class.md) oluşturur, çünkü başarılı olan com metotları özel durumlar oluşturmaz.

*İleti*<br/>
Hatayı açıklayan bir dize.

### <a name="return-value"></a>Dönüş Değeri

HRESULT hatasını temsil eden bir özel durum.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi, örneğin bir COM arabirimi yöntemine yapılan çağrıdan döndürülen HRESULT dışında bir özel durum oluşturmak için kullanın. Özel bir ileti sağlamak için bir dize ^ parametresi alan aşırı yüklemeyi kullanabilirsiniz.

Yalnızca HRESULT içeren bir [Platform:: COMException](../cppcx/platform-comexception-class.md) oluşturmak yerine kesin olarak yazılmış bir özel durum oluşturmak Için CreateException kullanılması önemle önerilir.

## <a name="exceptionexception-constructor"></a><a name="ctor"></a> Özel durum:: Exception Oluşturucusu

Özel durum sınıfının yeni bir örneğini başlatma.

### <a name="syntax"></a>Söz dizimi

```cpp
Exception(int32 hresult);
Exception(int32 hresult, ::Platform::String^ message);
```

### <a name="parameters"></a>Parametreler

*HRESULT*<br/>
Özel durumla temsil edilen HRESULT hatası.

*İleti*<br/>
Özel durumla ilişkili, seçkin metin gibi kullanıcı tarafından belirtilen bir ileti. Genel olarak, hatanın nasıl ve neden gerçekleştiği hakkında mümkün olduğunca özel açıklayıcı bir ileti sağlamak için ikinci aşırı yüklemeyi tercih etmelisiniz.

## <a name="exceptionhresult-property"></a><a name="hresult"></a> Exception:: HResult özelliği

Özel duruma karşılık gelen HRESULT.

### <a name="syntax"></a>Syntax

```cpp
public:
    property int HResult { int get(); }
```

### <a name="property-value"></a>Özellik Değeri

HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Çoğu özel durum, HRESULT değerleri olarak döndürülen COM hataları olarak başlatılır. C++/CX bu değerleri Platform:: Exception ^ nesnelerine dönüştürür ve bu özellik özgün hata kodunun değerini depolar.

## <a name="exceptionmessage-property"></a><a name="message"></a> Exception:: Message özelliği

Hatayı açıklayan ileti.

### <a name="syntax"></a>Syntax

```cpp
public:property String^ Message;
```

### <a name="property-value"></a>Özellik Değeri

Windows Çalışma Zamanı olan özel durumlarda, bu hatanın sistem tarafından sağlanan bir açıklamasıdır.

### <a name="remarks"></a>Açıklamalar

Windows 8 ' de, bu özellik salt okunurdur çünkü bu Windows Çalışma Zamanı sürümündeki özel durumlar yalnızca HRESULTS olarak ABı üzerinden aktarılmalıdır. Windows 8.1, daha zengin özel durum bilgileri ABı arasında taşınır ve diğer bileşenlerin programlı olarak erişebileceği özel bir ileti sağlayabilirsiniz. Daha fazla bilgi için bkz. [özel durumlar (C++/CX)](../cppcx/exceptions-c-cx.md).

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
