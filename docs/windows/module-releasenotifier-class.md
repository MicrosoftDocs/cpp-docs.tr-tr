---
title: Module::ReleaseNotifier sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- ReleaseNotifier class
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e6f720d0a918a22aee4a4cade6af1cb02a90e8d8
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42588875"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier Sınıfı

Modül içindeki son nesnenin yayımlandığında bir olay işleyici çağırır.

## <a name="syntax"></a>Sözdizimi

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Module::ReleaseNotifier::~ReleaseNotifier Yıkıcısı](../windows/module-releasenotifier-tilde-releasenotifier-destructor.md)|Geçerli örneğinin başlatmasını geri alır **Module::ReleaseNotifier** sınıfı.|
|[Module::ReleaseNotifier::ReleaseNotifier Oluşturucusu](../windows/module-releasenotifier-releasenotifier-constructor.md)|Yeni bir örneğini başlatır **Module::ReleaseNotifier** sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Module::ReleaseNotifier::Invoke Metodu](../windows/module-releasenotifier-invoke-method.md)|Modül içindeki son nesnenin serbest bırakıldığında uygulandığında, bir olay işleyici çağırır.|
|[Module::ReleaseNotifier::Release](../windows/module-releasenotifier-release.md)|Geçerli siler **Module::ReleaseNotifier** nesnesi bir parametre ile oluşturulmuş nesne **true**.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ReleaseNotifier`

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.
[Modül Sınıfı](../windows/module-class.md)