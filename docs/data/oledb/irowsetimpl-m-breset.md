---
title: Irowsetımpl::m_breset | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetImpl.m_bReset
- IRowsetImpl.m_bReset
- m_bReset
- IRowsetImpl::m_bReset
- ATL::IRowsetImpl::m_bReset
dev_langs:
- C++
helpviewer_keywords:
- m_bReset
ms.assetid: d423f9f3-4d48-4d0c-b152-684c81a0b34e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9aec38e3cf7e9a58c4fe99d06f35ae55cfdf81c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetimplmbreset"></a>IRowsetImpl::m_bReset
İmleç konumu satır kümesinde tanımlı olup olmadığını belirlemek için kullanılan bit bayrağı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
unsigned m_bReset:1;  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Tüketici çağırırsa [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) negatif ile `lOffset` veya *cRows* ve `m_bReset` doğrudur `GetNextRows` satır sonuna taşır. Varsa `m_bReset` yanlış tüketici OLE DB belirtimine uygunluğu bir hata kodu alır. `m_bReset` Bayrağı ayarlanmış **true** satır ilk oluşturulduğunda ve tüketici çağırdığında [Irowsetımpl::restartposition](../../data/oledb/irowsetimpl-restartposition.md). Ayarlayın **false** çağırdığınızda `GetNextRows`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IRowsetImpl Sınıfı](../../data/oledb/irowsetimpl-class.md)