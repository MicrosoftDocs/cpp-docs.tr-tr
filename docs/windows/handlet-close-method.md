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
ms.openlocfilehash: 7cbe76cdea5c8fadef818ede1d63d88e4437bdae
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651073"
---
# <a name="handletclose-method"></a>HandleT::Close Yöntemi
Geçerli kapatır **HandleT** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
void Close();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Geçerli altını tanıtıcı **HandleT** kapatılır ve **HandleT** geçersiz duruma ayarlanır.  
  
 Tanıtıcı düzgün kapatmadığına, çağıran iş parçacığında bir özel durum oluşturulur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HandleT Sınıfı](../windows/handlet-class.md)