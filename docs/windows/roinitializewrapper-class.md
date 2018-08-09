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
ms.openlocfilehash: 41eb5e79ca1471fb8c12ffca420a134115fbfcc1
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014045"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper Sınıfı
Windows çalışma zamanı'nı başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
class RoInitializeWrapper  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Roınitializewrapper** Windows çalışma zamanı başlatır ve işlemin başarılı olup olmadığını belirten bir HRESULT döndüren bir kolaylık. Sınıf yok edicisini çağırır çünkü `::Windows::Foundation::Uninitialize`, örneklerini **Roınitializewrapper** genel veya üst düzey kapsamda bildirilmelidir.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[RoInitializeWrapper::RoInitializeWrapper Oluşturucusu](../windows/roinitializewrapper-roinitializewrapper-constructor.md)|Yeni bir örneğini başlatır **Roınitializewrapper** sınıfı.|  
|[RoInitializeWrapper::~RoInitializeWrapper Yıkıcısı](../windows/roinitializewrapper-tilde-roinitializewrapper-destructor.md)|Geçerli örneğini yok eder **Roınitializewrapper** sınıfı.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[RoInitializeWrapper::HRESULT() İşleci](../windows/roinitializewrapper-hresult-parens-operator.md)|Tarafından üretilen HRESULT alır **Roınitializewrapper** Oluşturucusu.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `RoInitializeWrapper`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)