---
title: ComPtr::operator -&gt; işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator->
dev_langs:
- C++
helpviewer_keywords:
- operator-> operator
ms.assetid: 7b7faefd-d1e4-4f31-a77d-17a42e0d6b6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 417fd11017f9f70ee8cc247898e23741488ae5e7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599994"
---
# <a name="comptroperator-gt-operator"></a>ComPtr::operator -&gt; işleci

Geçerli bir şablon parametresi tarafından belirtilen tür için bir işaretçi alır.

## <a name="syntax"></a>Sözdizimi

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

## <a name="return-value"></a>Dönüş Değeri

Geçerli şablon tür adıyla belirtilen türün işaretçisi.

## <a name="remarks"></a>Açıklamalar

Bu yardımcı işlevi, gereksiz yük STDMETHOD makrosu kullanarak neden olunan kaldırır. Bu işlev yapar `IUnknown` türleri **özel** yerine **sanal**.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[ComPtr Sınıfı](../windows/comptr-class.md)