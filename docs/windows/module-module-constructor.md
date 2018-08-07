---
title: Module::Module Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Module
dev_langs:
- C++
helpviewer_keywords:
- Module, constructor
ms.assetid: 5436fc74-61dc-41b6-81af-4f03177159aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 207b1006aeb57d9c16c09f5d8101a7f64b2cb85b
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608725"
---
# <a name="modulemodule-constructor"></a>Module::Module Oluşturucusu
Yeni bir örneğini başlatır **Modülü** sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Module();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu oluşturucu korunur ve ile çağrılamaz **yeni** anahtar sözcüğü. Bunun yerine, ya da çağrı [Module::GetModule metodu](../windows/module-getmodule-method.md) veya [Module::Create yöntemi](../windows/module-create-method.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül Sınıfı](../windows/module-class.md)