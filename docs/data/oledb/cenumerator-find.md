---
title: CEnumerator::Find | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2466127dab53fa6646a4f149400e4318aed59970
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094488"
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