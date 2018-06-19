---
title: TerminateMap işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
dev_langs:
- C++
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b4787fec0a6b4b9f55c500b66786372945d9a523
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890355"
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
 `true` sınıf sonlandırmak için oluşturucuları bunlar bağımsız olarak etkindir; `false` herhangi Fabrika etkinse sınıfı Fabrikalar sona erdirmek.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `true` tüm sınıf oluşturucuları sonlandırılmış Aksi takdirde `false`.  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf oluşturucuları belirtilen modülde kapatır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)