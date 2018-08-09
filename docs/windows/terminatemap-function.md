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
ms.openlocfilehash: de57e03b1e3a150ab96cb72996b48200b153de1c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016713"
---
# <a name="terminatemap-function"></a>TerminateMap İşlevi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
inline bool TerminateMap(  
   _In_ ModuleBase *module,   
   _In_opt_z_ const wchar_t *serverName,   
    bool forceTerminate) throw()  
```  
  
### <a name="parameters"></a>Parametreler  
 *Modülü*  
 A [Modülü](../windows/module-class.md).  
  
 *SunucuAdı*  
 Sınıf üreteçlerini parametresi tarafından belirtilen modüldeki bir alt kümesi adını *Modülü*.  
  
 *forceTerminate*  
 **doğru** sınıfı sonlandırmak için bunlar bağımsız olarak fabrikaları; etkindir **false** herhangi bir Fabrika etkinse sınıf üreteçlerini sona erdirmek.  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** tüm sınıf üreteçlerini, sonlandırılmış; Aksi takdirde **false**.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen modül sınıfı Fabrikalar kapatır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)