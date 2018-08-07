---
title: HStringReference::HStringReference Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
dev_langs:
- C++
ms.assetid: 29f5fe11-3928-4f60-9861-f0894247bfcb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7dce8c6fca14ad26665bf4868681234374c20f85
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608150"
---
# <a name="hstringreferencehstringreference-constructor"></a>HStringReference::HStringReference Oluşturucusu
Yeni bir örneğini başlatır **HStringReference** sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest]) throw();  
  
template<unsigned int sizeDest>  
HStringReference(wchar_t const (&str)[ sizeDest],   
                 unsigned int len) throw();  
  
HStringReference(HStringReference&& other) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *sizeDest*  
 Hedef boyutunu belirten bir şablon parametresi **HStringReference** arabellek.  
  
 *str*  
 Bir geniş karakter dizesi bir başvuru.  
  
 *Len*  
 En büyük uzunluğunu *str* parametre arabelleği bu işlemi kullanmak için. Varsa *len* parametresi belirtilmediyse, tüm *str* parametresi kullanılır. Varsa *len* büyüktür *sizeDest*, *len* ayarlanır *sizeDest*-1.  
  
 *Diğer*  
 Başka bir **HStringReference** nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucu, yeni bir başlatır **HStringReference** aynı boyuttaki parametre olarak nesne *str*.  
  
 İkinci Oluşturucu, yeni bir başlatır **HStringReference** nesnesinin boyutu specifeid parametresi tarafından *len*.  
  
 Üçüncü Oluşturucu, yeni bir başlatır **HStringReference** değerini nesnesine *diğer* parametresi ve ardından yok eder *diğer* parametresi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HStringReference Sınıfı](../windows/hstringreference-class.md)