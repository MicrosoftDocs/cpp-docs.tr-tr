---
title: sequenced_policy sınıfı
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_policy
ms.openlocfilehash: 63be7166b84fa452f53baf6b6de16831eb657a23
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268113"
---
# <a name="sequencedpolicy-class"></a>sequenced_policy sınıfı

Gerektiren paralel algoritma 's yürütme paralel ve paralel algoritma aşırı yükleme belirsizliği ortadan kaldırmak için benzersiz bir türü olarak kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
class execution::sequenced_policy;
```

## <a name="remarks"></a>Açıklamalar

Bir paralel algoritma ile yürütülmesi sırasında `execution::sequenced_policy` yakalanmayan bir özel durum ile bir öğe erişimi işlevine çağırmayı bulunup bulunmadığını ilke `terminate()` çağrılması.
