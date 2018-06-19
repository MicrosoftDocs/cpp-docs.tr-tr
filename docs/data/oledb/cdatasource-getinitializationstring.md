---
title: CDataSource::getınitializationstring | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDataSource::GetInitializationString
- CDataSource.GetInitializationString
- GetInitializationString
- CDataSource::GetInitializationString
- ATL.CDataSource.GetInitializationString
dev_langs:
- C++
helpviewer_keywords:
- GetInitializationString method
ms.assetid: 97134723-6e99-4004-a56d-ec57543dbf3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c2cc4652dcb7450217fd99969089bdbeb41c3a3f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094058"
---
# <a name="cdatasourcegetinitializationstring"></a>CDataSource::GetInitializationString
Şu anda açık olan bir veri kaynağının başlatma dizesini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT GetInitializationString(BSTR* pInitializationString,   
   bool bIncludePassword = false) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pInitializationString*  
 [out] Başlatma dizesinin bir işaretçi.  
  
 *bIncludePassword*  
 [in] **true** ; parola dize içeriyorsa, aksi takdirde **false**.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Sonuç başlatma dizesi, daha sonra bu veri kaynağı bağlantısı yeniden açmak için kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDataSource Sınıfı](../../data/oledb/cdatasource-class.md)