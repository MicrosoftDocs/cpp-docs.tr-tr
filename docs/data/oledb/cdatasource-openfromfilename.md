---
title: CDataSource::OpenFromFileName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataSource::OpenFromFileName
- ATL::CDataSource::OpenFromFileName
- OpenFromFileName
- CDataSource.OpenFromFileName
- ATL.CDataSource.OpenFromFileName
dev_langs: C++
helpviewer_keywords: OpenFromFileName method
ms.assetid: c4226de6-59da-4368-9c15-c5afab86f68b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c807ead64a068a9797b49606d41d16664b6331e4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdatasourceopenfromfilename"></a>CDataSource::OpenFromFileName
Kullanıcı tarafından sağlanan dosya adıyla belirtilen dosyadan bir veri kaynağı açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT OpenFromFileName(   
   LPCOLESTR szFileName    
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `szFileName`  
 [in] Bir dosya, genellikle bir veri kaynağı bağlantısı adı (. UDL) dosyası.  
  
 Veri bağlantısı dosyalarını (UDL dosyaları) hakkında daha fazla bilgi için bkz: [veri bağlantısı API genel bakış](https://msdn.microsoft.com/en-us/library/ms718102.aspx) Windows SDK'sındaki.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem oledb32.dll içinde hizmet Bileşenleri'ni kullanarak bir veri kaynağı nesnesi açar; Bu DLL kaynak havuzu, otomatik işlem kaydı vb. gibi hizmet bileşenleri özellikleri uygulamasını içerir. Daha fazla bilgi için bkz: "OLE DB hizmetleri" OLE DB Programcı Başvurusu, [http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDataSource sınıfı](../../data/oledb/cdatasource-class.md)