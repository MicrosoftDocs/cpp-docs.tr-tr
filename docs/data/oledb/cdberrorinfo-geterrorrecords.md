---
title: "Cdberrorınfo::geterrorrecords | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBErrorInfo.GetErrorRecords
- ATL.CDBErrorInfo.GetErrorRecords
- ATL::CDBErrorInfo::GetErrorRecords
- GetErrorRecords
- CDBErrorInfo::GetErrorRecords
dev_langs: C++
helpviewer_keywords: GetErrorRecords method
ms.assetid: 07746774-bcca-4833-8f55-a619e9777c17
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 584915a27a6f980933cd9aa71f67f6a223f743be
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdberrorinfogeterrorrecords"></a>CDBErrorInfo::GetErrorRecords
Hata kayıtları için belirtilen nesneyi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT GetErrorRecords(   
   IUnknown* pUnk,   
   const IID& iid,   
   ULONG* pcRecords    
) throw( );  
HRESULT GetErrorRecords(   
   ULONG* pcRecords    
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pUnk*  
 [in] Nesne için hata kayıtları almak için arabirim.  
  
 `iid`  
 [in] Şu hata ile ilişkili arabiriminin IID.  
  
 *pcRecords*  
 [out] Hata kaydı (tabanlı) sayısını gösteren bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Hata bilgileri için hangi arabirimi denetlemek istiyorsanız işlevinin ilk biçimini kullanın. Aksi takdirde, ikinci formu kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cdberrorınfo sınıfı](../../data/oledb/cdberrorinfo-class.md)