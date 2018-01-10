---
title: "Runtimeclass::getıids yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClass::GetIids
dev_langs: C++
helpviewer_keywords: GetIids method
ms.assetid: 826a67d1-ebc4-4940-b5d5-7cd66885e4a1
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e26101377aaf85cbae24e400557280d06d1402fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclassgetiids-method"></a>RuntimeClass::GetIids Metodu
Kimlikleri geçerli RuntimeClass nesne tarafından uygulanan arabirimi içeren bir dizi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   GetIids  
)  
   (_Out_ ULONG *iidCount,   
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `iidCount`  
 Bu işlem tamamlandığında, dizideki öğeler toplam sayısı `iids`.  
  
 `iids`  
 Bu işlem tamamlandığında, bir dizi arabirim kimlikleri için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, E_OUTOFMEMORY.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [RuntimeClass Sınıfı](../windows/runtimeclass-class.md)