---
description: 'Hakkında daha fazla bilgi edinin: parallel_policy sınıfı'
title: parallel_policy sınıfı
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_policy
ms.openlocfilehash: 1cead0bcc44256bf7d41d061d592849a7411b057
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340807"
---
# <a name="parallel_policy-class"></a>parallel_policy sınıfı

Paralel algoritma aşırı yüklemesini belirsizliği ortadan kaldırmak için benzersiz bir tür olarak kullanılır ve paralel algoritma yürütmenin paralelleştirilmesine işaret edilebilir.

## <a name="syntax"></a>Syntax

```cpp
class execution::parallel_policy;
```

## <a name="remarks"></a>Açıklamalar

Bir paralel algoritmanın ilkeyle yürütülmesi sırasında `execution::parallel_policy` , bir öğe erişim işlevinin çağrılması yakalanamayan bir özel durum ile çıkış yaparken, `terminate()` çağırılır.
