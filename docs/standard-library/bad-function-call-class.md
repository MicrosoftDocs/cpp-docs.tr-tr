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
ms.openlocfilehash: 4b6a450d26480a0e89a115efc5731725f8f8b913
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714200"
---
# <a name="badfunctioncall-class"></a>bad_function_call Sınıfı

Hatalı işlev çağrısı bildirir.

## <a name="syntax"></a>Sözdizimi

```cpp
class bad_function_call : public std::exception {};
```

## <a name="remarks"></a>Açıklamalar

Sınıfı, bir çağrı göstermek için özel bir durum oluştu açıklar `operator()` üzerinde bir [sınıfı işlevi](../standard-library/function-class.md)
