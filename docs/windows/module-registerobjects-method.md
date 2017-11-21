---
title: "Module::RegisterObjects yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::RegisterObjects
dev_langs: C++
helpviewer_keywords: RegisterObjects method
ms.assetid: db4077b7-068d-4534-aaa5-41b5444ccb49
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fbff1d4c16c8cfb4f265760a6919637808efe28d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="moduleregisterobjects-method"></a>Module::RegisterObjects Yöntemi
Diğer uygulamalar için bağlanabilmesi için COM veya Windows çalışma zamanı nesneleri kaydeder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT RegisterObjects(  
   ModuleBase* module,   
   const wchar_t* serverName);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `module`  
 COM veya Windows çalışma zamanı nesnelerinin bir dizisi.  
  
 `serverName`  
 Nesneleri oluşturma sunucunun adıdır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, nedenini belirten bir HRESULT işlemi başarısız oldu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
## <a name="see-also"></a>Ayrıca Bkz.
[Modül sınıfı](../windows/module-class.md)