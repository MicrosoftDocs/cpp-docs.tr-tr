---
title: CManualAccessor::CreateAccessor | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CManualAccessor::CreateAccessor
- CreateAccessor
- ATL.CManualAccessor.CreateAccessor
- CManualAccessor.CreateAccessor
- CManualAccessor::CreateAccessor
dev_langs:
- C++
helpviewer_keywords:
- CreateAccessor method
ms.assetid: 594c8d6d-b49a-4818-a9a5-81c8115d4e42
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7d066bec37955d39ecee1fdca5522df843c84442
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cmanualaccessorcreateaccessor"></a>CManualAccessor::CreateAccessor
Bağ yapıları sütunu için bellek ayırır ve sütun veri üyelerine başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
HRESULT CreateAccessor(int nBindEntries,   
  void* pBuffer,   
   DBLENGTH nBufferSize) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nBindEntries`  
 [in] Sütun sayısı. Bu çağrı sayısı ile eşleşmelidir [CManualAccessor::AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md) işlevi.  
  
 `pBuffer`  
 [in] Çıkış sütunlarında depolandığı arabellek için bir işaretçi.  
  
 `nBufferSize`  
 [in] Arabelleğinin bayt cinsinden boyutu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
## <a name="remarks"></a>Açıklamalar  
 Arama yapmadan önce bu işlevi çağırmak `CManualAccessor::AddBindEntry` işlevi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CManualAccessor sınıfı](../../data/oledb/cmanualaccessor-class.md)   
 [DBVIEWER örneği](../../visual-cpp-samples.md)