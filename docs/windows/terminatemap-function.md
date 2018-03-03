---
title: "TerminateMap işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
dev_langs:
- C++
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 42f71f86dce35457d5efa81c28d2a58106ba5b81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="terminatemap-function"></a>TerminateMap İşlevi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline bool TerminateMap(  
   _In_ ModuleBase *module,   
   _In_opt_z_ const wchar_t *serverName,   
    bool forceTerminate) throw()  
```  
  
## <a name="parameters"></a>Parametreler  
 `module`  
 A [Modülü](../windows/module-class.md).  
  
 `serverName`  
 Sınıf oluşturucuları parametresi tarafından belirtilen modüldeki bir kısmı adını `module`.  
  
 `forceTerminate`  
 `true`sınıf sonlandırmak için oluşturucuları bunlar bağımsız olarak etkindir; `false` herhangi Fabrika etkinse sınıfı Fabrikalar sona erdirmek.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true`tüm sınıf oluşturucuları sonlandırılmış Aksi takdirde `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf oluşturucuları belirtilen modülde kapatır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)