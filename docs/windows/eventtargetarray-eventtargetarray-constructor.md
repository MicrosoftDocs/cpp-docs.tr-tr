---
title: "EventTargetArray::EventTargetArray Oluşturucusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
dev_langs:
- C++
helpviewer_keywords:
- EventTargetArray, constructor
ms.assetid: 6c6d3737-3cd3-4515-a8f6-d27901bb8ed2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e8c8ada61a18437ed159452355e8286bc9d190f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
  
#### <a name="parameters"></a>Parametreler  
 `hr`  
 Bu oluşturucu işlemlerinden sonra parametresi `hr` ayırma dizisinin başarılı veya başarısız olup olmadığını gösterir. İçin olası değerler aşağıdaki tabloda listelenmektedir `hr`.  
  
 S_OK  
 İşlemi başarılı oldu.  
  
 E_OUTOFMEMORY  
 Dizi için bellek ayrılamıyor.  
  
 S_FALSE  
 Parametre `items` sıfırdan küçük veya eşit.  
  
 `items`  
 Dizi öğeleri tahsis sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 EventTargetArray sınıfı yeni bir örneğini başlatır.  
  
 EventTargetArray EventSource nesnesinde bir dizi olay işleyicileri tutmak için kullanılır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EventTargetArray sınıfı](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)