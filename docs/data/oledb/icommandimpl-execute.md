---
title: Icommandımpl::Execute | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandImpl::Execute
- ICommandImpl.Execute
dev_langs:
- C++
helpviewer_keywords:
- Execute method
ms.assetid: 033e0d4e-256b-4eed-9215-70e0bebb768c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 369c60c1f6407856fb204654794c214fd9ee8b57
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100775"
---
# <a name="icommandimplexecute"></a>ICommandImpl::Execute
Komut yürütür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Execute(IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="remarks"></a>Açıklamalar  
 İstenen giden arabirimi bu işlev oluşturur satır kümesi nesneden alınan bir arabirim olacaktır.  
  
 **Yürütme** çağrıları [CreateRowset](../../data/oledb/icommandimpl-createrowset.md). Varsayılan uygulama birden fazla satır kümesi oluşturun veya farklı satır kümeleri oluşturmak için kendi koşullar sağlamak için geçersiz kılar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Icommandımpl sınıfı](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)