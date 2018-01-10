---
title: "CDataSource sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDataSource
- ATL::CDataSource
- CDataSource
dev_langs: C++
helpviewer_keywords: CDataSource class
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a8f5a7b4c09400ad31be0b8b403899c5e8401afa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdatasource-class"></a>CDataSource Sınıfı
Bir veri kaynağına bağlantı sağlayıcısı üzerinden temsil eden bir OLE DB veri kaynağı nesnesi karşılık gelir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDataSource  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Kapat](../../data/oledb/cdatasource-close.md)|Bağlantıyı kapatır.|  
|[Getınitializationstring](../../data/oledb/cdatasource-getinitializationstring.md)|Şu anda açık olan veri kaynağı başlatma dizisini alır.|  
|[GetProperties](../../data/oledb/cdatasource-getproperties.md)|Bağlı veri kaynağı için ayarlanmış özelliklerinin değerlerini alır.|  
|[GetProperty](../../data/oledb/cdatasource-getproperty.md)|Bağlı veri kaynağı için ayarlanmış tek bir özellik değerini alır.|  
|[Açık](../../data/oledb/cdatasource-open.md)|Bir sağlayıcı (veri kaynağı) kullanarak bir bağlantı oluşturur bir **CLSID**, **ProgID**, veya bir `CEnumerator` çağıran tarafından sağlanan ad.|  
|[OpenFromFileName](../../data/oledb/cdatasource-openfromfilename.md)|Kullanıcı tarafından sağlanan dosya adıyla belirtilen dosyadan bir veri kaynağı açar.|  
|[OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md)|Başlatma dizesi tarafından belirtilen veri kaynağı açar.|  
|[OpenWithPromptFileName](../../data/oledb/cdatasource-openwithpromptfilename.md)|Kullanıcının karşılık gelen veri kaynağı açmak için daha önce oluşturulan veri bağlantısı dosyası seçmesine olanak sağlar.|  
|[OpenWithServiceComponents](../../data/oledb/cdatasource-openwithservicecomponents.md)|Veri Bağlantısı iletişim kutusunu kullanarak bir veri kaynağı nesnesi açar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir veya daha fazla veritabanı oturumları için tek bir bağlantı oluşturulamıyor. Bu oturumlar tarafından temsil edilen `CSession`. Çağırmalısınız [CDataSource::Open](../../data/oledb/cdatasource-open.md) bir oturumla oluşturmadan önce bağlantıyı açmak için `CSession::Open`.  
  
 Bir örnek için nasıl kullanılacağını `CDataSource`, bkz: [CatDB](../../visual-cpp-samples.md) örnek.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)