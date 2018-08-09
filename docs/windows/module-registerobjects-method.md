---
title: Module::RegisterObjects yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterObjects
dev_langs:
- C++
helpviewer_keywords:
- RegisterObjects method
ms.assetid: db4077b7-068d-4534-aaa5-41b5444ccb49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 04281b87584d10d36f5f2eeea05dfae0923b2d9f
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013320"
---
# <a name="moduleregisterobjects-method"></a>Module::RegisterObjects Yöntemi
Diğer uygulamalar için bağlanabilmesi için COM veya Windows çalışma zamanı nesneleri kaydeder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT RegisterObjects(  
   ModuleBase* module,   
   const wchar_t* serverName);  
```  
  
### <a name="parameters"></a>Parametreler  
 *Modülü*  
 COM veya Windows çalışma zamanı nesneleri dizisi.  
  
 *SunucuAdı*  
 Nesneleri oluşturan sunucunun adı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, nedenini belirten bir HRESULT, işlem başarısız oldu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
## <a name="see-also"></a>Ayrıca Bkz.
[Modül Sınıfı](../windows/module-class.md)