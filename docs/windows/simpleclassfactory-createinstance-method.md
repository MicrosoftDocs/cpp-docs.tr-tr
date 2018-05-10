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
ms.openlocfilehash: 8a31d364a6464962b8243cfaced03131a20f9324
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="simpleclassfactorycreateinstance-method"></a>SimpleClassFactory::CreateInstance Yöntemi

Belirtilen arabiriminin bir örneğini oluşturur.

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
Olmalıdır `nullptr`; Aksi halde, dönüş değeri CLASS_E_NOAGGREGATION değeridir.

SimpleClassFactory toplama desteklemiyor. Toplama desteklenen ve oluşturulan nesne bir toplama parçası olan `pUnkOuter` toplama denetleme IUnknown arabirimi için bir işaretçi olabilir.

*nRIID*  
Nesnenin kimliği oluşturmak için arabirim.

*ppvObject*  
Bu işlem tamamlandığında, işaretçi tarafından belirtilen nesne örneği `riid` parametresi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, HRESULT hata gösterir.

## <a name="remarks"></a>Açıklamalar

Varsa &#95; &#95;WRL_STRICT&#95; &#95; olduğu sınıfı şablonu parametresinde belirtilen taban sınıfı türetilmiş değil, tanımlanmış bir assert hata yayılan [RuntimeClass](../windows/runtimeclass-class.md), ya da ClassicCom ile yapılandırılmamış veya WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırma değeri.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[SimpleClassFactory Sınıfı](../windows/simpleclassfactory-class.md)