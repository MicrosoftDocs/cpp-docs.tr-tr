---
title: "Module::UnregisterCOMObject yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::UnregisterCOMObject
dev_langs: C++
helpviewer_keywords: UnregisterCOMObject method
ms.assetid: 5d377525-0385-482a-a215-6e8a1f032861
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 45a6dc776feb1534cd7e58240a40cc173e7459de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
  
#### <a name="parameters"></a>Parametreler  
 `serverName`  
 (Kullanılmaz)  
  
 `cookies`  
 İçin sona erdirilecek sınıfı nesneleri tanımlamak değerlerini dizisi. Dizi tarafından oluşturulan [RegisterCOMObject](../windows/module-registercomobject-method.md) yöntemi.  
  
 `count`  
 Kaydını kaldırmak üzere sınıfları sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlem başarılı olursa S_OK; Aksi takdirde bir hata nedenini gösterir HRESULT işlemi başarısız oldu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül Sınıfı](../windows/module-class.md)