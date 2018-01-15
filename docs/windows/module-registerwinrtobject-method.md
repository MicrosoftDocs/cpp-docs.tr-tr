---
title: "Module::RegisterWinRTObject yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::RegisterWinRTObject
dev_langs: C++
helpviewer_keywords: RegisterWinRTObject method
ms.assetid: a2782c9c-b9c5-4e4b-9c8d-ef513aea20c5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 279a661fae0def63443c9a42d2f290b8d23fa2a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="moduleregisterwinrtobject-method"></a>Module::RegisterWinRTObject Yöntemi
Diğer uygulamalar için bağlanabilmesi için bir veya daha fazla Windows çalışma zamanı nesneleri kaydeder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT RegisterWinRTObject(const wchar_t* serverName,  
   wchar_t** activatableClassIds,  
   WINRT_REGISTRATION_COOKIE* cookie,  
   unsigned int count)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `serverName`  
 Bu işlem tarafından etkilenen nesneler kümesinin belirtir adı.  
  
 `activatableClassIds`  
 Kaydetmek için activatable CLSID dizisi.  
  
 `cookie`  
 Kaydedilen sınıf nesneleri tanımlayan bir değer. Bu değer daha sonra kaydını iptal etmek için kullanılır.  
  
 `count`  
 Kaydetmek için nesnelerin sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde bir hata nedenini gösterir CO_E_OBJISREG gibi HRESULT işlemi başarısız oldu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül Sınıfı](../windows/module-class.md)