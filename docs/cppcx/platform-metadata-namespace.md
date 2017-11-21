---
title: Platform::metadata Namespace | Microsoft Docs
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::Metadata
dev_langs: C++
helpviewer_keywords: Platform::Metadata Namespace
ms.assetid: e3e114d8-a4b0-47f0-865a-9ce9d7212e86
caps.latest.revision: "6"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 7c108dd9435d433076ea2f2c9b573f2ebf3685e3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="platformmetadata-namespace"></a>Platform::metadata Namespace
Bu ad alanı bildirimleri türlerinin değiştirme öznitelikleri içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
namespace Platform {  
   namespace Metadata {  
}}  
```  
  
### <a name="members"></a>Üyeler  
 Bu ad alanı iç kullanım için tasarlanmıştır ancak tarayıcılar bu ad aşağıdaki üyeleri görüntüleyebilir.  
  
|Ad|Açıklama|  
|----------|------------|  
|Öznitelik|Öznitelikleri için temel sınıf.|  
|[Platform::metadata::DefaultMemberAttribute özniteliği](../cppcx/platform-metadata-defaultmemberattribute-attribute.md)|Birkaç olası aşırı yüklenmiş işlevlerin çağırmak için tercih edilen işlev gösterir.|  
|[Platform::metadata::FlagsAttribute özniteliği](../cppcx/platform-metadata-flagsattribute-attribute.md)bayrakları|Sabit bit alanları numaralandırması olarak bildirir.<br /><br /> Aşağıdaki örnekte nasıl uygulanacağını gösterir `Flags` numaralandırma özniteliği.<br /><br /> `[Flags] enum class MyEnumeration { enumA = 1, enumB = 2, enumC = 3}`|  
|[Platform::metadata::RuntimeClassNameAttribute](../cppcx/platform-metadata-runtimeclassname.md)|Bir özel ref sınıf geçerli çalışma zamanı sınıf adı sahip olmasını sağlar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Platform`  
  
### <a name="requirements"></a>Gereksinimler  
 **Meta veriler:** platform.winmd  
  
 **Namespace:** Platform::Metadata  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)