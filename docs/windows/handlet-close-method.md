---
title: HandleT::Close yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 1b9d597c-abcf-4028-a068-0344560009f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4f0c1e47420106651cfe0526d6d212e9819a72ff
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873257"
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
 [HandleT Sınıfı](../windows/handlet-class.md)