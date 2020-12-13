---
description: 'Daha fazla bilgi edinin: Cancelgeçişli Ilke numaralandırması'
title: CancelTransitionPolicy Numaralandırması
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled
- module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled
- module/Microsoft::WRL::CancelTransitionPolicy
helpviewer_keywords:
- CancelTransitionPolicy Enumeration
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
ms.openlocfilehash: 8de995ed492f8f1260534b08b818b77d889d95fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344542"
---
# <a name="canceltransitionpolicy-enumeration"></a>CancelTransitionPolicy Numaralandırması

Zaman uyumsuz bir işlemin, tamamlandı veya hata bir Terminal durumuna geçiş denemesinin, istemci tarafından istenen iptal edilmiş duruma göre davranması gerektiğini gösterir.

## <a name="syntax"></a>Syntax

```cpp
enum CancelTransitionPolicy;
```

## <a name="members"></a>Üyeler

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`RemainCanceled`|Zaman uyumsuz işlem şu anda istemci tarafından istenen bir iptal durumunda ise, bu durum, Terminal tamamlanmış veya hata durumuna geçiş yerine iptal durumunda kalacağını gösterir.|
|`TransitionFromCanceled`|Zaman uyumsuz işlem şu anda istemci tarafından istenen bir iptal durumunda ise, bu bayrağı kullanan çağrı tarafından belirlendiği şekilde durum durumunun bu iptal durumundan tamamlandı veya hata durumuna geçmesi gerektiğini gösterir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** Async. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL ad alanı](microsoft-wrl-namespace.md)
