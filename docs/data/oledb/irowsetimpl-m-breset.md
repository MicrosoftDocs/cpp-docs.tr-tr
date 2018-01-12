---
title: "Irowsetımpl::m_breset | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetImpl.m_bReset
- IRowsetImpl.m_bReset
- m_bReset
- IRowsetImpl::m_bReset
- ATL::IRowsetImpl::m_bReset
dev_langs: C++
helpviewer_keywords: m_bReset
ms.assetid: d423f9f3-4d48-4d0c-b152-684c81a0b34e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4cd9840b37157aed050bb71d48a275efd2849035
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplmbreset"></a>IRowsetImpl::m_bReset
İmleç konumu satır kümesinde tanımlı olup olmadığını belirlemek için kullanılan bit bayrağı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
unsigned m_bReset:1;  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Tüketici çağırırsa [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) negatif ile `lOffset` veya *cRows* ve `m_bReset` doğrudur `GetNextRows` satır sonuna taşır. Varsa `m_bReset` yanlış tüketici OLE DB belirtimine uygunluğu bir hata kodu alır. `m_bReset` Bayrağı ayarlanmış **true** satır ilk oluşturulduğunda ve tüketici çağırdığında [Irowsetımpl::restartposition](../../data/oledb/irowsetimpl-restartposition.md). Ayarlayın **false** çağırdığınızda `GetNextRows`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IRowsetImpl Sınıfı](../../data/oledb/irowsetimpl-class.md)