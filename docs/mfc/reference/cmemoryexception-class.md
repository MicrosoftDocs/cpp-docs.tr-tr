---
title: CMemoryException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
dev_langs:
- C++
helpviewer_keywords:
- CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12971af6bed7c04c6f6f214f0b583a4f7e6eb7a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
  
##  <a name="cmemoryexception"></a>  CMemoryException::CMemoryException  
 Oluşturan bir `CMemoryException` nesnesi.  
  
```  
CMemoryException();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu oluşturucu doğrudan kullanmayın, ancak bunun yerine genel bir işlevi çağırmak [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). Bu genel işlevi, önceden ayrılmış belleğe özel durum nesnesi oluşturur çünkü bir bellek yetersiz durumda başarılı olabilir. özel durum işleme hakkında daha fazla bilgi için bkz: [özel durumları](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CException sınıfı](cexception-class.md)   
 [Hiyerarşi Grafiği](../hierarchy-chart.md)



