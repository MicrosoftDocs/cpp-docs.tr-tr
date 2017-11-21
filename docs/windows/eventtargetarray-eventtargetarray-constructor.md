---
title: "EventTargetArray::EventTargetArray Oluşturucusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
dev_langs: C++
helpviewer_keywords: EventTargetArray, constructor
ms.assetid: 6c6d3737-3cd3-4515-a8f6-d27901bb8ed2
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6dbe316310e04172c659460c08137edd2a401df6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)