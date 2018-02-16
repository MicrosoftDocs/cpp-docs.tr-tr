---
title: CEnumerator::Find | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CEnumerator::Find
- ATL::CEnumerator::Find
- ATL.CEnumerator.Find
- CEnumerator.Find
dev_langs:
- C++
helpviewer_keywords:
- Find method
ms.assetid: 69a153af-d6c3-40fd-9018-27c7d2f344c6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 863832f41c866764883336c7de76fa343eb1cbac
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cenumeratorfind"></a>CEnumerator::Find
Kullanılabilir sağlayıcılar arasında belirli bir ad arar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      bool Find(TCHAR* szSearchName) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *szSearchName*  
 [in] Aranacak adı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 **doğru** adı bulunursa. Aksi takdirde, **false**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu ad eşlendiği **SOURCES_NAME** üyesi [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) arabirimi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CEnumerator Sınıfı](../../data/oledb/cenumerator-class.md)