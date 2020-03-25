---
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
ms.openlocfilehash: e820b3fffb4a00e95a1210a5c0beb3229c6d1657
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214129"
---
# <a name="canceltransitionpolicy-enumeration"></a>CancelTransitionPolicy Numaralandırması

Zaman uyumsuz bir işlemin, tamamlandı veya hata bir Terminal durumuna geçiş denemesinin, istemci tarafından istenen iptal edilmiş duruma göre davranması gerektiğini gösterir.

## <a name="syntax"></a>Sözdizimi

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

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)
