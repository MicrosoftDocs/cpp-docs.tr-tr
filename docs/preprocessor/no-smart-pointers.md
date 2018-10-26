---
title: no_smart_pointers | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_search_pointers
dev_langs:
- C++
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 233e302d4035801e7d8871754d8ecfcfee54cf1a
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060917"
---
# <a name="nosmartpointers"></a>no_smart_pointers
**C++ özgü**

Tür kitaplığındaki tüm arabirimler için akıllı işaretçiler oluşturulmasını engeller.

## <a name="syntax"></a>Sözdizimi

```
no_smart_pointers
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak kullandığınızda, `#import`, bir tür kitaplığındaki tüm arabirimler için akıllı işaretçi bildirimi alın. Bu akıllı işaretçileri türlerinin [_com_ptr_t sınıfı](../cpp/com-ptr-t-class.md).

**END C++ özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)