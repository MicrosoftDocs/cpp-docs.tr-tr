---
title: "CDynamicParameterAccessor sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 02/14/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
ms.openlocfilehash: 18f53ca6d95d215ad41c6b2501245be0e470bbb1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicparameteraccessor-class"></a>CDynamicParameterAccessor Sınıfı

Benzer şekilde [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) çağırarak ayarlanacak parametre bilgilerini alır, ancak [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) arabirimi.

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

Bu sınıf bir SQL Server saklı yordamı yürütmek ve çıkış parametresi değerlerini almak için nasıl kullanılacağını gösteren bir örnek için bkz: [DynamicConsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) örnek kodda [Microsoft VCSamples](https://github.com/Microsoft/VCSamples) GitHub deposunu.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi**: atldbcli.h

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)  
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)  
[CAccessor Sınıfı](../../data/oledb/caccessor-class.md)  
[CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)  
[CManualAccessor Sınıfı](../../data/oledb/cmanualaccessor-class.md)  
