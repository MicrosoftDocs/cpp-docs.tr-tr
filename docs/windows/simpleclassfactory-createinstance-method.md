---
title: "Simpleclassfactory::CreateInstance yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::SimpleClassFactory::CreateInstance
dev_langs: C++
helpviewer_keywords: CreateInstance method
ms.assetid: 17b7947a-2608-49d9-b730-fef76501c9bc
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: aaffaf02c7db9c311f3f06e18e0194089d79e430
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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

Varsa &#95; &#95; WRL_STRICT &#95; &#95; olduğundan sınıfı şablonu parametresinde belirtilen taban sınıfı türetilmiş değil, tanımlanmış bir assert hata yayılan [RuntimeClass](../windows/runtimeclass-class.md), ya da ClassicCom veya WinRtClassicComMix ile yapılandırılmamış [RuntimeClassType ](../windows/runtimeclasstype-enumeration.md) numaralandırma değeri.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[SimpleClassFactory sınıfı](../windows/simpleclassfactory-class.md)