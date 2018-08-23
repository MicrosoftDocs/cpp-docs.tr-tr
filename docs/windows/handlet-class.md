---
title: HandleT sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT
dev_langs:
- C++
helpviewer_keywords:
- HandleT class
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6da9451d6f009bad6163efec23bb6f920a56df49
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42590536"
---
# <a name="handlet-class"></a>HandleT Sınıfı

Bir tutamacı nesneyi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename HandleTraits
>
class HandleT;
```

### <a name="parameters"></a>Parametreler

*HandleTraits*  
Örneği [HandleTraits](../windows/handletraits-structure.md) ortak bir tanıtıcı özelliklerini tanımlayan bir yapıda.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`Traits`|İçin bir eşanlamlı `HandleTraits`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[HandleT::HandleT Oluşturucusu](../windows/handlet-handlet-constructor.md)|Yeni bir örneğini başlatır **HandleT** sınıfı.|
|[HandleT::~HandleT Yıkıcısı](../windows/handlet-tilde-handlet-destructor.md)|Örneği başlatılmasını geri alır **HandleT** sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[HandleT::Attach Metodu](../windows/handlet-attach-method.md)|Belirtilen tanıtıcı geçerli ilişkilendirir **HandleT** nesne.|
|[HandleT::Close Metodu](../windows/handlet-close-method.md)|Geçerli kapatır **HandleT** nesne.|
|[HandleT::Detach Metodu](../windows/handlet-detach-method.md)|Geçerli ayırır **HandleT** , temel alınan tanıtıcısını nesne.|
|[HandleT::Get Metodu](../windows/handlet-get-method.md)|Temel alınan tanıtıcısının değerini alır.|
|[HandleT::IsValid Metodu](../windows/handlet-isvalid-method.md)|Belirtir olup olmadığını geçerli **HandleT** nesnesi bir işleyici temsil eder.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[HandleT::InternalClose Metodu](../windows/handlet-internalclose-method.md)|Geçerli kapatır **HandleT** nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[HandleT::operator= İşleci](../windows/handlet-operator-assign-operator.md)|Belirtilen değer taşır **HandleT** geçerli nesneye **HandleT** nesne.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[HandleT::handle_ Veri Üyesi](../windows/handlet-handle-data-member.md)|Tarafından temsil edilen tanıtıcı içeren **HandleT** nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HandleT`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)