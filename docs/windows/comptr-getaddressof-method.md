---
title: "ComPtr::GetAddressOf yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::GetAddressOf
dev_langs: C++
helpviewer_keywords: GetAddressOf method
ms.assetid: 972a41d0-c2ef-4ae3-b2cd-77cc45156ac9
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4a14a6366d1f8e6c5917835e750b5fddc45310d3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrgetaddressof-method"></a>ComPtr::GetAddressOf Metodu
Adresini alır [ptr_](../windows/comptr-ptr-data-member.md) bu ComPtr tarafından temsil edilen arayüzü için bir işaretçi içeriyor veri üyesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
T* const* GetAddressOf() const;  
T** GetAddressOf();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir değişken adresi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr sınıfı](../windows/comptr-class.md)