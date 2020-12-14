---
description: 'Hakkında daha fazla bilgi edinin: sequenced_policy sınıfı'
title: sequenced_policy sınıfı
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::sequenced_policy
ms.openlocfilehash: e4d19e3649e3c768e8efc062baaf735e28a8fc22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250419"
---
# <a name="sequenced_policy-class"></a>sequenced_policy sınıfı

Paralel algoritma aşırı yüklemesini ayırt etmek için benzersiz bir tür olarak kullanılır ve paralel algoritma yürütmenin paralelleştirilmesine gerek yoktur.

## <a name="syntax"></a>Syntax

```cpp
class execution::sequenced_policy;
```

## <a name="remarks"></a>Açıklamalar

Bir paralel algoritmanın ilkeyle yürütülmesi sırasında `execution::sequenced_policy` , bir öğe erişim işlevinin çağrılması yakalanamayan bir özel durum ile çıkış yaparken, `terminate()` çağırılır.
