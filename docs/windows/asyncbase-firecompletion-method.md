---
title: "AsyncBase::FireCompletion yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::FireCompletion
dev_langs: C++
helpviewer_keywords: FireCompletion method
ms.assetid: b5e29d6d-52e7-4148-a7f3-a313b1359819
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2f5478b7ea3777230eb4adcb9f94cd15cbb9cd9d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbasefirecompletion-method"></a>AsyncBase::FireCompletion Yöntemi
Tamamlama olay işleyiciyi çağırır veya iç ilerleme temsilci sıfırlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void FireCompletion(  
   void  
) override;  
  
virtual void FireCompletion();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 FireCompletion() ilk sürümü iç ilerleme temsilci değişkeni sıfırlar. Zaman uyumsuz işlemi tamamlandığında ikinci sürüm tamamlama olay işleyiciyi çağırır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase sınıfı](../windows/asyncbase-class.md)