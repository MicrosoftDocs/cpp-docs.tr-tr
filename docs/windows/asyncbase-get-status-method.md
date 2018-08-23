---
title: AsyncBase::get_Status metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::get_Status
dev_langs:
- C++
helpviewer_keywords:
- get_Status method
ms.assetid: 9823ecb9-212e-471d-b76f-7b8f21208905
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 31b333c14af6d57fb098d6aff0d0938092477de0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613130"
---
# <a name="asyncbasegetstatus-method"></a>AsyncBase::get_Status Metodu

Zaman uyumsuz işlemin durumunu gösteren bir değer alır.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(
   get_Status
)(AsyncStatus *status) override;
```

### <a name="parameters"></a>Parametreler

*Durumu*  
Durum depolanacak bulunduğu konumu. Daha fazla bilgi için `Windows::Foundation::AsyncStatus` sabit listesi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="remarks"></a>Açıklamalar

Bu yöntem `IAsyncInfo::get_Status`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[AsyncBase Sınıfı](../windows/asyncbase-class.md)