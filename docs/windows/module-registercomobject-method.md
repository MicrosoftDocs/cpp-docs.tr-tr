---
title: Module::RegisterCOMObject yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterCOMObject
dev_langs:
- C++
helpviewer_keywords:
- RegisterCOMObject method
ms.assetid: 59f223dc-03c6-429d-95da-b74b3f73b702
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c002dd64049006c8ee74c709c585a3a9d0f253a5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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