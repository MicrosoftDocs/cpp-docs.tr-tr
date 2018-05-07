---
title: CDynamicAccessor::SetBlobHandling | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor::SetBlobHandling
- CDynamicAccessor.SetBlobHandling
- ATL::CDynamicAccessor::SetBlobHandling
- SetBlobHandling
- ATL.CDynamicAccessor.SetBlobHandling
dev_langs:
- C++
helpviewer_keywords:
- SetBlobHandling method
ms.assetid: fa8b0bb3-a21b-4d64-aeef-e79bf61d079c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8ee2c2d57f9f413346bb33a178fc3d8fa90439e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicaccessorsetblobhandling"></a>CDynamicAccessor::SetBlobHandling
Geçerli satır değeri işleme BLOB ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      bool SetBlobHandling(DBBLOBHANDLINGENUM eBlobHandling);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `eBlobHandling`  
 Nasıl BLOB verilerini işleneceğini belirtir. Aşağıdaki değerleri alabilir:  
  
-   **DBBLOBHANDLING_DEFAULT**: işlemek sütun veri büyük `nBlobSize` (tarafından ayarlanmış `SetBlobSizeLimit`) olarak BLOB veri ve üzerinden almak bir `ISequentialStream` veya `IStream` nesnesi. Bu seçenek daha büyük veri içeren her bir sütun bağlama dener `nBlobSize` veya olarak listelenen **DBTYPE_IUNKNOWN** BLOB verisi olarak.  
  
-   **DBBLOBHANDLING_NOSTREAMS**: işlemek sütun veri büyük `nBlobSize` (tarafından ayarlanmış `SetBlobSizeLimit`) olarak BLOB veri ve tüketici ait sağlayıcı tarafından ayrılan bellek başvurusunda üzerinden almak. Bu seçenek, birden fazla BLOB sütuna sahip tablolar için yararlıdır ve yalnızca bir sağlayıcının desteklediği `ISequentialStream` erişimci her nesne.  
  
-   **DBBLOBHANDLING_SKIP**: Atla (bağlamayın) BLOB'lar içerecek şekilde niteleme sütunlar (erişimcisi değil bağlamak veya sütun değeri almak ancak hala sütun durum ve uzunluk alacaktır).  
  
## <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız `SetBlobHandling` çağırmadan önce **açık**.  
  
 Yapıcı yöntemi [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) değerine işleme BLOB ayarlar **DBBLOBHANDLING_DEFAULT**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)