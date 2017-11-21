---
title: "Module::UnregisterObjects yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::UnregisterObjects
dev_langs: C++
helpviewer_keywords: UnregisterObjects method
ms.assetid: 3d8119a7-991d-45e9-b8c5-ed36c0be0332
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6f62ae76b0ff86c11ab0bc347550fe27b406acb5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="moduleunregisterobjects-method"></a>Module::UnregisterObjects Yöntemi
Böylece diğer uygulamalar için bağlanamıyor Belirtilen modül nesneleri kaydını siler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT UnregisterObjects(  
   ModuleBase* module,  
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `module`  
 Bir modül işaretçi.  
  
 `serverName`  
 Bu işlem tarafından etkilenen nesneler kümesinin belirtir belirleme adı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlem başarılı olursa S_OK; Aksi takdirde bir hata nedenini gösterir HRESULT bu işlemi başarısız oldu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül sınıfı](../windows/module-class.md)