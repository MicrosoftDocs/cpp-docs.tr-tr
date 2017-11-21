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
ms.openlocfilehash: 497ced5337a44bb0d72be734cfea35a30ead383b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Hiyerarşi grafiği](../hierarchy-chart.md)


