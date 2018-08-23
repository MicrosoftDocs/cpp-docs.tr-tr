---
title: CancelTransitionPolicy sabit listesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled
- module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled
- module/Microsoft::WRL::CancelTransitionPolicy
dev_langs:
- C++
helpviewer_keywords:
- CancelTransitionPolicy Enumeration
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: abc49a62e1cc9fb4abdc56b329b8fa057edebde7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42583523"
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