---
title: CColumnAccessor sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
dev_langs:
- C++
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8d211277a8354d94f1892b97ea8f808cc0b22c30
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095326"
---
# <a name="ccolumnaccessor-class"></a>CColumnAccessor Sınıfı
Eklenen tüketici kod oluşturur.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CColumnAccessor : public CAccessorBase  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Eklenen kod içinde her sütun ayrı bir erişimci bağlıdır. Bu sınıf eklenen kodda kullanılır farkında olmalıdır (örneğin, bu hata ayıklama sırasında karşılaşabileceğiniz), ancak genellikle hiçbir zaman veya yöntemlerinden doğrudan kullanmanız gerekir.  
  
 `CColumnAccessor` her biri karşılık gelen diğer erişimci sınıfı yöntemlerine işlevsellik aşağıdaki saplama yöntemlerini uygular:  
  
-   `CColumnAccessor` Oluşturucusu oluşturur ve başlatır `CColumnAccessor` nesnesi.  
  
-   `CreateAccessor` Bağlama yapıları sütunu için bellek ayırır ve sütun veri üyelerine başlatır.  
  
-   **BindColumns** sütunlar için erişimciler bağlar.  
  
-   **SetParameterBuffer** arabellekleri için parametreleri ayırır.  
  
-   `AddParameter` Parametre giriş parametresi giriş yapılara ekler.  
  
-   **HasOutputColumns** erişimci sütunları çıktısı olup olmadığını belirler  
  
-   **HasParameters** erişimci parametreleri olup olmadığını belirler.  
  
-   `BindParameters` Oluşturulan parametre sütunları bağlar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)