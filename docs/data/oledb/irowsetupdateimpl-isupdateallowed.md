---
title: IRowsetUpdateImpl::ısupdateallowed | Microsoft Docs
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
dev_langs:
- C++
helpviewer_keywords:
- IsUpdateAllowed method
ms.assetid: d6daf3b3-a8e0-4275-a67d-897dea01e297
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 363626cedddea3da57e829a43c21c63b5c2b05cd
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122010"
---
# <a name="irowsetupdateimplisupdateallowed"></a>IRowsetUpdateImpl::IsUpdateAllowed
Güvenlik güncelleştirmeleri ve benzeri önce bütünlüğünü denetlemek için bu yöntemi geçersiz kılın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] */ /* status */,  
   HROW /* [in] */ /* hRowUpdate */,  
   DBROWSTATUS* /* [out] */ /* pRowStatus */);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Durumu*  
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
 [IRowsetUpdateImpl Sınıfı](../../data/oledb/irowsetupdateimpl-class.md)