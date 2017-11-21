---
title: "IRowsetNotifyImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetNotifyImpl
- ATL::IRowsetNotifyImpl
- IRowsetNotifyImpl
dev_langs: C++
helpviewer_keywords: IRowsetNotifyImpl class
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7473e63c7ca67dff200d5cf96f1774ca9a2d6817
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetnotifyimpl-class"></a>IRowsetNotifyImpl Sınıfı
Uygular ve kaydeder [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) (olarak da bilinen "havuz") tüketici böylece bildirimleri işleyebilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[OnFieldChange](../../data/oledb/irowsetnotifyimpl-onfieldchange.md)|Bir sütunun değeri herhangi bir değişiklik tüketici bildirir.|  
|[OnRowChange](../../data/oledb/irowsetnotifyimpl-onrowchange.md)|Bir satır ilk değişiklik veya tüm satırı etkiler herhangi bir değişiklik tüketici bildirir.|  
|[OnRowsetChange](../../data/oledb/irowsetnotifyimpl-onrowsetchange.md)|Tüm satır etkileyen herhangi bir değişiklik tüketici bildirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [bildirimleri alma](../../data/oledb/receiving-notifications.md) tüketici üzerinde bağlantı noktası arabirimi uygulama hakkında.  
  
 `IRowsetNotifyImpl`sahte bir uygulamasını sağlar `IRowsetNotify`, boş işlevleri için ile `IRowsetNotify` yöntemleri [OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx), [OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx), ve [OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx). Gerçekleştirdiğinizde bu sınıftan devralınan varsa bir `IRowsetNotify` arabirimi, yalnızca ihtiyacınız yöntemleri uygulayabilirsiniz. Ayrıca diğer yöntemleri için boş uygulamaları kendiniz vermeniz gerekir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)   
 [IRowsetNotifyCP sınıfı](../../data/oledb/irowsetnotifycp-class.md)