---
description: 'Daha fazla bilgi edinin: SimpleClassFactory sınıfı'
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
ms.openlocfilehash: cd771909790f80048d8fee678b842f820e2f7be2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135206"
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory Sınıfı

Temel sınıf oluşturmak için temel bir mekanizma sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename Base>
class SimpleClassFactory : public ClassFactory<>;
```

### <a name="parameters"></a>Parametreler

*Temel*<br/>
Temel sınıf.

## <a name="remarks"></a>Açıklamalar

Temel sınıf varsayılan bir Oluşturucu sağlamalıdır.

Aşağıdaki kod örneği, `SimpleClassFactory` [ActivatableClassWithFactoryEx](activatableclass-macros.md) makrosu ile nasıl kullanılacağını göstermektedir.

`ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
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

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL

## <a name="simpleclassfactorycreateinstance-method"></a><a name="createinstance"></a> SimpleClassFactory:: CreateInstance yöntemi

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
Olmalıdır **`nullptr`** ; Aksi takdirde, dönüş değeri CLASS_E_NOAGGREGATION.

SimpleClassFactory toplamayı desteklemiyor. Toplama destekleniyorsa ve oluşturulmakta olan nesne bir toplamanın parçasıysa, *pUnkOuter* toplamanın denetim arabirimine bir işaretçi olacaktır `IUnknown` .

*riıd*<br/>
Oluşturulacak nesnenin arabirim KIMLIĞI.

*ppvObject*<br/>
Bu işlem tamamlandığında, *riıd* parametresi tarafından belirtilen nesnenin örneğine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

`__WRL_STRICT__`Tanımlanmışsa, sınıf şablonu parametresinde belirtilen temel sınıf [RuntimeClass](runtimeclass-class.md)'dan türetilmemişse veya ClassicCom veya WinRtClassicComMix [RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırma değeriyle yapılandırılmamışsa bir onaylama hatası yayınlanır.
