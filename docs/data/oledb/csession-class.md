---
title: "CSession sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSession
- ATL::CSession
- ATL.CSession
dev_langs: C++
helpviewer_keywords: CSession class
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d8b6bb75d12b4ab96c3a44c74f4487eb8a70efc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csession-class"></a>CSession Sınıfı
Tek veritabanı erişim oturumu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSession  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Durdurma](../../data/oledb/csession-abort.md)|İptal eder (sonlandırır) işlem.|  
|[Kapat](../../data/oledb/csession-close.md)|Oturumunu kapatır.|  
|[Tamamlama](../../data/oledb/csession-commit.md)|İşlem kaydeder.|  
|[Gettransactionınfo](../../data/oledb/csession-gettransactioninfo.md)|Bir işlem ile ilgili bilgiler döndürür.|  
|[Açık](../../data/oledb/csession-open.md)|Veri kaynağı nesnesi için yeni bir oturum açar.|  
|[StartTransaction](../../data/oledb/csession-starttransaction.md)|Bu oturum için yeni bir işlem başlatır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir veya daha fazla oturum ilişkilendirilebilir tarafından temsil edilen her sağlayıcı bağlantısı (veri kaynağı) ile bir [CDataSource](../../data/oledb/cdatasource-class.md) nesnesi. Yeni `CSession` için bir `CDataSource`, çağrı [CSession::Open](../../data/oledb/csession-open.md). Bir veritabanı işlemi başlatmak için `CSession` sağlar `StartTransaction` yöntemi. Bir işlem başladıktan sonra onu kullanarak onaylayabilirsiniz **tamamlama** yöntemini veya kullanarak iptal **Abort** yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CatDB](../../visual-cpp-samples.md)   
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)