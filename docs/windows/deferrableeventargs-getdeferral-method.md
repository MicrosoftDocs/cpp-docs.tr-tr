---
title: "DeferrableEventArgs::GetDeferral yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2a49fba82867650a80f45de3c6301405f96b5c47
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
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