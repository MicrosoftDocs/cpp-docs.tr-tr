---
title: EventTargetArray::EventTargetArray Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
dev_langs:
- C++
helpviewer_keywords:
- EventTargetArray, constructor
ms.assetid: 6c6d3737-3cd3-4515-a8f6-d27901bb8ed2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 831c9a524f8120c855382d198a5f53ac312cada6
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569794"
---
# <a name="eventtargetarrayeventtargetarray-constructor"></a>EventTargetArray::EventTargetArray Oluşturucusu
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
EventTargetArray(  
   _Out_ HRESULT* hr,  
   size_t items  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *İK*  
 Bu oluşturucu işlemlerinden sonra parametre *ik* dizinin ayırma başarılı veya başarısız olduğunu gösterir. İçin olası değerler aşağıdaki tabloda *ik*.  
  
 S_OK  
 İşlem başarılı oldu.  
  
 E_OUTOFMEMORY  
 Dizi için bellek ayrılamıyor.  
  
 S_FALSE  
 Parametre *öğeleri* sıfırdan küçük veya ona eşit.  
  
 *Öğeleri*  
 Ayrılacak dizi öğelerinin sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Yeni bir örneğini başlatır **EventTargetArray** sınıfı.  
  
 **EventTargetArray** bir dizi olay işleyicileri tutmak için kullanılan bir `EventSource` nesne.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EventTargetArray sınıfı](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)