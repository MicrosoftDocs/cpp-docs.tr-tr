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
ms.openlocfilehash: 69f3f2c756d158954676f6fc42941b1b80f4345e
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569924"
---
# <a name="handletclose-method"></a>HandleT::Close Yöntemi
Geçerli kapatır **HandleT** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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