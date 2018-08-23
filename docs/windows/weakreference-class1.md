---
title: WeakReference sınıfı1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference
dev_langs:
- C++
helpviewer_keywords:
- WeakReference class
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a9b7270a03192a6fcf53f0c2ecfd1af07a216243
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595537"
---
# <a name="weakreference-class1"></a>WeakReference sınıfı1

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
class WeakReference;
```

## <a name="remarks"></a>Açıklamalar

Temsil eden bir *zayıf başvuru* kullanılabilen Windows çalışma zamanı veya klasik COM ile Zayıf bir başvuru erişilebilir olmayabilir veya bir nesneyi temsil eder.

A **WeakReference** nesne tutar bir *güçlü başvuru*, bir nesneye bir işaretçi olduğu ve bir *güçlü başvuru sayısı*, güçlü kopya sayısını olduğu tarafından dağıtılan başvuru `Resolve()` yöntemi. Güçlü Başvuru sayısı sıfır dışında olsa da, güçlü başvuru geçerli olduğundan ve erişilebilir bir nesnedir. Güçlü Başvuru sayısı sıfır olduğunda, güçlü başvuru geçersiz ve nesne erişilemez.

A **WeakReference** nesne genellikle, varlığı harici bir iş parçacığı ya da uygulama tarafından denetlenen bir nesneyi göstermek için kullanılır. Örneğin, oluşturun bir **WeakReference** nesneden bir dosya nesnesine bir başvuru. Dosya açıkken, güçlü başvuru geçerli değil. Ancak, dosya kapalıysa, güçlü başvuru geçersiz hale gelir.

**WeakReference** yöntemlerdir iş parçacığı açısından güvenlidir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[WeakReference::WeakReference Oluşturucusu](../windows/weakreference-weakreference-constructor.md)|Yeni bir örneğini başlatır **WeakReference** sınıfı.|
|[WeakReference::~WeakReference Yıkıcısı](../windows/weakreference-tilde-weakreference-destructor.md)|Başlatılmasını geri alır (yok eder), geçerli örneğini **WeakReference** sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[WeakReference::DecrementStrongReference Metodu](../windows/weakreference-decrementstrongreference-method.md)|Güçlü Başvuru geçerli sayısını azaltır **WeakReference** nesne.|
|[WeakReference::IncrementStrongReference Metodu](../windows/weakreference-incrementstrongreference-method.md)|Geçerli güçlü başvuru sayısını artırır **WeakReference** nesne.|
|[WeakReference::Resolve Metodu](../windows/weakreference-resolve-method.md)|Güçlü Başvuru sayısı sıfır değilse belirtilen işaretçi geçerli güçlü başvuru değerine ayarlar.|
|[WeakReference::SetUnknown Metodu](../windows/weakreference-setunknown-method.md)|Güçlü Başvuru geçerli ayarlar **WeakReference** belirtilen arabirim işaretçisini için nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`WeakReference`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)