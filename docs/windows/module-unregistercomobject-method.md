---
title: Module::UnregisterCOMObject yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterCOMObject
dev_langs:
- C++
helpviewer_keywords:
- UnregisterCOMObject method
ms.assetid: 5d377525-0385-482a-a215-6e8a1f032861
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c19e7b5388438b8c3c2359672360e4a2ee3001a3
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39602636"
---
# <a name="moduleunregistercomobject-method"></a>Module::UnregisterCOMObject Yöntemi
Bir veya daha fazla COM nesneleri, diğer uygulamalar için bağlanmasını engelleyen kaydını siler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
virtual HRESULT UnregisterCOMObject(  
   const wchar_t* serverName,  
   DWORD* cookies,  
   unsigned int count  
```  
  
### <a name="parameters"></a>Parametreler  
 *SunucuAdı*  
 (Kullanılmayan)  
  
 *Tanımlama bilgileri*  
 Sınıf nesneleri silinmesine izin değerleri için işaretçiler dizisi. Dizi tarafından oluşturulan [RegisterCOMObject](../windows/module-registercomobject-method.md) yöntemi.  
  
 *Sayısı*  
 Sınıfların kaydını sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlem başarılı olursa S_OK; Aksi takdirde bir hata nedenini belirten HRESULT işlemi başarısız oldu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül Sınıfı](../windows/module-class.md)