---
title: "CMemoryException sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
dev_langs: C++
helpviewer_keywords: CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 13130321dd26612b2bbd24457e02e09ce5fe1ec6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmemoryexception-class"></a>CMemoryException sınıfı
Bir bellek yetersiz özel durumu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMemoryException : public CSimpleException  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMemoryException::CMemoryException](#cmemoryexception)|Oluşturan bir `CMemoryException` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Başka hiçbir niteliğe gerekli veya olası değil. Bellek özel durumlar tarafından otomatik olarak **yeni**. Kendi bellek işlevleri yazarsanız, kullanarak `malloc`, örnek olduktan sonra bellek özel durumları atma için sorumlu için.  
  
 Daha fazla bilgi için `CMemoryException`, makaleye bakın [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CMemoryException`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="cmemoryexception"></a>CMemoryException::CMemoryException  
 Oluşturan bir `CMemoryException` nesnesi.  
  
```  
CMemoryException();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu oluşturucu doğrudan kullanmayın, ancak bunun yerine genel bir işlevi çağırmak [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). Bu genel işlevi, önceden ayrılmış belleğe özel durum nesnesi oluşturur çünkü bir bellek yetersiz durumda başarılı olabilir. özel durum işleme hakkında daha fazla bilgi için bkz: [özel durumları](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CException sınıfı](cexception-class.md)   
 [Hiyerarşi grafiği](../hierarchy-chart.md)



