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
ms.openlocfilehash: 61ebc6b7bfb0571ba1f2ce1957d916ecb4c790c7
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010990"
---
# <a name="moduleregistercomobject-method"></a>Module::RegisterCOMObject Yöntemi
Diğer uygulamalar için bağlanabilmesi için bir veya daha fazla COM nesneleri kaydeder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
WRL_NOTHROW virtual HRESULT RegisterCOMObject(  
   const wchar_t* serverName,  
   IID* clsids,  
   IClassFactory** factories,  
   DWORD* cookies,  
   unsigned int count);  
  
```  
  
### <a name="parameters"></a>Parametreler  
 *SunucuAdı*  
 Bir sunucunun tam adı.  
  
 *CLSID*  
 CLSID kaydetmek için bir dizi.  
  
 *fabrikaları*  
 IUnknown arabirimi olan kullanılabilirlik yayımlanan sınıf nesnelerinin dizisi.  
  
 *Tanımlama bilgileri*  
 İşlem tamamlandığında, kayıtlı olan bir sınıfı değerleri için işaretçiler dizisi nesneleri. Bu değerler daha sonra kullanılır kaydını iptal etme.  
  
 *Sayısı*  
 Kaydedilecek CLSID sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 S_OK varsa saldırgan; Aksi takdirde, bir HRESULT nedenini belirten CO_E_OBJISREG gibi işlem başarısız oldu.  
  
## <a name="remarks"></a>Açıklamalar  
 COM nesnelerinin CLSCTX numaralandırma CLSCTX_LOCAL_SERVER Numaralandırıcı ile kaydedilir.  
  
 Kayıtlı nesneler için bağlantı türü, geçerli bir birleşimi tarafından belirtilen *comflag* şablon parametresi ile REGCLS numaralandırma REGCLS_SUSPENDED Numaralandırıcı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Modül Sınıfı](../windows/module-class.md)