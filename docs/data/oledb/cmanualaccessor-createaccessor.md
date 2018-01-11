---
title: CManualAccessor::CreateAccessor | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CManualAccessor::CreateAccessor
- CreateAccessor
- ATL.CManualAccessor.CreateAccessor
- CManualAccessor.CreateAccessor
- CManualAccessor::CreateAccessor
dev_langs: C++
helpviewer_keywords: CreateAccessor method
ms.assetid: 594c8d6d-b49a-4818-a9a5-81c8115d4e42
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f313e6d2b13a03a91295c75d52e4e77d5dfda22b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmanualaccessorcreateaccessor"></a>CManualAccessor::CreateAccessor
Bağ yapıları sütunu için bellek ayırır ve sütun veri üyelerine başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT CreateAccessor(   
   int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize    
) throw( );  
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