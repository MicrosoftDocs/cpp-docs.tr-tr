---
description: 'Hakkında daha fazla bilgi edinin: bad_function_call sınıfı'
title: bad_function_call Sınıfı
ms.date: 11/04/2016
f1_keywords:
- functional/std::bad_function_call
helpviewer_keywords:
- bad_function_call class
ms.assetid: b70a0268-43ff-4f3b-a283-faf1cb172d4c
ms.openlocfilehash: 659630874f84ea9e7d164b560408b162f07e1f68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321605"
---
# <a name="bad_function_call-class"></a>bad_function_call Sınıfı

Hatalı işlev çağrısını raporlar.

## <a name="syntax"></a>Syntax

```cpp
class bad_function_call : public std::exception {};
```

## <a name="remarks"></a>Açıklamalar

Sınıfı, bir `operator()` [işlev sınıfı](../standard-library/function-class.md) üzerinde bir çağrının olduğunu göstermek için oluşturulan bir özel durum tanımlar
