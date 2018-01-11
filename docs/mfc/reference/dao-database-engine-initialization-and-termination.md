---
title: "DAO veritabanı motoru başlatma ve sonlandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros.data
dev_langs: C++
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 32dbcb02615f552a2bb26ec047b0b817bb828a95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dao-database-engine-initialization-and-termination"></a>DAO Veritabanı Motoru Başlatma ve Sonlandırma
MFC DAO nesneleri kullanılırken DAO veritabanı motoru ilk olmalıdır başlatılmadı ve sonra sonlandırılan uygulamanızı veya DLL sonlandırılmadan önce. İki işlevleri `AfxDaoInit` ve `AfxDaoTerm`, bu görevleri gerçekleştirin.  
  
### <a name="dao-database-engine-initialization-and-termination"></a>DAO Veritabanı Motoru Başlatma ve Sonlandırma  
  
|||  
|-|-|  
|[Afxdaoınit](#afxdaoinit)|DAO veritabanı motoru başlatır.|  
|[AfxDaoTerm](#afxdaoterm)|DAO veritabanı motoru sonlandırır.|  
  
##  <a name="afxdaoinit"></a>Afxdaoınit  
 Bu işlev DAO veritabanı motoru başlatır.  
  
```  
 
void AfxDaoInit();

throw(CDaoException*);  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çoğu durumda, çağrı gerekmez `AfxDaoInit` çünkü gerektiğinde uygulama otomatik olarak çağırır.  
  
 Çağırma örneği ve ilgili bilgiler için `AfxDaoInit`, bkz: [Teknik Not 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdao.h  
  
##  <a name="afxdaoterm"></a>AfxDaoTerm  
 Bu işlev DAO veritabanı motoru sonlandırır.  
  
```  
 
void AfxDaoTerm();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, yalnızca Normal MFC DLL bu işlevi çağırmak gerekir; bir uygulamayı otomatik olarak çağıracaktır `AfxDaoTerm` ne zaman yapılması gerekiyor.  
  
 Normal MFC DLL'lerde çağrısı `AfxDaoTerm` önce `ExitInstance` işlevi, ancak tüm MFC DAO nesneler yok.  
  
 İlgili bilgi için bkz: [Teknik Not 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  

### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdao.h  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
