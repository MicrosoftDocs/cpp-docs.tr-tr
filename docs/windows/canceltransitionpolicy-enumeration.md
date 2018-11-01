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
ms.openlocfilehash: 99ca0c475d7fe700c2350ae05a87b8e64b10d775
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509973"
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

[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)