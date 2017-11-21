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
ms.openlocfilehash: 8c4ad47ce5163291c45827d94c9e6f8d5904c847
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [CDataConnection::operator CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md)