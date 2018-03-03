---
title: "CSecurityAttributes sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
dev_langs:
- C++
helpviewer_keywords:
- CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 918f90c9f04736eb2328d989e21b7b9997edab86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csecurityattributes-class"></a>CSecurityAttributes sınıfı
Güvenlik öznitelikleri yapısı için ince sarmalayıcı sınıftır.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSecurityAttributes::CSecurityAttributes](#csecurityattributes)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSecurityAttributes::Set](#set)|Öznitelikleri ayarlamak için bu yöntemi çağırın `CSecurityAttributes` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 **SECURITY_ATTRIBUTES** yapısının bir [güvenlik tanımlayıcısı](http://msdn.microsoft.com/library/windows/desktop/aa379561) bir nesne oluşturmak için kullanılan ve bu yapı belirterek alınan tanıtıcı devralınabilir olup olmadığını belirtir.  
  
 Erişim denetimi modeli Windows giriş için bkz: [erişim denetimi](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows SDK'sındaki.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `SECURITY_ATTRIBUTES`  
  
 `CSecurityAttributes`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsecurity.h  
  
##  <a name="csecurityattributes"></a>CSecurityAttributes::CSecurityAttributes  
 Oluşturucu.  
  
```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rSecurityDescriptor`  
 Güvenlik tanımlayıcısı başvuru.  
  
 `bInheritsHandle`  
 Yeni bir işlem oluşturulduğunda döndürülen tanıtıcı devralınan olup olmadığını belirtir. Bu üye true ise, yeni işlem tanıtıcısı devralır.  
  
##  <a name="set"></a>CSecurityAttributes::Set  
 Öznitelikleri ayarlamak için bu yöntemi çağırın `CSecurityAttributes` nesnesi.  
  
```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rSecurityDescriptor`  
 Güvenlik tanımlayıcısı başvuru.  
  
 `bInheritHandle`  
 Yeni bir işlem oluşturulduğunda döndürülen tanıtıcı devralınan olup olmadığını belirtir. Bu üye true ise, yeni işlem tanıtıcısı devralır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından Oluşturucusu başlatmak için kullanılan `CSecurityAttributes` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenliği örneği](../../visual-cpp-samples.md)   
 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)   
 [Güvenlik tanımlayıcısı](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
