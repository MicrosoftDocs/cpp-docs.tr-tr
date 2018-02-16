---
title: "CDynamicParameterAccessor sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicParameterAccessor
- ATL::CDynamicParameterAccessor
- CDynamicParameterAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicParameterAccessor class
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6c0bf234bd0f8a3de96c545e2bbdfe492822d627
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicparameteraccessor-class"></a>CDynamicParameterAccessor Sınıfı
Benzer şekilde [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) çağırarak ayarlanacak parametre bilgilerini alır, ancak [ICommandWithParameters](https://msdn.microsoft.com/en-us/library/ms712937.aspx) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CDynamicParameterAccessor : public CDynamicAccessor  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-cdynamicparameteraccessor.md)|Oluşturucu.|  
|[GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md)|Parametre veri arabelleğinden alır.|  
|[GetParamCount](../../data/oledb/cdynamicparameteraccessor-getparamcount.md)|Erişimci parametrelerinde sayısını alır.|  
|[GetParamIO](../../data/oledb/cdynamicparameteraccessor-getparamio.md)|Belirtilen parametre bir giriş veya çıkış parametresi olup olmadığını belirler.|  
|[GetParamLength](../../data/oledb/cdynamicparameteraccessor-getparamlength.md)|Arabellekte depolanan belirtilen parametresinin uzunluğu alır.|  
|[GetParamName](../../data/oledb/cdynamicparameteraccessor-getparamname.md)|Belirtilen parametre adını alır.|  
|[GetParamStatus](../../data/oledb/cdynamicparameteraccessor-getparamstatus.md)|Arabellekte depolanan belirtilen parametre durumunu alır.|  
|[GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md)|Arabellekte depolanan belirtilen parametresinin dize verilerini alır.|  
|[GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)|Belirtilen parametre veri türünü alır.|  
|[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)|Parametre veri kullanarak arabelleği ayarlar.|  
|[SetParamLength](../../data/oledb/cdynamicparameteraccessor-setparamlength.md)|Arabellekte depolanan belirtilen parametresinin uzunluğu ayarlar.|  
|[SetParamStatus](../../data/oledb/cdynamicparameteraccessor-setparamstatus.md)|Arabellekte depolanan belirtilen parametre durumunu ayarlar.|  
|[SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md)|Arabellekte depolanan belirtilen parametresinin dize verilerini ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sağlayıcı desteklemelidir `ICommandWithParameters` tüketici bu sınıfını kullanmak için.  
  
 Parametre bilgileri oluşturulur ve bu sınıf tarafından yönetilen bir arabellek depolanır. Parametre veri arabelleğinden kullanarak elde [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) ve [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md).  
  
 Örneğin, Bilgi Bankası makalesi Q058860 bakın Bu sınıf bir SQL Server saklı yordamı yürütmek ve çıkış parametre değerlerini almak için nasıl kullanılacağını gösteren "nasıl yapılır: CDynamicParameterAccessor kullanarak saklı yordamı yürütme." Bilgi Bankası makaleleri, MSDN Kitaplığı Visual Studio belgelerinde bulunur veya adresindeki [http://support.microsoft.com/](http://support.microsoft.com).  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor sınıfı](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor sınıfı](../../data/oledb/cdynamicaccessor-class.md)   
 [CManualAccessor Sınıfı](../../data/oledb/cmanualaccessor-class.md)