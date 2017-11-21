---
title: "Cdberrorınfo sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBErrorInfo
- ATL::CDBErrorInfo
- ATL.CDBErrorInfo
dev_langs: C++
helpviewer_keywords: CDBErrorInfo class
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3d1ecd29e32686e8cc91ec9716625beeee2cef25
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdberrorinfo-class"></a>CDBErrorInfo Sınıfı
OLE DB kullanarak OLE DB hata işleme için destek sağlar [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDBErrorInfo  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Getallerrorınfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md)|Bir hata kaydında bulunan tüm hata bilgilerini döndürür.|  
|[Getbasicerrorınfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|Çağrıları [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) belirtilen hata ile ilgili temel bilgileri döndürmek için.|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|Çağrıları [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) bir işaretçi bir arabirim bir özel hata nesnesi üzerinde dönün.|  
|[Geterrorınfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|Çağrıları [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) döndürmek için bir **IErrorInfo** belirtilen kayıt arabirimi işaretçisi.|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|Çağrıları [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx) hata parametreleri dönün.|  
|[GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md)|Hata kayıtları için belirtilen nesneyi alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim, kullanıcıya bir veya daha fazla hata kaydı döndürür. Çağrı [Cdberrorınfo::geterrorrecords](../../data/oledb/cdberrorinfo-geterrorrecords.md) hata kayıt sayısı ulaşmak için öncelikle,. Ardından gibi erişim birini işlev çağrısı [Cdberrorınfo::getallerrorınfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md), her kayıt için hata bilgileri alınamadı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DBVIEWER](../../visual-cpp-samples.md)   
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)