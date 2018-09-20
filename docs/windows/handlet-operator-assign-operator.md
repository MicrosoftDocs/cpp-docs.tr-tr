---
title: HandleT::operator = işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4c6aeca188f51f35c739c32f5290aac011781b41
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396902"
---
# <a name="handletoperator-operator"></a>HandleT::operator= İşleci

Belirtilen değer taşır **HandleT** geçerli nesneye **HandleT** nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Bir rvalue başvuru için bir tanıtıcı.

## <a name="return-value"></a>Dönüş Değeri

Geçerli bir başvuru **HandleT** nesne.

## <a name="remarks"></a>Açıklamalar

Bu işlem geçersiz kılar **HandleT** parametresi tarafından belirtilen nesne *h*.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[HandleT Sınıfı](../windows/handlet-class.md)