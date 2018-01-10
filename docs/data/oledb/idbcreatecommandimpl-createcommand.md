---
title: "Idbcreatecommandımpl::CreateCommand | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBCreateCommandImpl.CreateCommand
- CreateCommand
- IDBCreateCommandImpl::CreateCommand
dev_langs: C++
helpviewer_keywords: CreateCommand method
ms.assetid: 50ffbf8b-2c07-4bcb-96c5-ffce4519c7f7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ff1f7e9815ae5cea9a96c95f7faad30340bf548d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="idbcreatecommandimplcreatecommand"></a>IDBCreateCommandImpl::CreateCommand
Yeni bir komut oluşturur ve istenen arabirimi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      STDMETHOD(CreateCommand)(   
   IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppvCommand    
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IDBCreateCommand::CreateCommand](https://msdn.microsoft.com/en-us/library/ms709772.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 Bazı parametreler karşılık *OLE DB Programcının Başvurusu* açıklanan farklı adlar parametrelerinin **IDBCreateCommand::CreateCommand**:  
  
|OLE DB Şablon parametreleri|*OLE DB Programcının Başvurusu* parametreleri|  
|--------------------------------|------------------------------------------------|  
|*ppvCommand*|*ppCommand*|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDBCreateCommandImpl Sınıfı](../../data/oledb/idbcreatecommandimpl-class.md)