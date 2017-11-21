---
title: "CEnumerator sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CEnumerator
dev_langs: C++
helpviewer_keywords: CEnumerator class
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 856356117161a0c9e3588732faf01c3a663b6a9b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cenumerator-class"></a>CEnumerator Sınıfı
Kullanıma sunan bir OLE DB Numaralandırıcı nesne kullanan [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) arabirimi tüm veri kaynakları ve numaralandırmalar açıklayan bir satır kümesi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CEnumerator :   
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Bul](../../data/oledb/cenumerator-find.md)|Kullanılabilir sağlayıcılar (veri kaynakları) belirtilen ada sahip bir arayan arar.|  
|[GetMoniker](../../data/oledb/cenumerator-getmoniker.md)|Alır `IMoniker` geçerli kayıt için arabirim.|  
|[Açık](../../data/oledb/cenumerator-open.md)|Numaralayıcı açar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Alabilirsiniz **ISourcesRowset** dolaylı olarak bu sınıfın verileri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:**atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DBVIEWER](../../visual-cpp-samples.md)   
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)