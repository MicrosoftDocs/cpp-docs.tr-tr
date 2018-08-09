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
ms.openlocfilehash: d63b90bb3622129589fca41c029f548a07ec21b8
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017662"
---
# <a name="modulemodule-constructor"></a>Module::Module Oluşturucusu
Yeni bir örneğini başlatır **Modülü** sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
Module();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu oluşturucu korunur ve ile çağrılamaz **yeni** anahtar sözcüğü. Bunun yerine, ya da çağrı [Module::GetModule metodu](../windows/module-getmodule-method.md) veya [Module::Create yöntemi](../windows/module-create-method.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül Sınıfı](../windows/module-class.md)