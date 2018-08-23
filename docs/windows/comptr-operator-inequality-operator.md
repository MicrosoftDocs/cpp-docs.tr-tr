---
title: ComPtr::operator! = işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator!=
dev_langs:
- C++
ms.assetid: 63647240-dec7-4eb9-9272-96c07d01493c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4874121f22daa8e4a13bf7a1d332c9b8e3db60ba
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42578113"
---
# <a name="comptroperator-operator"></a>ComPtr::operator!= İşleci

Belirtir olup iki **ComPtr** nesneler eşit değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
bool operator!=(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);

bool operator!=(
   const ComPtr<T>& a,
   decltype(__nullptr)  
);

bool operator!=(
   decltype(__nullptr),
   const ComPtr<T>& a
);
```

### <a name="parameters"></a>Parametreler

*a*  
Bir başvuru bir **ComPtr** nesne.

*b*  
Başka bir başvuru **ComPtr** nesne.

## <a name="return-value"></a>Dönüş Değeri

İlk işleç sayıları **true** , nesne *bir* nesnesine eşit değil *b*; Aksi takdirde **false**.

İkinci ve üçüncü işleçleri yield **true** , nesne *bir* eşit değildir **nullptr**; Aksi takdirde **false**.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)  
[ComPtr Sınıfı](../windows/comptr-class.md)