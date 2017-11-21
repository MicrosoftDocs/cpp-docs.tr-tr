---
title: "HStringReference sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HStringReference
dev_langs: C++
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1d09ba7fff2426f58f72b26a2c7e7681cecde8b5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="hstringreference-class"></a>HStringReference Sınıfı
Varolan bir dizeden oluşturulmuş bir HSTRING temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
class HStringReference;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Yeni HSTRING yedekleme arabellekte ömrü Windows çalışma zamanı tarafından yönetilmiyor. Arayan yığın çerçevesinde yığın ayırma önlemek için ve bir bellek sızıntısı riskini ortadan kaldırmak için bir kaynak dizesi ayırır. Ayrıca, çağıran kaynak dize ekli HSTRING ömrü boyunca değişmeden kalır emin olmalısınız. Daha fazla bilgi için bkz: [WindowsCreateStringReference işlevi](http://msdn.microsoft.com/en-us/0361bb7e-da49-4289-a93e-de7aab8712ac).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[HStringReference::HStringReference Oluşturucusu](../windows/hstringreference-hstringreference-constructor.md)|HStringReference sınıfı yeni bir örneğini başlatır.|  
  
### <a name="members"></a>Üyeler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[HStringReference::CopyTo yöntemi](../windows/hstringreference-copyto-method.md)|Kopya geçerli HStringReference HSTRING nesneye nesne.|  
|[HStringReference::Get yöntemi](../windows/hstringreference-get-method.md)|Temel alınan HSTRING tanıtıcı değerini alır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[HStringReference::Operator = işleci](../windows/hstringreference-operator-assign-operator.md)|Başka bir HStringReference nesnenin değerini geçerli HStringReference nesneye taşır.|  
|[HStringReference::Operator == işleci](../windows/hstringreference-operator-equality-operator.md)|İki parametre eşit olup olmadığını gösterir.|  
|[HStringReference::Operator! = işleci](../windows/hstringreference-operator-inequality-operator.md)|İki parametre eşit olup olmadığını gösterir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `HStringReference`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: Wrappers Namespace](../windows/microsoft-wrl-wrappers-namespace.md)