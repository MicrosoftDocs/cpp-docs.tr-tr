---
title: "CUserException sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUserException
dev_langs:
- C++
helpviewer_keywords:
- operations [MFC], stopping
- exceptions [MFC], throwing
- CUserException class [MFC]
- errors [MFC], trapping
- operations [MFC]
- throwing exceptions [MFC], stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4613f2ba06ffa697df219172b98a5cf193c1f3b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cuserexception-class"></a>CUserException sınıfı
Bir son kullanıcı işlemi durdurmak için oluşturulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CUserException : public CSimpleException  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanmak `CUserException` throw/catch özel durum mekanizması için uygulamaya özgü özel durumları kullanmak istediğinizde. Sınıf adı "kullanıcı" yorumlanabilen "Benim Kullanıcı işlemek gereken olağanüstü bir şey gibi."  
  
 A `CUserException` genellikle genel işlevi çağırdıktan sonra atılır `AfxMessageBox` bir işlem başarısız oldu kullanıcıya bildirmek için. Özel durum işleyicisi yazma, özel kullanıcı genellikle zaten hata bildirildi beri özel durumu işler. Framework bazı durumlarda bu özel durum oluşturur. Throw için bir `CUserException` kendiniz kullanıcıyı uyarmak ve genel işlevini çağırın `AfxThrowUserException`.  
  
 Aşağıdaki örnekte, başlatılamayabilir işlemleri içeren bir işlev kullanıcıyı uyarır ve oluşturur bir `CUserException`. Çağıran işlev özel durum yakalar ve özel işler:  
  
 [!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]  
  
 Kullanma hakkında daha fazla bilgi için `CUserException`, makaleye bakın [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CUserException`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CException Sınıfı](../../mfc/reference/cexception-class.md)
