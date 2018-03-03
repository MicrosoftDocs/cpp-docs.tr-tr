---
title: "ComPtr::ReleaseAndGetAddressOf yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAndGetAddressOf method
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: be56e7afb23295e9b03d801943af25c652d18758
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrreleaseandgetaddressof-method"></a>ComPtr::ReleaseAndGetAddressOf Yöntemi
Bu ComPtr ile ilişkili arabiriminin serbest bırakır ve adresini alır [ptr_](../windows/comptr-ptr-data-member.md) yayımlanan arayüzü için bir işaretçi içeriyor veri üyesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
T** ReleaseAndGetAddressOf();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Adresini [ptr_](../windows/comptr-ptr-data-member.md) bu ComPtr veri üyesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr sınıfı](../windows/comptr-class.md)   
 [ComPtr::ptr_ Veri Üyesi](../windows/comptr-ptr-data-member.md)