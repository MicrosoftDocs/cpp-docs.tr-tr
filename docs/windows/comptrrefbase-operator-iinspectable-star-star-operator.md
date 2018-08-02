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
ms.openlocfilehash: 19e04f5415f9f7a736371c888dff7559df6c6c66
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462342"
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

Bu tür dönüştürme kullanılabilir yalnızca **&#95; &#95;WRL_CLASSIC_COM&#95; &#95;** tanımlanır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.
[ComPtrRefBase sınıfı](../windows/comptrrefbase-class.md)   
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)