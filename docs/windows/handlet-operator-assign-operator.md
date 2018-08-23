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
ms.openlocfilehash: cf539082ef88abb5fb27f09d92b73403dc2d03a5
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611348"
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

*h*  
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