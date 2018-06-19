---
title: CDynamicAccessor::CDynamicAccessor | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor::CDynamicAccessor
- ATL::CDynamicAccessor::CDynamicAccessor
- ATL.CDynamicAccessor.CDynamicAccessor
- CDynamicAccessor.CDynamicAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicAccessor class, constructor
ms.assetid: bf40fe81-2c85-473e-9075-51ad9b060b39
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 80446719ac8e523efc5ef885fe55fb89561509e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090607"
---
# <a name="cdynamicaccessorcdynamicaccessor"></a>CDynamicAccessor::CDynamicAccessor
Oluşturur ve başlatır `CDynamicAccessor` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      CDynamicAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `eBlobHandling`  
 Nasıl ikili büyük nesne (BLOB) veri işleneceğini belirtir. Varsayılan değer **DBBLOBHANDLING_DEFAULT**. Bkz: [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) bir açıklaması için **DBBLOBHANDLINGENUM** değerleri.  
  
 `nBlobSize`  
 Bayt cinsinden en büyük BLOB boyutu; Bu değer sütun verilerinde BLOB olarak kabul edilir. 8000 varsayılan değerdir. Bkz: [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) Ayrıntılar için.  
  
## <a name="remarks"></a>Açıklamalar  
 Başlatmak için Oluşturucusu kullanırsanız `CDynamicAccessor` nesnesi, BLOB'ları nasıl bağlayacaksınız belirtebilirsiniz. BLOB grafikler, ses veya derlenmiş kod gibi ikili veriler içerebilir. Sütunları 8.000 bayttan fazla BLOB olarak kabul eder ve bunları bağlamak denemek için varsayılan davranıştır bir `ISequentialStream` nesnesi. Bununla birlikte, BLOB boyutu için farklı bir değer belirtebilirsiniz.  
  
 De belirtebilirsiniz nasıl `CDynamicAccessor` BLOB verisi olarak niteleyen sütun veri işleme: BLOB verileri varsayılan şekilde işleyebilir; bunu atlayabilirsiniz (bağlanmaz) BLOB verilerini; veya bağlayabilirsiniz BLOB veri sağlayıcısı ayrılmış bellek.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)