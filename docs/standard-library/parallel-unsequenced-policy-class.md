---
description: 'Hakkında daha fazla bilgi edinin: parallel_unsequenced_policy sınıfı'
title: parallel_unsequenced_policy sınıfı
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_unsequenced_policy
ms.openlocfilehash: e39edc0979bf1374bc6092dbadb032811180f668
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340794"
---
# <a name="parallel_unsequenced_policy-class"></a>parallel_unsequenced_policy sınıfı

Paralel algoritma aşırı yüklemesini netleştirmek için benzersiz bir tür olarak kullanılır ve bir paralel algoritma yürütmenin paralelleştirilmiş ve vektörleştirilmemiş olabileceğini belirtir.

## <a name="syntax"></a>Syntax

```cpp
class execution::parallel_unsequenced_policy;
```

## <a name="remarks"></a>Açıklamalar

Bir paralel algoritmanın ilkeyle yürütülmesi sırasında `execution::parallel_unsequenced_policy` , bir öğe erişim işlevinin çağrılması yakalanamayan bir özel durum ile çıkış yaparken, `terminate()` çağırılır.
