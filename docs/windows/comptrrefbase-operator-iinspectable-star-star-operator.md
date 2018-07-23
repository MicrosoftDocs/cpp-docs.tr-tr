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
ms.openlocfilehash: 0c23ba7ba476b44b44f48b76119776e2f2cb188e
ms.sourcegitcommit: 04d327940787df1297b72d534f388a035d472af0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39181152"
---
# <a name="comptrrefbaseoperator-iinspectable-operator"></a>ComPtrRefBase::operator Iınspectable\* \* işleci

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
operator IInspectable**() const;
```

## <a name="remarks"></a>Açıklamalar

Geçerli bıraktığı [ptr_](../windows/comptrrefbase-ptr-data-member.md) veri üyesi için bir işaretçi-için-a-işaretçi-Iınspectable arabirimi.

Geçerli ComPtrRefBase Iınspectable türetirseniz olmayan bir hata yayılır.

Bu tür dönüştürme kullanılabilir yalnızca **&#95; &#95;WRL_CLASSIC_COM&#95; &#95;** tanımlanır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[ComPtrRefBase sınıfı](../windows/comptrrefbase-class.md)   
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)
