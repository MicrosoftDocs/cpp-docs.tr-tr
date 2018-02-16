---
title: "Icommandımpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl
dev_langs:
- C++
helpviewer_keywords:
- ICommandImpl class
ms.assetid: ef285fef-0d66-45e6-a762-b03357098e3b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 80cc82023131a23ebfea33c5264cf83fdafb1b36
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="icommandimpl-class"></a>ICommandImpl Sınıfı
Uygulamasını sağlar [ICommand](https://msdn.microsoft.com/en-us/library/ms709737.aspx) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class CommandBase = ICommand>   
class ATL_NO_VTABLE ICommandImpl : public CommandBase  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `ICommandImpl`.  
  
 `CommandBase`  
 Bir komut arabirimi. Varsayılan, `ICommand` değeridir.  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)|Geçerli komut yürütme iptal eder.|  
|[İptal](../../data/oledb/icommandimpl-cancel.md)|Geçerli komut yürütme iptal eder.|  
|[CreateRowset](../../data/oledb/icommandimpl-createrowset.md)|Bir satır kümesi nesnesi oluşturur.|  
|[Execute](../../data/oledb/icommandimpl-execute.md)|Komut yürütür.|  
|[GetDBSession](../../data/oledb/icommandimpl-getdbsession.md)|Arabirim işaretçisi komutu oluşturulan oturumuna döndürür.|  
|[ICommandImpl](../../data/oledb/icommandimpl-icommandimpl.md)|Oluşturucu.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_bCancel](../../data/oledb/icommandimpl-m-bcancel.md)|Komut iptal edilmesi olup olmadığını gösterir.|  
|[m_bCancelWhenExecuting](../../data/oledb/icommandimpl-m-bcancelwhenexecuting.md)|Komut yürütülürken iptal edilmesi olup olmadığını gösterir.|  
|[m_bIsExecuting](../../data/oledb/icommandimpl-m-bisexecuting.md)|Komut şu anda yürütülmekte olup olmadığını gösterir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Komut nesnesi üzerinde zorunlu bir arabirim.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)