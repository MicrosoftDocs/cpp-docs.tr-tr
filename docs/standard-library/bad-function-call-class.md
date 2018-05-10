---
title: bad_function_call sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::bad_function_call
dev_langs:
- C++
helpviewer_keywords:
- bad_function_call class
ms.assetid: b70a0268-43ff-4f3b-a283-faf1cb172d4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e00dd485478a5a6fb7ff029afdad7bf7212fd56
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="badfunctioncall-class"></a>bad_function_call Sınıfı

Hatalı işlev çağrısı bildirir.

## <a name="syntax"></a>Sözdizimi

```cpp
class bad_function_call
 : public std::exception {
 };
```

## <a name="remarks"></a>Açıklamalar

Sınıf olduğunu belirten bir durum yapılan bir çağrı tanımlar `operator()` üzerinde bir [sınıfı işlevi](../standard-library/function-class.md)
