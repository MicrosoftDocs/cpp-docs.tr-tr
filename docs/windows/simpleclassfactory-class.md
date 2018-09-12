---
title: SimpleClassFactory sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/7/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory
- module/Microsoft::WRL::SimpleClassFactory::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::SimpleClassFactory class
- Microsoft::WRL::SimpleClassFactory::CreateInstance method
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b20cbb906676705113bd1a84884cc5719b8272bf
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691451"
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory Sınıfı

Bir temel sınıf oluşturmak için temel bir mekanizma sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Base>
class SimpleClassFactory : public ClassFactory<>;
```

### <a name="parameters"></a>Parametreler

*temel*  
Temel sınıf.

## <a name="remarks"></a>Açıklamalar

Temel sınıfın varsayılan bir oluşturucu sağlamanız gerekir.

Aşağıdaki kod örneğinde nasıl kullanılacağını gösterir `SimpleClassFactory` ile [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) makrosu.

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

*pUnkOuter*  
Olmalıdır `nullptr`; Aksi takdirde CLASS_E_NOAGGREGATION dönüş değeridir.

SimpleClassFactory toplama desteklemiyor. Oluşturulan nesne bir toplamanın parçası toplama desteklenen ve *pUnkOuter* denetlemek için bir işaretçi olabilir `IUnknown` toplamanın arabirimi.

*riid*  
Nesnenin kimliği oluşturmak için arabirim.

*ppvObject*  
Bu işlem tamamlandığında, işaretçi tarafından belirtilen nesnede örneğine *riid* parametresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Varsa `__WRL_STRICT__` olan tanımlanan, türetilen sınıf şablonu parametresinde belirtilen temel sınıf değil, bir onay hata yayıldığını [RuntimeClass](../windows/runtimeclass-class.md), ya da ClassicCom veya WinRtClassicComMix ile yapılandırılmamış [ RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırma değeri.
