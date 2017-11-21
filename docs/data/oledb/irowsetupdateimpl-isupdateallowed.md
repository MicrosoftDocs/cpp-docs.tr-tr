---
title: "IRowsetUpdateImpl::ısupdateallowed | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
dev_langs: C++
helpviewer_keywords: IsUpdateAllowed method
ms.assetid: d6daf3b3-a8e0-4275-a67d-897dea01e297
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: feaa5b397989667da62bbf979603391c08eada2c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetupdateimplisupdateallowed"></a>IRowsetUpdateImpl::IsUpdateAllowed
Güvenlik güncelleştirmeleri ve benzeri önce bütünlüğünü denetlemek için bu yöntemi geçersiz kılın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT IsUpdateAllowed(  
   DBPENDINGSTATUS /* [in] *//* status */,  
   HROW /* [in] *//* hRowUpdate */,  
   DBROWSTATUS* /* [out] *//* pRowStatus */  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *durumu*  
 [in] Bekleyen satırları işlemler durumu.  
  
 *hRowUpdate*  
 [in] Güncelleştirmek için kullanıcının istediği satırlar için işler.  
  
 *pRowStatus*  
 [out] Kullanıcı için bir durum döndürdü.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir güncelleştirme izin verilmesi gerektiğini belirlerseniz döndürür `S_OK`; Aksi takdirde döndürür **E_FAIL**. Bir güncelleştirme izin verirseniz, aynı zamanda ayarlamak ihtiyacınız **DBROWSTATUS** içinde [IRowsetUpdateImpl::Update](../../data/oledb/irowsetupdateimpl-update.md) için uygun bir [satır durumu](https://msdn.microsoft.com/en-us/library/ms722752.aspx).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IRowsetUpdateImpl sınıfı](../../data/oledb/irowsetupdateimpl-class.md)