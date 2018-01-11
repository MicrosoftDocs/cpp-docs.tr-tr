---
title: CRowsetImpl::m_rgRowData | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowsetImpl.m_rgRowData
- CRowsetImpl::m_rgRowData
dev_langs: C++
helpviewer_keywords: m_rgRowData
ms.assetid: e4e75ca7-12e8-4a0b-94e8-e395c21385b2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cde93940ae690457df89923a214fd219b8b87606
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetimplmrgrowdata"></a>CRowsetImpl::m_rgRowData
Varsayılan olarak, bir `CAtlArray` kullanıcı kayıt şablonu bağımsız değişkeni üzerinde templatizes `CRowsetImpl`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
ArrayType CRowsetBaseImpl::m_rgRowData;  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **ArrayType** şablon parametresi `CRowsetImpl`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRowsetImpl sınıfı](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md)   
 [CRowsetImpl::m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)