---
title: CCommand::Prepare | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CCommand.Prepare
- CCommand::Prepare
- Prepare
dev_langs: C++
helpviewer_keywords: Prepare method
ms.assetid: f0e473fc-2f7a-4d29-96c2-1328dc21e702
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e9f809e9d416599721a0d683362fcf27a99ad2ec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccommandprepare"></a>CCommand::Prepare
Doğrular ve geçerli komutu en iyi duruma getirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT CCommandBase::Prepare(  
   ULONG cExpectedRuns = 0   
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 *cExpectedRuns*  
 [in] Komutu yürütmek için beklediğiniz sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem OLE DB yöntemi sarmalar [ICommandPrepare::Prepare](https://msdn.microsoft.com/en-us/library/ms718370.aspx).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CCommand sınıfı](../../data/oledb/ccommand-class.md)