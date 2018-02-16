---
title: CCommand::Create | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CCommand.Create
- CCommand::Create
dev_langs:
- C++
helpviewer_keywords:
- Create method [C++]
ms.assetid: e4bede7a-68bd-491a-97f4-89b03d45cd24
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e84809d24479d85b01441c67b467102936b7f1aa
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="ccommandcreate"></a>CCommand::Create
Çağrıları [CCommand::CreateCommand](../../data/oledb/ccommand-createcommand.md) belirtilen oturum için bir komut oluşturmak için daha sonra çağırır [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) komut metnini belirtmek için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT CCommandBase::Create(const CSession& session,   
   LPCWSTR wszCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();  


HRESULT CCommandBase::Create(const CSession& session,   
   LPCSTR szCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT) throw ();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `session`  
 [in] Bir oturum üzerinde komutu oluşturulacak.  
  
 `wszCommand`  
 [in] Komut dizesini Unicode metni için bir işaretçi.  
  
 `szCommand`  
 [in] Komut dizesini ANSI metni için bir işaretçi.  
  
 `guidCommand`  
 [in] Komut metni ayrıştırma için kullanılan sağlayıcının için genel kurallar ve sözdizimi belirtir bir GUID. Portekizce açıklaması için bkz: [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk biçimini **oluşturma** Unicode komut dizesini alır. İkinci biçiminde **oluşturma** (varolan ANSI uygulamalarla geriye dönük uyumluluk için sağlanır) ANSI komut dizisi alır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCommand Sınıfı](../../data/oledb/ccommand-class.md)