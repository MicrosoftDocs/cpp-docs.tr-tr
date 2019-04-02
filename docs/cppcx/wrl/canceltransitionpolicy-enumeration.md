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
ms.openlocfilehash: cfd8e25f98ec1001a8fbd287eaec12408b9f240e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787050"
---
# <a name="canceltransitionpolicy-enumeration"></a>CancelTransitionPolicy Numaralandırması

Ne zaman uyumsuz bir işlem denemesi bir terminal durumuna geçirmeye gösteren tamamlanmış veya hata, bir istemci tarafından istenen iptal edilmiş duruma göre davranır.

## <a name="syntax"></a>Sözdizimi

```cpp
enum CancelTransitionPolicy;
```

## <a name="members"></a>Üyeler

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`RemainCanceled`|Zaman uyumsuz işlemi şu anda bir istemci tarafından istenen iptal edildi durumunda ise bunun aksine, bir terminal tamamlandı ya da hata durumuna geçiş işlemi iptal edildi durumunda kalır gösterir.|
|`TransitionFromCanceled`|Zaman uyumsuz işlemi şu anda bir istemci tarafından istenen iptal edildi durumunda ise, bu durum, terminal durumuna iptal edilmiş duruma tamamlandı geçiş gösterir veya bu bayrağı yararlanan çağrı tarafından belirlenen şekilde bir hata oluştu.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)