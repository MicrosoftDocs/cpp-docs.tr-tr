---
title: "Module::RegisterCOMObject yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterCOMObject
dev_langs:
- C++
helpviewer_keywords:
- RegisterCOMObject method
ms.assetid: 59f223dc-03c6-429d-95da-b74b3f73b702
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a2984d5950464385ea47301db356b7364707e667
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="moduleregistercomobject-method"></a>Module::RegisterCOMObject Yöntemi
Diğer uygulamalar için bağlanabilmesi için bir veya daha fazla COM nesneleri kaydeder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WRL_NOTHROW virtual HRESULT RegisterCOMObject(  
   const wchar_t* serverName,  
   IID* clsids,  
   IClassFactory** factories,  
   DWORD* cookies,  
   unsigned int count);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `serverName`  
 Bir sunucunun tam adı.  
  
 `clsids`  
 CLSID kaydetmek için bir dizi.  
  
 `factories`  
 IUnknown arabirimi olan kullanılabilirlik yayımlanan sınıfı nesnelerinin bir dizisi.  
  
 `cookies`  
 İşlem tamamlandığında, kaydedilen sınıfı değerleri işaretçiler bir dizi nesneleri. Daha sonra bu değerler kullanılır kaydını iptal etme.  
  
 `count`  
 CLSID kayıt sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 S_OK, saldırgan; Aksi takdirde, HRESULT nedenini gösterir CO_E_OBJISREG gibi işlem başarısız oldu.  
  
## <a name="remarks"></a>Açıklamalar  
 COM nesneleri CLSCTX numaralandırma CLSCTX_LOCAL_SERVER Numaralandırıcı ile kaydedilir.  
  
 Kayıtlı nesnelere bağlantı türü geçerli bir birleşimi tarafından belirtilen `comflag` şablon parametresi ve REGCLS numaralandırma REGCLS_SUSPENDED Numaralandırıcı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül Sınıfı](../windows/module-class.md)