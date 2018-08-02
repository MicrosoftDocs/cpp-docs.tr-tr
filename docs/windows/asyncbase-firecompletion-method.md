---
title: AsyncBase::FireCompletion yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::FireCompletion
dev_langs:
- C++
helpviewer_keywords:
- FireCompletion method
ms.assetid: b5e29d6d-52e7-4148-a7f3-a313b1359819
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fa5988516f3836749357b15295ac228b78fe3f04
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467247"
---
# <a name="asyncbasefirecompletion-method"></a>AsyncBase::FireCompletion Yöntemi
Tamamlanma olayı işleyicisini çağırır veya iç ilerleme temsilci sıfırlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void FireCompletion(  
   void  
) override;  
  
virtual void FireCompletion();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Ürününün ilk sürümünü **FireCompletion()** iç ilerleme temsilci değişkeni sıfırlar. Zaman uyumsuz işlem tamamlandıysa ikinci sürüm tamamlama olay işleyicisini çağırır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase Sınıfı](../windows/asyncbase-class.md)