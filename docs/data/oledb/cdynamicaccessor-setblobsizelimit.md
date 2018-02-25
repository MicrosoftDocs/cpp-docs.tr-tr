---
title: CDynamicAccessor::SetBlobSizeLimit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicAccessor::SetBlobSizeLimit
- SetBlobSizeLimit
- CDynamicAccessor.SetBlobSizeLimit
- ATL.CDynamicAccessor.SetBlobSizeLimit
- ATL::CDynamicAccessor::SetBlobSizeLimit
dev_langs:
- C++
helpviewer_keywords:
- SetBlobSizeLimit method
ms.assetid: fb8cb85d-f841-408e-a344-37895b10993f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a2fac05c1380e2b612cb39994716387d99bef237
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicaccessorsetblobsizelimit"></a>CDynamicAccessor::SetBlobSizeLimit
KABARCIK boyutunu bayt cinsinden ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      void SetBlobSizeLimit(DBLENGTH nBlobSize);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nBlobSize`  
 BLOB boyut sınırını belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 KABARCIK boyutunu bayt olarak ayarlar; sütun verileri bu değerden daha büyük bir BLOB olarak kabul edilir. Bazı sağlayıcılar sütunlar (örneğin, 2 GB) için son derece büyük boyutları verin. Bu boyutta bir sütun için bellek ayrılamadı çalışırken yerine, genellikle bu sütunları BLOB olarak bağlamak isteriz. Bu şekilde tüm belleği ayırmaya gerekmez, ancak hala kesilmesi korkusu olmadan tüm verileri okuyabilir. Ancak, istediğiniz zorlamak bazı durumlar vardır `CDynamicAccessor` kendi yerel veri türlerinde büyük sütunları bağlamak için. Bunu yapmak için arama `SetBlobSizeLimit` çağırmadan önce **açık**.  
  
 Yapıcı yöntemi [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) BLOB boyutu üst sınırı 8.000 bayt varsayılan değerine ayarlar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)