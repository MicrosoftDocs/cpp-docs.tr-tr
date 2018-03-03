---
title: "ComPtr::GetAddressOf yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::GetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- GetAddressOf method
ms.assetid: 972a41d0-c2ef-4ae3-b2cd-77cc45156ac9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d62a1bca258e0903ddd4e71b161d87d926588248
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [ComPtr Sınıfı](../windows/comptr-class.md)