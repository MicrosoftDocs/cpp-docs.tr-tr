---
title: CUserException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1701f6894ba3b44205526c59bad7ef635c1bbbd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369479"
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
