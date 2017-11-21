---
title: "CDynamicStringAccessor sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDynamicStringAccessor
dev_langs: C++
helpviewer_keywords: CDynamicStringAccessor class
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cbd9526904eca0a4b0cc59c1aac22970b83d3090
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicstringaccessor-class"></a>CDynamicStringAccessor Sınıfı
Veritabanı şeması (veritabanının temel yapısı) olanağıyla varsa, bir veri kaynağına erişim sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      template< typename BaseType, DBTYPEENUM OleDbType >  
class CDynamicStringAccessorT : public CDynamicAccessor  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[GetString](../../data/oledb/cdynamicstringaccessor-getstring.md)|Belirtilen sütun verileri dize olarak alır.|  
|[SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)|Belirtilen sütun veri dize olarak ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sırada [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) sağlayıcı tarafından bildirilen yerel biçiminde veri istekleri `CDynamicStringAccessor` sağlayıcı dize veri olarak veri deposundan erişilen tüm veriler getirilemedi ister. Bu, özellikle görüntüleme ya da veri deposunun içeriği yazdırma gibi veri deposundaki değerlerin hesaplamasını gerektirmeyen basit görevler için kullanışlıdır.  
  
 Yerel veri deposundaki sütun veri türü önemli değildir; Sağlayıcının veri dönüştürme destekleyebilir sürece, dize biçimindeki verileri kullanacaksınız. Sağlayıcı yerel veri türünden (hangi ortak değildir) bir dizeye dönüştürme desteklemiyorsa, istekte bulunan çağrı başarılı değeri döndürür **DB_S_ERRORSOCCURED**, ve karşılık gelen sütunun durumu bir dönüştürme sorun olduğunu gösteriyor **DBSTATUS_E_CANTCONVERTVALUE**.  
  
 Kullanım `CDynamicStringAccessor` sütun bilgileri almak için yöntemleri. Erişimci çalışma zamanında dinamik olarak oluşturmak için bu sütun bilgileri kullanın.  
  
 Sütun bilgileri oluşturulur ve bu sınıf tarafından yönetilen bir arabellek depolanır. Arabellek kullanımından verileri elde [GetString](../../data/oledb/cdynamicstringaccessor-getstring.md), veya arabellek kullanmaya mağaza [SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).  
  
 Bir tartışma ve dinamik erişimciyi sınıfları kullanma örnekleri için bkz: [Dinamik Erişimcileri Kullanma](../../data/oledb/using-dynamic-accessors.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor sınıfı](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor sınıfı](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor sınıfı](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessorA sınıfı](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW sınıfı](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CXMLAccessor sınıfı](../../data/oledb/cxmlaccessor-class.md)