---
title: Mutex::operator = işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9b0ee206-a930-4fea-8dc0-1f79839e9d13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1b7cc38d595c6f6ad1aa92e584068ccb852dbbd4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42578694"
---
# <a name="mutexoperator-operator"></a>Mutex::operator= İşleci

Atar (taşıma) belirtilen **Mutex** geçerli nesneye **Mutex** nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
Mutex& operator=(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Parametreler

*h*  
Bir rvalue başvurusuna bir **Mutex** nesne.

## <a name="return-value"></a>Dönüş Değeri

Geçerli bir başvuru **Mutex** nesne.

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için **taşıma semantiği** bölümünü [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.
[Mutex sınıfı](../windows/mutex-class1.md)