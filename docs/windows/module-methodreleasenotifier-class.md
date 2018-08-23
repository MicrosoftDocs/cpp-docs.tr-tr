---
title: Module::MethodReleaseNotifier sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- MethodReleaseNotifier class
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cee634ab62e699b4de6af54a57b0fe3d6b5e9a40
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606614"
---
# <a name="modulemethodreleasenotifier-class"></a>Module::MethodReleaseNotifier Sınıfı

Geçerli modül içinde son nesnenin yayımlandığında bir olay işleyici çağırır. Olay işleyicisi, bir nesne ve onun yöntemi için işaretçi üye tarafından belirtilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
class MethodReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>Parametreler

*T*  
Olay işleyicisi üye işlevi olan nesnenin türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Module::MethodReleaseNotifier::MethodReleaseNotifier Oluşturucusu](../windows/module-methodreleasenotifier-methodreleasenotifier-constructor.md)|Yeni bir örneğini başlatır **Module::MethodReleaseNotifier** sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Module::MethodReleaseNotifier::Invoke Metodu](../windows/module-methodreleasenotifier-invoke-method.md)|Geçerli ile ilişkili olay işleyicisini çağırır **Module::MethodReleaseNotifier** nesne.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Module::MethodReleaseNotifier::method_ Veri Üyesi](../windows/module-methodreleasenotifier-method-data-member.md)|İçin geçerli olay işleyicisine bir işaretçiyi tuttuğu **Module::MethodReleaseNotifier** nesne.|
|[Module::MethodReleaseNotifier::object_ Veri Üyesi](../windows/module-methodreleasenotifier-object-data-member.md)|Üye işlevi için geçerli olay işleyicisi olan nesneye bir işaretçi tutan **Module::MethodReleaseNotifier** nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ReleaseNotifier`

`MethodReleaseNotifier`

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.
[Modül Sınıfı](../windows/module-class.md)