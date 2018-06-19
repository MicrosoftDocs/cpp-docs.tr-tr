---
title: CSession sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSession
- ATL::CSession
- ATL.CSession
dev_langs:
- C++
helpviewer_keywords:
- CSession class
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 03c0bfec758bb663803b05b1f690816394f61239
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097087"
---
# <a name="csession-class"></a>CSession Sınıfı
Tek veritabanı erişim oturumu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CSession  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Durdurma](../../data/oledb/csession-abort.md)|İptal eder (sonlandırır) işlem.|  
|[Kapat](../../data/oledb/csession-close.md)|Oturumunu kapatır.|  
|[Tamamlama](../../data/oledb/csession-commit.md)|İşlem kaydeder.|  
|[GetTransactionInfo](../../data/oledb/csession-gettransactioninfo.md)|Bir işlem ile ilgili bilgiler döndürür.|  
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