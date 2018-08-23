---
title: RuntimeClass::DecrementReference yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::DecrementReference
dev_langs:
- C++
ms.assetid: f5ecfeaa-2865-455b-9208-94a0685fd2c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3c2b83d64315ed03fce0527dc11668265c1db461
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613149"
---
# <a name="runtimeclassdecrementreference-method"></a>RuntimeClass::DecrementReference Yöntemi

Başvuru için geçerli sayısını azaltır **RuntimeClass** nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
ULONG DecrementReference();
```

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[RuntimeClass Sınıfı](../windows/runtimeclass-class.md)