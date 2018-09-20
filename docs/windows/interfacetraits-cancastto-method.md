---
title: Interfacetraits::cancastto yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 275847cb-69ea-42bf-910f-05ba6ef8b48d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 705b495e3f6d626a742fd1a63989c8cc658446a4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379676"
---
# <a name="interfacetraitscancastto-method"></a>InterfaceTraits::CanCastTo Yöntemi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
static __forceinline bool CanCastTo(
   _In_ T* ptr,
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parametreler

*ptr*<br/>
Bir tür için bir işaretçi adı.

*riid*<br/>
Arabirim Kimliği `Base`.

*ppv*<br/>
Bu işlem başarılı olursa *ppv* tarafından belirtilen arabirim işaret `Base`. Aksi takdirde, *ppv* ayarlanır **nullptr**.

## <a name="return-value"></a>Dönüş Değeri

**doğru** bu işlem başarılı olursa ve *ptr* işaretçisine dönüştürme `Base`; Aksi takdirde **false** .

## <a name="remarks"></a>Açıklamalar

Belirtilen işaretçi işaretçisi içerip içermeyeceğini belirten `Base`.

Hakkında daha fazla bilgi için `Base`, bkz: **genel Typedefler** konusundaki [Interfacetraits yapısı](../windows/interfacetraits-structure.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[InterfaceTraits Yapısı](../windows/interfacetraits-structure.md)<br/>
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)