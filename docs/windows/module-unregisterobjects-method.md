---
title: Module::UnregisterObjects yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterObjects
dev_langs:
- C++
helpviewer_keywords:
- UnregisterObjects method
ms.assetid: 3d8119a7-991d-45e9-b8c5-ed36c0be0332
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b711338c436eda3e64d9b51ef0d3137975d834a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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
 [Modül Sınıfı](../windows/module-class.md)