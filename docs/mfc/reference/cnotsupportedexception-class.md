---
title: "CNotSupportedException sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
dev_langs: C++
helpviewer_keywords: CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4013b26e3c07d6ec2a729bf9868db48923e35f86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cnotsupportedexception-class"></a>CNotSupportedException sınıfı
Desteklenmeyen bir özellik için bir istek sonucu bir özel durumu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CNotSupportedException : public CSimpleException  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CNotSupportedException::CNotSupportedException](#cnotsupportedexception)|Oluşturan bir `CNotSupportedException` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Başka hiçbir niteliğe gerekli veya olası değil.  
  
 Kullanma hakkında daha fazla bilgi için `CNotSupportedException`, makaleye bakın [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CNotSupportedException`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="cnotsupportedexception"></a>CNotSupportedException::CNotSupportedException  
 Oluşturan bir `CNotSupportedException` nesnesi.  
  
```  
CNotSupportedException();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu oluşturucu doğrudan kullanmayın, ancak bunun yerine genel bir işlevi çağırmak [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception). özel durum işleme hakkında daha fazla bilgi için bkz: [özel durum işleme MFC'de](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CException sınıfı](cexception-class.md)   
 [Hiyerarşi Grafiği](../hierarchy-chart.md)


