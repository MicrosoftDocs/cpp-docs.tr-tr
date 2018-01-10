---
title: CDataConnection::operator CSession * | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection.operatorCSession*
- CDataConnection::operatorCSession*
- operatorCSession*
- CSession*
dev_langs: C++
helpviewer_keywords:
- operator CSession*
- CSession* operator
ms.assetid: 0b0feede-5c3e-4835-be5b-03651597014d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 53efb82e9f78b4ea5a76b4f200012ed98fb513d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdataconnectionoperator-csession"></a>CDataConnection::operator CSession*
İşaretçi içerdiği için döndüren `CSession` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
operator const CSession*() throw( );  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İşaretçi içerdiği için bu işleci döndüren `CSession` geçmesine izin vererek nesne, bir `CDataConnection` nesne burada bir `CSession` işaretçi beklenmektedir.  
  
## <a name="example"></a>Örnek  
 Bkz: [işleç CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md) kullanım örneğin.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDataConnection sınıfı](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md)