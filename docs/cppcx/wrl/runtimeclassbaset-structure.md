---
description: 'Daha fazla bilgi edinin: RuntimeClassBaseT yapısı'
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
ms.openlocfilehash: 48f03a5d54eba455b60646ed47c48e228f07863e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135297"
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <unsigned int RuntimeClassTypeT>
friend struct Details::RuntimeClassBaseT;
```

### <a name="parameters"></a>Parametreler

*RuntimeClassTypeT*<br/>
Bir veya daha fazla [RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırıcıları belirten bayrakların alanı.

## <a name="remarks"></a>Açıklamalar

İşlemler için yardımcı yöntemler sağlar `QueryInterface` ve arabirim kimliklerini elde edin.

## <a name="members"></a>Üyeler

### <a name="protected-methods"></a>Korumalı Yöntemler

Ad                                                         | Açıklama
------------------------------------------------------------ | -----------------------------------------------------------------------------
[RuntimeClassBaseT:: AsIID](#asiid)                           | Belirtilen arabirim KIMLIĞINE bir işaretçi alır.
[RuntimeClassBaseT:: Getımplementediıds](#getimplementediids) | Belirtilen bir tür tarafından uygulanan arabirim kimlikleri dizisini alır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`RuntimeClassBaseT`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="runtimeclassbasetasiid"></a><a name="asiid"></a> RuntimeClassBaseT:: AsIID

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

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
Parametresi *riıd* tarafından BELIRTILEN arabirim kimliğini uygulayan bir tür.

*uygular*<br/>
Şablon parametresi *T* tarafından belirtilen türde bir değişken.

*riıd*<br/>
Alınacak arabirim KIMLIĞI.

*ppvObject*<br/>
Bu işlem başarılı olursa, parametre *riıd* tarafından belirtilen arabirime işaretçiden işaretçiden işaretçisi işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Belirtilen arabirim KIMLIĞINE bir işaretçi alır.

## <a name="runtimeclassbasetgetimplementediids"></a><a name="getimplementediids"></a> RuntimeClassBaseT:: Getımplementediıds

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

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
*Implements* parametresinin türü.

*uygular*<br/>
*T* parametresiyle belirtilen türe yönelik işaretçi.

*IidCount*<br/>
Alınacak en fazla arabirim kimliği sayısı.

*IID*<br/>
Bu işlem başarıyla tamamlanırsa, tür *T* tarafından uygulanan arabirim kimliklerinin bir dizisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Belirtilen bir tür tarafından uygulanan arabirim kimlikleri dizisini alır.
