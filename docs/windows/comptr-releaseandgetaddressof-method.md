---
title: "ComPtr::ReleaseAndGetAddressOf yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
dev_langs: C++
helpviewer_keywords: ReleaseAndGetAddressOf method
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b6711cc93071c1e260a5d216a6ad21add9c00540
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [ComPtr::ptr_ veri üyesi](../windows/comptr-ptr-data-member.md)