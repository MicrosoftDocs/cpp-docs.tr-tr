---
title: RuntimeClassBaseT Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
helpviewer_keywords:
- Microsoft::WRL::Details::RuntimeClassBaseT structure
- Microsoft::WRL::Details::RuntimeClassBaseT::AsIID method
- Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS method
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
ms.openlocfilehash: 06a9f73e00d541b0e5bcbe20c57befe4a67c5132
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375730"
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <unsigned int RuntimeClassTypeT>
friend struct Details::RuntimeClassBaseT;
```

### <a name="parameters"></a>Parametreler

*RuntimeClassTypeT*<br/>
Bir veya daha fazla [RuntimeClassType](runtimeclasstype-enumeration.md) sayıtaycı belirten bir bayrak alanı.

## <a name="remarks"></a>Açıklamalar

İşlemler ve `QueryInterface` arabirim tonları almak için yardımcı yöntemler sağlar.

## <a name="members"></a>Üyeler

### <a name="protected-methods"></a>Korumalı Yöntemler

Adı                                                         | Açıklama
------------------------------------------------------------ | -----------------------------------------------------------------------------
[RuntimeClassBaseT::AsIID](#asiid)                           | Belirtilen arabirim kimliği için bir işaretçi alır.
[RuntimeClassBaseT::GetImplementedIIDS](#getimplementediids) | Belirli bir tür tarafından uygulanan bir dizi arabirim dis'i alır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`RuntimeClassBaseT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** implements.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="runtimeclassbasetasiid"></a><a name="asiid"></a>RuntimeClassBaseT::AsIID

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
template<typename T>
__forceinline static HRESULT AsIID(
   _In_ T* implements,
   REFIID riid,
   _Deref_out_ void **ppvObject
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Parametre *riid*tarafından belirtilen arabirim kimliğini uygulayan bir tür.

*Uygulayan*<br/>
Şablon parametresi *T*tarafından belirtilen türden bir değişken.

*Riid*<br/>
Alınacak arayüz kimliği.

*ppvNesne*<br/>
Bu işlem başarılı olursa, parametre *riid*tarafından belirtilen arabirimin işaretçi-to-a-pointer.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı açıklayan bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Belirtilen arabirim kimliği için bir işaretçi alır.

## <a name="runtimeclassbasetgetimplementediids"></a><a name="getimplementediids"></a>RuntimeClassBaseT::GetImplementedIIDS

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
template<typename T>
__forceinline static HRESULT GetImplementedIIDS(
   _In_ T* implements,
   _Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
*Uygulama* parametresi türü.

*Uygulayan*<br/>
*T*parametresi ile belirtilen türe işaretçi .

*iidSay*<br/>
Alınacak en fazla arabirim numarası.

*iids*<br/>
Bu işlem başarıyla tamamlanırsa, *T*türüne göre uygulanan arabirim ilikleri dizisi.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı açıklayan bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Belirli bir tür tarafından uygulanan bir dizi arabirim dis'i alır.
