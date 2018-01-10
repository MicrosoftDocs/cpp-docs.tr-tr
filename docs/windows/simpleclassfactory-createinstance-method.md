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
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 68778eb1b5421cfcf22261d8b1c1efd99bc32c50
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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

[SimpleClassFactory Sınıfı](../windows/simpleclassfactory-class.md)