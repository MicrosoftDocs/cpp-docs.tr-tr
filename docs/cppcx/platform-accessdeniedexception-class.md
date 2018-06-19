---
title: Platform::AccessDeniedException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::AccessDeniedException
- VCCORLIB/Platform::AccessDeniedException::AccessDeniedException
dev_langs:
- C++
helpviewer_keywords:
- Platform::AccessDeniedException
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4be26bfc87be55d36954429c64094cabd6a6cf9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33087620"
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