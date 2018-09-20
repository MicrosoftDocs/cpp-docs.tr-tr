---
title: Chainınterfaces::fillarraywithıid yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: f1ce699c-dfb6-40a9-9ea0-e6703d3cf971
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 17e1f47c2dfaf53b63e6bc672cb7822f9bf2b391
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375352"
---
# <a name="chaininterfacesfillarraywithiid-method"></a>ChainInterfaces::FillArrayWithIid Yöntemi

Arabirim kimliği tarafından tanımlanan depoları *I0* şablon parametresi belirtilen bir dizisinde belirtilen bir konuma arabiriminin kimlikleri.

## <a name="syntax"></a>Sözdizimi

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Parametreler

*Dizin*<br/>
Bir dizin değeri işaretçisine *IID'leri* dizisi.

*IID'leri*<br/>
Arabirim kimlikleri dizisi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[ChainInterfaces Yapısı](../windows/chaininterfaces-structure.md)