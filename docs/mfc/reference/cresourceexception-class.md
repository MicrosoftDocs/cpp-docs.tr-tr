---
title: "CResourceException sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
dev_langs: C++
helpviewer_keywords: CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e2e17b859042a5712a998eaeebe9f16f81c91200
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cresourceexception-class"></a>CResourceException sınıfı
Windows bulamıyor veya istenen kaynak tahsis oluşturulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CResourceException : public CSimpleException  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CResourceException::CResourceException](#cresourceexception)|Oluşturan bir `CResourceException` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Başka hiçbir niteliğe gerekli veya olası değil.  
  
 Kullanma hakkında daha fazla bilgi için `CResourceException`, makaleye bakın [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CResourceException`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cresourceexception"></a>CResourceException::CResourceException  
 Oluşturan bir `CResourceException` nesnesi.  
  
```  
CResourceException();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu oluşturucu doğrudan kullanmayın, ancak bunun yerine genel bir işlevi çağırmak [AfxThrowResourceException](exception-processing.md#afxthrowresourceexception). özel durumlar hakkında daha fazla bilgi için bkz: [özel durum işleme MFC'de](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CException sınıfı](cexception-class.md)   
 [Hiyerarşi Grafiği](../hierarchy-chart.md)


