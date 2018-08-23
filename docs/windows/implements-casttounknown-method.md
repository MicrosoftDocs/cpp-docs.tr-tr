---
title: Implements::casttounknown yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: ca3324f7-4136-406b-8698-7389f4f3d3c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 988580a34c030c84c50adfff2741408be4b249cd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42586364"
---
# <a name="implementscasttounknown-method"></a>Implements::CastToUnknown Yöntemi

Temel alınan bir işaretçi alır `IUnknown` arabirimi.

## <a name="syntax"></a>Sözdizimi

```cpp
__forceinline IUnknown* CastToUnknown();
```

## <a name="return-value"></a>Dönüş Değeri

Bu işlem, her zaman başarılı olur ve döndürür `IUnknown` işaretçi.

## <a name="remarks"></a>Açıklamalar

İç yardımcı işlevi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Implements Yapısı](../windows/implements-structure.md)