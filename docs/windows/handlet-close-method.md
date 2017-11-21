---
title: "HandleT::Close yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
dev_langs: C++
helpviewer_keywords: Close method
ms.assetid: 1b9d597c-abcf-4028-a068-0344560009f6
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 94c246153e5c7e159ccbfe4196ab3692f4138047
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="handletclose-method"></a>HandleT::Close Yöntemi
Geçerli HandleT nesnesini kapatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void Close();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Geçerli HandleT altını çizen tanıtıcı kapatılır ve HandleT geçersiz duruma ayarlanır.  
  
 Tanıtıcı düzgün kapatmaz, çağıran iş parçacığında özel durum oluşturulur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HandleT sınıfı](../windows/handlet-class.md)