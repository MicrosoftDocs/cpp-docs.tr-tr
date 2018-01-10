---
title: "ComPtr::Swap yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::Swap
dev_langs: C++
helpviewer_keywords: Swap method
ms.assetid: 74275f00-b24e-4b4c-b8b6-ac2aa2dd7ae9
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b402d60b5f9cda3f9c98e6a92ac451cbdd6bfa79
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrswap-method"></a>ComPtr::Swap Yöntemi
Belirtilen ComPtr tarafından yönetilen arabirimi geçerli ComPtr tarafından yönetilen arabirimi değiş tokuş eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void Swap(  
   _Inout_ ComPtr&& r  
);  
  
void Swap(  
   _Inout_ ComPtr& r  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `r`  
 ComPtr.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtr Sınıfı](../windows/comptr-class.md)