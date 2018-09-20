---
title: ComPtrRefBase::operator Iınspectable ** işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
dev_langs:
- C++
helpviewer_keywords:
- operator IInspectable** operator
ms.assetid: 06ac1051-606c-449b-a566-cac78ca53762
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c27a1957ff6198ea68893dd9bb92f4e60b70e4f9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372346"
---
# <a name="comptrrefbaseoperator-iinspectable-operator"></a>ComPtrRefBase::operator Iınspectable\* \* işleci

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
operator IInspectable**() const;
```

## <a name="remarks"></a>Açıklamalar

Geçerli bıraktığı [ptr_](../windows/comptrrefbase-ptr-data-member.md) veri üyesi için bir işaretçi-için-a-işaretçi- `IInspectable` arabirimi.

Bir hata varsa yayıldığını geçerli **ComPtrRefBase** öğesinden türetilen değil `IInspectable`.

Bu tür dönüştürme kullanılabilir yalnızca `__WRL_CLASSIC_COM__` tanımlanır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[ComPtrRefBase Sınıfı](../windows/comptrrefbase-class.md)<br/>
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)