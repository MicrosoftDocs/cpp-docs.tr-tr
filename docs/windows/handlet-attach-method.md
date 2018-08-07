---
title: HandleT::Attach yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method
ms.assetid: a8783a18-bbf6-456c-98a3-e2048a10d79f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5db96e9b8fd2090d9c58d9458bd53c66f6162477
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569178"
---
# <a name="handletattach-method"></a>HandleT::Attach Yöntemi
Belirtilen tanıtıcı geçerli ilişkilendirir **HandleT** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void Attach(  
   typename HandleTraits::Type h  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *h*  
 Tanıtıcı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HandleT Sınıfı](../windows/handlet-class.md)