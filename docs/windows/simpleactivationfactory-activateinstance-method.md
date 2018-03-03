---
title: "Simpleactivationfactory::activateınstance yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
dev_langs:
- C++
helpviewer_keywords:
- ActivateInstance method
ms.assetid: 4f836e51-5a6c-4bad-b871-9f25199298b4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6bbe9d8c215674f087c6e0fa4ca7f3439fb89b78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="simpleactivationfactoryactivateinstance-method"></a>SimpleActivationFactory::ActivateInstance Yöntemi

Belirtilen arabiriminin bir örneğini oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>Parametreler

*ppvObject*  
Bu işlem tamamlandığında, işaretçi tarafından belirtilen nesne örneği `Base` sınıfı şablon parametresi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, HRESULT hata gösterir.

## <a name="remarks"></a>Açıklamalar

Varsa &#95; &#95; WRL_STRICT &#95; &#95; olduğundan sınıfı şablonu parametresinde belirtilen taban sınıfı türetilmiş değil, tanımlanmış bir assert hata yayılan [RuntimeClass](../windows/runtimeclass-class.md), ya da WinRt veya WinRtClassicComMix ile yapılandırılmamış [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırma değeri.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[SimpleActivationFactory Sınıfı](../windows/simpleactivationfactory-class.md)