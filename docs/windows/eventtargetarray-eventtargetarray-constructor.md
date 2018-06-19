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
ms.openlocfilehash: fbfd12ea513044f1062e60f5c73f5089683f043d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33872721"
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