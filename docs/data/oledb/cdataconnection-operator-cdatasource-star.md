---
title: CDataConnection::operator CDataSource * | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataSource*
- CDataConnection::operatorCDataSource*
- CDataConnection.operatorCDataSource*
- operatorCDataSource*
dev_langs: C++
helpviewer_keywords:
- CDataSource* operator
- operator * (CDataSource)
ms.assetid: 9118e324-e68d-45c5-a791-03f041d420ed
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3010f0774224cd02a35aeaa185bca32f370d5ba0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdataconnectionoperator-cdatasource"></a>CDataConnection::operator CDataSource*
İşaretçi içerdiği için döndüren `CDataSource` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
operator const CDataSource*() throw( );  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İşaretçi içerdiği için bu işleci döndüren `CDataSource` geçmesine izin vererek nesne, bir `CDataConnection` nesne burada bir `CDataSource` işaretçi beklenmektedir.  
  
 Bkz: [işleci CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md) kullanım örneğin.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDataConnection sınıfı](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)