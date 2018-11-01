---
title: bad_function_call Sınıfı
ms.date: 11/04/2016
f1_keywords:
- functional/std::bad_function_call
helpviewer_keywords:
- bad_function_call class
ms.assetid: b70a0268-43ff-4f3b-a283-faf1cb172d4c
ms.openlocfilehash: 6d0a3f5f5b6ac48d23b937b04b4521799ba31502
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523832"
---
# <a name="badfunctioncall-class"></a>bad_function_call Sınıfı

Hatalı işlev çağrısı bildirir.

## <a name="syntax"></a>Sözdizimi

```cpp
class bad_function_call : public std::exception {};
```

## <a name="remarks"></a>Açıklamalar

Sınıfı, bir çağrı göstermek için özel bir durum oluştu açıklar `operator()` üzerinde bir [sınıfı işlevi](../standard-library/function-class.md)
