---
title: Roınitializewrapper sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 05/20/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
dev_langs:
- C++
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cac71857e6b472f11d1c9eaba48d181ea78fb456
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705598"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper Sınıfı
Windows çalışma zamanı başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class RoInitializeWrapper  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Roınitializewrapper Windows çalışma zamanı başlatır ve işlemin başarılı olup olmadığını belirten bir HRESULT döndüren kullanışlı olur. Sınıf yıkıcı çağrıları çünkü `::Windows::Foundation::Uninitialize`, örneklerini `RoInitializeWrapper` genel ya da üst düzey kapsamında bildirilmelidir.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[RoInitializeWrapper::RoInitializeWrapper Oluşturucusu](../windows/roinitializewrapper-roinitializewrapper-constructor.md)|Roınitializewrapper sınıfının yeni bir örneğini başlatır.|  
|[RoInitializeWrapper::~RoInitializeWrapper Yıkıcısı](../windows/roinitializewrapper-tilde-roinitializewrapper-destructor.md)|Roınitializewrapper sınıfının geçerli örneği yok eder.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[RoInitializeWrapper::HRESULT() İşleci](../windows/roinitializewrapper-hresult-parens-operator.md)|Roınitializewrapper oluşturucusu tarafından üretilen HRESULT alır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `RoInitializeWrapper`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)