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
ms.openlocfilehash: 924b9d2c30f11e6f0444d9c647807f1c86dcc411
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373556"
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory Sınıfı

Taban sınıf oluşturmak için temel bir mekanizma sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Base>
class SimpleClassFactory : public ClassFactory<>;
```

### <a name="parameters"></a>Parametreler

*Temel*<br/>
Taban sınıf.

## <a name="remarks"></a>Açıklamalar

Taban sınıf varsayılan bir oluşturucu sağlaması gerekir.

Aşağıdaki kod örneği `SimpleClassFactory` [ActivatableClassWithFactoryEx](activatableclass-macros.md) makrosu ile nasıl kullanılacağını gösterir.

`ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[SimpleClassFactory::CreateInstance Metodu](#createinstance)|Belirtilen arabirimin bir örneğini oluşturur.|

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

**Üstbilgi:** module.h

**Ad alanı:** Microsoft::WRL

## <a name="simpleclassfactorycreateinstance-method"></a><a name="createinstance"></a>SimpleClassFactory::CreateInstance Yöntemi

Belirtilen arabirimin bir örneğini oluşturur.

```cpp
STDMETHOD( CreateInstance )(
   _Inout_opt_ IUnknown* pUnkOuter,
   REFIID riid,
   _Deref_out_ void** ppvObject
);
```

#### <a name="parameters"></a>Parametreler

*pUnkOuter*<br/>
Olmalı `nullptr`; aksi takdirde, iade değeri CLASS_E_NOAGGREGATION.

SimpleClassFactory toplamayı desteklemez. Toplama desteklenir ve oluşturulan nesne bir agreganın parçası ysa, *pUnkOuter* toplamın `IUnknown` denetleme arabirimine işaretçi olur.

*Riid*<br/>
Oluşturulacak nesnenin arabirim kimliği.

*ppvNesne*<br/>
Bu işlem tamamlandığında, *riid* parametresi tarafından belirtilen nesnenin bir örneğini işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

`__WRL_STRICT__` Tanımlanırsa, sınıf şablonu parametresinde belirtilen taban sınıf [RuntimeClass'tan](runtimeclass-class.md)türetilmemişse veya ClassicCom veya WinRtClassicComMix [RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırma değeriyle yapılandırılmamışsa bir ileri savunma hatası yayımlanır.
