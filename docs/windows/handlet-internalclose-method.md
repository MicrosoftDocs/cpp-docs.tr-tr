---
title: Handlet::ınternalclose yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
dev_langs:
- C++
helpviewer_keywords:
- InternalClose method
ms.assetid: fe693c02-aa1f-4e00-8bdd-a0d7d736da0b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b0aef97645d515a03dcf2cab90eedc06f07971c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="handletinternalclose-method"></a>HandleT::InternalClose Yöntemi
Geçerli HandleT nesnesini kapatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
virtual bool InternalClose();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true` Geçerli HandleT başarıyla kapattıysanız; Aksi takdirde `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 InternalClose() korunur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HandleT Sınıfı](../windows/handlet-class.md)