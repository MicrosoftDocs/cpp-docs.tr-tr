---
title: HString::GetAddressOf metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf
dev_langs:
- C++
ms.assetid: 6050decf-5f99-49f0-9497-1c8192c485ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e327e2818903396c154be7406ec325695b6b6982
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613371"
---
# <a name="hstringgetaddressof-method"></a>HString::GetAddressOf Metodu

Temel HSTRING tanıtıcısına bir işaretçi alır.

## <a name="syntax"></a>Sözdizimi

```cpp
HSTRING* GetAddressOf() throw()  
```

## <a name="return-value"></a>Dönüş Değeri

Temel HSTRING tanıtıcısına bir işaretçi.

## <a name="remarks"></a>Açıklamalar

Temel HSTRING tanıtıcısına dize değerini bu işlemden sonra yok edilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[HString Sınıfı](../windows/hstring-class.md)