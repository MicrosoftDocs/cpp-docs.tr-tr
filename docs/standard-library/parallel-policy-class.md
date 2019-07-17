---
title: parallel_policy sınıfı
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_policy
ms.openlocfilehash: 7bb2b095a50e664dfc585e0bd4aaa608a6ad8e95
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268044"
---
# <a name="parallelpolicy-class"></a>parallel_policy sınıfı

Paralel algoritma aşırı yükleme belirsizliği ortadan kaldırmak ve bir paralel algoritma 's yürütme paralel belirtmek için benzersiz bir türü olarak kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
class execution::parallel_policy;
```

## <a name="remarks"></a>Açıklamalar

Bir paralel algoritma ile yürütülmesi sırasında `execution::parallel_policy` yakalanmayan bir özel durum ile bir öğe erişimi işlevine çağırmayı bulunup bulunmadığını ilke `terminate()` çağrılması.
