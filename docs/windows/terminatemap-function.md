---
title: "TerminateMap işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Details::TerminateMap
dev_langs: C++
helpviewer_keywords: TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: efe6b143c2fe9a48a008f9005244178b436d170e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)