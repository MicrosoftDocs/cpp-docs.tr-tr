---
title: "Platform::AccessDeniedException sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::AccessDeniedException
- VCCORLIB/Platform::AccessDeniedException::AccessDeniedException
dev_langs: C++
helpviewer_keywords: Platform::AccessDeniedException
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f2e39acbd87dffc6bd0ffdeb483ada1eb1c6cc52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="platformaccessdeniedexception-class"></a>Platform::AccessDeniedException sınıfı
Oluşturulan kaynak eriştiğinizde veya özellik engellendi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
public ref class AccessDeniedException : COMException,    IException,    IPrintable,   IEquatable  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu özel durumun isabet durumunda uygun özellik istenir ve gerekli bildirimleri, uygulamanızın paket bildirimi yapılan emin olun. Daha fazla bilgi için bkz: [COMException](../cppcx/platform-comexception-class.md) sınıfı.  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Meta veriler:** platform.winmd  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform::COMException Sınıfı](../cppcx/platform-comexception-class.md)