---
title: ComPtrRef sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRef class
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d4ec1139efae422035ef34030cfcffcc5547f0a2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418508"
---
# <a name="comptrref-class"></a>ComPtrRef Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename T
>
class ComPtrRef : public ComPtrRefBase<T>;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
A [ComPtr\<T >](../windows/comptr-class.md) türü veya tür, kesmenin tarafından temsil edilen arabirim sınıfından türetilen `ComPtr`.

## <a name="remarks"></a>Açıklamalar

Bir nesne türü bir başvuruyu temsil eder `ComPtr<T>`.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[ComPtrRef::ComPtrRef Oluşturucusu](../windows/comptrref-comptrref-constructor.md)|Yeni bir örneğini başlatır **ComPtrRef** belirtilen işaretçisinden sınıfa **ComPtrRef** nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ComPtrRef::GetAddressOf Metodu](../windows/comptrref-getaddressof-method.md)|Adresi geçerli tarafından temsil edilen arabirimi için bir işaretçi alır **ComPtrRef** nesne.|
|[ComPtrRef::ReleaseAndGetAddressOf Metodu](../windows/comptrref-releaseandgetaddressof-method.md)|Geçerli siler **ComPtrRef** nesnesi ve bir işaretçi-için-a-işaretçi tarafından temsil arabirimi döndürür **ComPtrRef** nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[ComPtrRef::operator InterfaceType** İşleci](../windows/comptrref-operator-interfacetype-star-star-operator.md)|Geçerli siler **ComPtrRef** nesnesi ve bir işaretçi-için-a-işaretçi tarafından temsil arabirimi döndürür **ComPtrRef** nesne.|
|[ComPtrRef::operator T* İşleci](../windows/comptrref-operator-t-star-operator.md)|Değerini döndürür [ptr_](../windows/comptrrefbase-ptr-data-member.md) geçerli ComPtrRef nesnenin veri üyesi.|
|[ComPtrRef::operator void** İşleci](../windows/comptrref-operator-void-star-star-operator.md)|Geçerli siler **ComPtrRef** nesne, işaretçi tarafından temsil arabirimine bıraktığı **ComPtrRef** nesnesi olarak bir işaretçiyi-için-işaretçi- **void**ve ardından cast işaretçiyi döndürür.|
|[ComPtrRef::operator* İşleci](../windows/comptrref-operator-star-operator.md)|Geçerli tarafından temsil edilen arabirim işaretçisi alır **ComPtrRef** nesne.|
|[ComPtrRef::operator== İşleci](../windows/comptrref-operator-equality-operator.md)|Belirtir olup iki **ComPtrRef** nesneler.|
|[ComPtrRef::operator!= İşleci](../windows/comptrref-operator-inequality-operator.md)|Belirtir olup iki **ComPtrRef** nesneler eşit değildir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ComPtrRefBase`

`ComPtrRef`

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)