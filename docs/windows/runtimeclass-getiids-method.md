---
title: Runtimeclass::getıids metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetIids
dev_langs:
- C++
helpviewer_keywords:
- GetIids method
ms.assetid: 826a67d1-ebc4-4940-b5d5-7cd66885e4a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 87f51d39bf1ff8c7d4271797dcaa23278ac2e747
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608449"
---
# <a name="runtimeclassgetiids-method"></a>RuntimeClass::GetIids Metodu
Kimlikleri geçerli tarafından uygulanan arabirimi içerebilir bir dizisini alır **RuntimeClass** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   GetIids  
)  
   (_Out_ ULONG *iidCount,   
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
### <a name="parameters"></a>Parametreler  
 *Iidcount*  
 Bu işlem tamamlandığında, toplam sayısı dizideki öğelerin *IID'leri*.  
  
 *IID'leri*  
 Bu işlem tamamlandığında arabirim kimlikleri dizisi için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, E_OUTOFMEMORY.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [RuntimeClass Sınıfı](../windows/runtimeclass-class.md)