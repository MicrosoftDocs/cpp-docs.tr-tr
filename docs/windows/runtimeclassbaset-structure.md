---
title: RuntimeClassBaseT yapısı | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::RuntimeClassBaseT structure
- Microsoft::WRL::Details::RuntimeClassBaseT::AsIID method
- Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS method
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c46e89dc11f4c6fe216cfd61c3222a9c52d9e45
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789143"
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
Bir veya daha fazla belirten bayraklar alanı [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırıcılar.

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

*Uygulayan*<br/>
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

*Uygulayan*<br/>
Parametresi tarafından belirtilen türe işaretçi *T*.

*Iidcount*<br/>
Arabirim kimlikleri alınacak maksimum sayısı.

*IID'leri*<br/>
Bu işlem kimlikleri tür tarafından uygulanan arabirimi dizisi başarıyla tamamlanırsa *T*.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Belirtilen bir tür tarafından uygulanan kimlikleri arabiriminin dizisini alır.
