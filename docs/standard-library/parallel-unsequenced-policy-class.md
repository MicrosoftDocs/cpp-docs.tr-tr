---
title: parallel_unsequenced_policy sınıfı
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_unsequenced_policy
ms.openlocfilehash: 92b4e3ce3743fdd3d5ba112a333b2306829b95d4
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68267990"
---
# <a name="parallelunsequencedpolicy-class"></a>parallel_unsequenced_policy sınıfı

Benzersiz bir türü paralel algoritma aşırı yükleme belirsizliği ortadan kaldırmak ve bir paralel algoritma 's yürütme paralel ve vektörleştirildi olduğunu belirtmek için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
class execution::parallel_unsequenced_policy;
```

## <a name="remarks"></a>Açıklamalar

Bir paralel algoritma ile yürütülmesi sırasında `execution::parallel_unsequenced_policy` yakalanmayan bir özel durum ile bir öğe erişimi işlevine çağırmayı bulunup bulunmadığını ilke `terminate()` çağrılması.
