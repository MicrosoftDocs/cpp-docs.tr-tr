---
title: Interfacetraits::casttobase yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase
dev_langs:
- C++
helpviewer_keywords:
- CastToBase method
ms.assetid: 0591a017-0adf-4358-b946-eb0a307ce7f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 55a4d7487be5b3565ba3945630cab4388f287a68
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611830"
---
# <a name="interfacetraitscasttobase-method"></a>InterfaceTraits::CastToBase Yöntemi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
static __forceinline Base* CastToBase(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Parametreler

*T*  
Parametresinin türü *ptr*.

*ptr*  
Bir tür işaretçisi *T*.

## <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `Base`.

## <a name="remarks"></a>Açıklamalar

Belirtilen bir işaretçi işaretçisi bıraktığı `Base`.

Hakkında daha fazla bilgi için `Base`, genel tür tanımları bölümüne bakın [Interfacetraits yapısı](../windows/interfacetraits-structure.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[InterfaceTraits Yapısı](../windows/interfacetraits-structure.md)  
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)