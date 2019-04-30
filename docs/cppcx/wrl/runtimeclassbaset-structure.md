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
ms.openlocfilehash: 5d93b3e86e7ba105a42ccbedbbf44c51ada97bbd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403171"
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
Bir veya daha fazla belirten bayraklar alanı [RuntimeClassType](runtimeclasstype-enumeration.md) numaralandırıcılar.

## <a name="remarks"></a>Açıklamalar

İçin yardımcı yöntemleri sağlar `QueryInterface` işlemler ve başlangıç arabirim kimliği.

## <a name="members"></a>Üyeler

### <a name="protected-methods"></a>Korumalı Yöntemler

Ad                                                         | Açıklama
------------------------------------------------------------ | -----------------------------------------------------------------------------
[Runtimeclassbaset::asııd](#asiid)                           | Belirtilen arabirim kimliği. bir işaretçi alır.
[Runtimeclassbaset::getımplementedııds](#getimplementediids) | Belirtilen bir tür tarafından uygulanan kimlikleri arabiriminin dizisini alır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`RuntimeClassBaseT`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="asiid"></a>Runtimeclassbaset::asııd

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
Parametresi tarafından belirtilen arabirim kimliği uygulayan bir tür *riid*.

*implements*<br/>
Şablon parametresi tarafından belirtilen türde bir değişken *T*.

*riid*<br/>
Alınacak arabirim kimliği.

*ppvObject*<br/>
Bu işlem başarılı olursa, bir işaretçi bir-işaretçiye arabirimi için belirtilen parametre tarafından *riid*.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Belirtilen arabirim kimliği. bir işaretçi alır.

## <a name="getimplementediids"></a>Runtimeclassbaset::getımplementedııds

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
Türünü *uygulayan* parametresi.

*implements*<br/>
Parametresi tarafından belirtilen türe işaretçi *T*.

*Iidcount*<br/>
Arabirim kimlikleri alınacak maksimum sayısı.

*IID'leri*<br/>
Bu işlem kimlikleri tür tarafından uygulanan arabirimi dizisi başarıyla tamamlanırsa *T*.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Belirtilen bir tür tarafından uygulanan kimlikleri arabiriminin dizisini alır.
