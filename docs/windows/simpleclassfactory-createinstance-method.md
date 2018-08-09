---
title: Simpleclassfactory::CreateInstance yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- CreateInstance method
ms.assetid: 17b7947a-2608-49d9-b730-fef76501c9bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aa0d48ba96c550ff6ee1248dccd0b4c8e3021212
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020310"
---
# <a name="simpleclassfactorycreateinstance-method"></a>SimpleClassFactory::CreateInstance Yöntemi

Belirtilen arabirim bir örneğini oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD( CreateInstance )(
   _Inout_opt_ IUnknown* pUnkOuter,
   REFIID riid,
   _Deref_out_ void** ppvObject
);
```

### <a name="parameters"></a>Parametreler
*pUnkOuter*  
Olmalıdır **nullptr**; Aksi takdirde CLASS_E_NOAGGREGATION dönüş değeridir.

SimpleClassFactory toplama desteklemiyor. Oluşturulan nesne bir toplamanın parçası toplama desteklenen ve *pUnkOuter* denetlemek için bir işaretçi olabilir `IUnknown` toplamanın arabirimi.

*riid*  
Nesnenin kimliği oluşturmak için arabirim.

*ppvObject*  
Bu işlem tamamlandığında, işaretçi tarafından belirtilen nesnede örneğine *riid* parametresi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="remarks"></a>Açıklamalar

Varsa `__WRL_STRICT__` olan tanımlanan, türetilen sınıf şablonu parametresinde belirtilen temel sınıf değil, bir onay hata yayıldığını [RuntimeClass](../windows/runtimeclass-class.md), ya da ClassicCom veya WinRtClassicComMix ile yapılandırılmamış [ RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırma değeri.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.
 [SimpleClassFactory Sınıfı](../windows/simpleclassfactory-class.md)