---
title: Interfacetraits::casttounknown yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: aca47fa0-3c60-47f2-a73c-258f7160adff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c75e02136c626d72215a2af79d1391863e9f494c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382668"
---
# <a name="interfacetraitscasttounknown-method"></a>InterfaceTraits::CastToUnknown Yöntemi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
static __forceinline IUnknown* CastToUnknown(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Parametresinin türü *ptr*.

*ptr*<br/>
İşaretçi türüne *T*.

## <a name="return-value"></a>Dönüş Değeri

IUnknown işaretçisi içinden `Base` türetilir.

## <a name="remarks"></a>Açıklamalar

Belirtilen bir işaretçi işaretçisi bıraktığı `IUnknown`.

Hakkında daha fazla bilgi için `Base`, genel tür tanımları bölümüne bakın [Interfacetraits yapısı](../windows/interfacetraits-structure.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[InterfaceTraits Yapısı](../windows/interfacetraits-structure.md)<br/>
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)