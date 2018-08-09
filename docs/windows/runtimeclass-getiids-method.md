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
ms.openlocfilehash: 91d0a082a422657f6716e16c8b53ab33e0313d82
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020141"
---
# <a name="runtimeclassgetiids-method"></a>RuntimeClass::GetIids Metodu
Kimlikleri geçerli tarafından uygulanan arabirimi içerebilir bir dizisini alır **RuntimeClass** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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