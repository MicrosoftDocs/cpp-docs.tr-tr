---
title: Platform::metadata Namespace | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata
dev_langs:
- C++
helpviewer_keywords:
- Platform::Metadata Namespace
ms.assetid: e3e114d8-a4b0-47f0-865a-9ce9d7212e86
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1a755314adec83e8853c2c29d9c9d9bb363575b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607812"
---
# <a name="platformmetadata-namespace"></a>Platform::metadata Namespace
Bu ad alanı türlerinin bildirimlerini değiştirme öznitelikleri içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
namespace Platform {  
   namespace Metadata {  
}}  
```  
  
### <a name="members"></a>Üyeler  
 Bu ad dahili kullanım içindir ancak tarayıcılar bu ad aşağıdaki üyeleri görüntüleyebilir.  
  
|Ad|Açıklama|  
|----------|------------|  
|Öznitelik|Öznitelikleri için temel sınıfı.|  
|[Platform::Metadata::DefaultMemberAttribute Özniteliği](../cppcx/platform-metadata-defaultmemberattribute-attribute.md)|Birkaç olası aşırı yüklenmiş işlevleri çağırmak için tercih edilen işlev gösterir.|  
|[Platform::metadata:: FlagsAttribute özniteliği](../cppcx/platform-metadata-flagsattribute-attribute.md)bayrakları|Sabit bir numaralandırma bit alanları olarak bildirir.<br /><br /> Aşağıdaki örnek nasıl uygulanacağını gösterir `Flags` numaralandırma özniteliği.<br /><br /> `[Flags] enum class MyEnumeration { enumA = 1, enumB = 2, enumC = 3}`|  
|[Platform::metadata::RuntimeClassNameAttribute](../cppcx/platform-metadata-runtimeclassname.md)|Özel bir başvuru sınıfı, geçerli çalışma zamanı sınıf adı sahip olmasını sağlar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Platform`  
  
### <a name="requirements"></a>Gereksinimler  
 **Meta veri:** platform.winmd  
  
 **Namespace:** Platform::Metadata  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)