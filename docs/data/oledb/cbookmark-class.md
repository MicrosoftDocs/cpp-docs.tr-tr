---
title: "CBookmark sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CBookmark
- ATL::CBookmark<nSize>
- CBookmark
- ATL.CBookmark<nSize>
- ATL::CBookmark
dev_langs: C++
helpviewer_keywords: CBookmark class
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dba5f98912fc69bac5554a4c6231f77e17e99d98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cbookmark-class"></a>CBookmark Sınıfı
Bir yer işareti değeri kendi arabellekte tutar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template < DBLENGTH nSize = 0 >  
class CBookmark : public CBookmarkBase  
template < >  
class CBookmark< 0 > : public CBookmarkBase  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nSize`  
 Yer işareti arabelleğinin bayt cinsinden boyutu. Zaman `nSize` sıfır işareti arabellek çalışma zamanında dinamik olarak oluşturulur.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CBookmark](../../data/oledb/cbookmark-class.md)|Oluşturucusu|  
|[GetBuffer](../../data/oledb/cbookmark-getbuffer.md)|İşaretçi arabelleğe alır.|  
|[GetSize](../../data/oledb/cbookmark-getsize.md)|Bayt cinsinden arabellek boyutunu alır.|  
|[SetBookmark](../../data/oledb/cbookmark-setbookmark.md)|Yer işareti değeri ayarlar.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](../../data/oledb/cbookmark-operator-equal.md)|Atar `CBookmark` başka bir sınıf.|  
  
## <a name="remarks"></a>Açıklamalar  
 **CBookmark\<0 >** şablonu uzmanlığı olan `CBookmark`; arabelleğini çalışma zamanında dinamik olarak oluşturulur.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)