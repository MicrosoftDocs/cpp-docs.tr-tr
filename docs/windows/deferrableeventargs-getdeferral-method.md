---
title: DeferrableEventArgs::GetDeferral yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2442894c5f7bd85eb94262e776294c1e52a19e01
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="deferrableeventargsgetdeferral-method"></a>DeferrableEventArgs::GetDeferral Metodu
Bir başvuru edinir [erteleme](http://go.microsoft.com/fwlink/p/?linkid=526520) ertelenmiş bir olayı temsil eden nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `result`  
 Başvurur bir işaretçi [erteleme](http://go.microsoft.com/fwlink/p/?linkid=526520) çağrısı tamamlandığında nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, HRESULT hata gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Kod örneği için bkz: [DeferrableEventArgs sınıfı](../windows/deferrableeventargs-class.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DeferrableEventArgs Sınıfı](../windows/deferrableeventargs-class.md)