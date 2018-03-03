---
title: "ComPtrRefBase::operator Iınspectable ** işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
dev_langs:
- C++
helpviewer_keywords:
- operator IInspectable** operator
ms.assetid: 06ac1051-606c-449b-a566-cac78ca53762
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d83580537a81b1c75f44e32e6aa43b2b014c8373
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrrefbaseoperator-iinspectable-operator"></a>ComPtrRefBase::operator IInspectable** İşleci

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
operator IInspectable**() const;
```

## <a name="remarks"></a>Açıklamalar

Geçerli bıraktığı [ptr_](../windows/comptrrefbase-ptr-data-member.md) veri üyesi için bir işaretçi-için-a-pointer-Iınspectable arabirimi.

Geçerli ComPtrRefBase Iınspectable türetirseniz olmayan bir hata yayınlanır.

Bu atama kullanılabilir yalnızca **&#95; &#95; WRL_CLASSIC_COM &#95; &#95;**  tanımlanır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[ComPtrRefBase sınıfı](../windows/comptrrefbase-class.md)   
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)