---
title: SimpleClassFactory Sınıfı
ms.date: 09/7/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory
- module/Microsoft::WRL::SimpleClassFactory::CreateInstance
helpviewer_keywords:
- Microsoft::WRL::SimpleClassFactory class
- Microsoft::WRL::SimpleClassFactory::CreateInstance method
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
ms.openlocfilehash: 9a4c169944d56b693efa681bf7089636477012ea
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54334943"
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory Sınıfı

Bir temel sınıf oluşturmak için temel bir mekanizma sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Base>
class SimpleClassFactory : public ClassFactory<>;
```

### <a name="parameters"></a>Parametreler

*temel*<br/>
Temel sınıf.

## <a name="remarks"></a>Açıklamalar

Temel sınıfın varsayılan bir oluşturucu sağlamanız gerekir.

Aşağıdaki kod örneğinde nasıl kullanılacağını gösterir `SimpleClassFactory` ile [ActivatableClassWithFactoryEx](activatableclass-macros.md) makrosu.

`ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[SimpleClassFactory::CreateInstance Metodu](#createinstance)|Belirtilen arabirim bir örneğini oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ClassFactory`

`SimpleClassFactory`

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="createinstance"></a>Simpleclassfactory::CreateInstance yöntemi

Belirtilen arabirim bir örneğini oluşturur.

```cpp
STDMETHOD( CreateInstance )(
   _Inout_opt_ IUnknown* pUnkOuter,
   REFIID riid,
   _Deref_out_ void** ppvObject
);
```

#### <a name="parameters"></a>Parametreler

*pUnkOuter*<br/>
Olmalıdır `nullptr`; Aksi takdirde CLASS_E_NOAGGREGATION dönüş değeridir.

SimpleClassFactory toplama desteklemiyor. Oluşturulan nesne bir toplamanın parçası toplama desteklenen ve *pUnkOuter* denetlemek için bir işaretçi olabilir `IUnknown` toplamanın arabirimi.

*riid*<br/>
Nesnenin kimliği oluşturmak için arabirim.

*ppvObject*<br/>
Bu işlem tamamlandığında, işaretçi tarafından belirtilen nesnede örneğine *riid* parametresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Varsa `__WRL_STRICT__` olan tanımlanan, türetilen sınıf şablonu parametresinde belirtilen temel sınıf değil, bir onay hata yayıldığını [RuntimeClass](runtimeclass-class.md), ya da ClassicCom veya WinRtClassicComMix ile yapılandırılmamış [ RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırma değeri.
