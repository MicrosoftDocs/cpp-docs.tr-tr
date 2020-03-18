---
title: sequenced_policy sınıfı
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::sequenced_policy
ms.openlocfilehash: 5647f20b560828016231a9bbd38977c51211e6bb
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444922"
---
# <a name="sequenced_policy-class"></a>sequenced_policy sınıfı

Paralel algoritma aşırı yüklemesini ayırt etmek için benzersiz bir tür olarak kullanılır ve paralel algoritma yürütmenin paralelleştirilmesine gerek yoktur.

## <a name="syntax"></a>Sözdizimi

```cpp
class execution::sequenced_policy;
```

## <a name="remarks"></a>Açıklamalar

Bir paralel algoritmanın `execution::sequenced_policy` ilkesiyle yürütülmesi sırasında, bir öğe erişim işlevinin çağrılması yakalanamayan bir özel durumla çıkıldığında, `terminate()` çağırılır.
