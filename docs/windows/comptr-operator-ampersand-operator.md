---
title: ComPtr::operator&amp; işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator&
dev_langs:
- C++
helpviewer_keywords:
- operator& operator
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f513ac83e0ee83109f42cf87b80b4fcc4960db1f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598609"
---
# <a name="comptroperatoramp-operator"></a>ComPtr::operator&amp; işleci

Şununla ilişkili arabirimini yayımlar **ComPtr** nesne ve adresini alır. **ComPtr** nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

## <a name="return-value"></a>Dönüş Değeri

Geçerli zayıf bir başvuru **ComPtr**.

## <a name="remarks"></a>Açıklamalar

Bu yöntem farklıdır [ComPtr::GetAddressOf](../windows/comptr-getaddressof-method.md) , bu yöntem bir arabirim işaretçisi başvurusu serbest bırakır. Kullanım `ComPtr::GetAddressOf` kullandığınızda arabirim işaretçisi adresini gerektirir ancak bu arabirimi serbest bırakmak istiyor musunuz.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[ComPtr Sınıfı](../windows/comptr-class.md)