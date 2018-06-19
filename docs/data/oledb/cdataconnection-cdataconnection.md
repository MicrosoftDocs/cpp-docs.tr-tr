---
title: CDataConnection::CDataConnection | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataConnection.CDataConnection
- ATL.CDataConnection.CDataConnection
- CDataConnection::CDataConnection
- ATL::CDataConnection::CDataConnection
dev_langs:
- C++
helpviewer_keywords:
- CDataConnection class, constructor
ms.assetid: ac25c9a0-44d3-4083-b13f-76c07772e12d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 267341f88886f3ff94a6b828034e8acbaa2dc0c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093330"
---
# <a name="cdataconnectioncdataconnection"></a>CDataConnection::CDataConnection
Oluşturur ve başlatır bir `CDataConnection` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      CDataConnection();   

CDataConnection(const CDataConnection &ds);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ds`  
 [in] Varolan bir veri bağlantısı referansı.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk geçersiz kılma yeni bir oluşturur `CDataConnection` varsayılan ayarlarla nesnesi.  
  
 İkinci geçersiz kılma yeni bir oluşturur `CDataConnection` ayarlarla belirttiğiniz veri bağlantı nesnesi eşdeğer nesne.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDataConnection Sınıfı](../../data/oledb/cdataconnection-class.md)