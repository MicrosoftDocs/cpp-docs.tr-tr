---
title: "CInvalidArgException sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
dev_langs: C++
helpviewer_keywords: CInvalidArgException [MFC], CInvalidArgException
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 03f9bea1c9e5e88856bbf5a5aa2e824a2c99963c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cinvalidargexception-class"></a>CInvalidArgException sınıfı
Bu sınıf, bir geçersiz bağımsız değişken özel durumu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CInvalidArgException : public CSimpleException  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInvalidArgException::CInvalidArgException](#cinvalidargexception)|Oluşturucu.|  
  
## <a name="remarks"></a>Açıklamalar  
 A `CInvalidArgException` nesnesi geçersiz bağımsız değişken özel durum koşulu temsil eder.  
  
 Özel durum işleme hakkında daha fazla bilgi için bkz: [CException sınıfı](../../mfc/reference/cexception-class.md) konu ve [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CInvalidArgException`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="cinvalidargexception"></a>CInvalidArgException::CInvalidArgException  
 Oluşturucu.  
  
```  
CInvalidArgException();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu oluşturucu doğrudan kullanmayın; Genel bir işlevi çağırmak **AfxThrowInvalidArgException**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CSimpleException Sınıfı](../../mfc/reference/csimpleexception-class.md)
