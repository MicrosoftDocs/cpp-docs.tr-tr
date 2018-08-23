---
title: Activationfactory::getıids metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetIids
dev_langs:
- C++
helpviewer_keywords:
- GetIids method
ms.assetid: 0983d709-d155-4d65-aae4-5b2c8bb0fede
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 49ef07365675ddb9cdedee1f6a2cdfb676188dc6
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42576715"
---
# <a name="activationfactorygetiids-method"></a>ActivationFactory::GetIids Metodu

Uygulanan arabirimi kimlikleri dizisini alır.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(
   GetIids
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Parametreler

*Iidcount*  
Bu işlem tamamlandığında, nesneniz kimlikleri sayısı *IID'leri* dizisi.

*IID'leri*  
Bu işlem tamamlandığında, bir dizi arabirim kimlikleri uygulanır.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT. E_OUTOFMEMORY olası bir hata HRESULT ' dir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[ActivationFactory Sınıfı](../windows/activationfactory-class.md)