---
title: CDataConnection::operator CDataSource&amp; | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataSource&
- CDataConnection.operatorCDataSource&
- operatorCDataSource&
- CDataConnection::operatorCDataSource&
dev_langs: C++
helpviewer_keywords:
- CDataSource& operator
- operator & (CDataSource)
ms.assetid: 852faeee-f1b1-4465-9828-b261d1edf022
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fc2309b7b97a97d19ff9a68895fef3ed3bda8b7c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdataconnectionoperator-cdatasourceamp"></a>CDataConnection::operator CDataSource&amp;
Kapsanan bir başvuru döndürür `CDataSource` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
operator const CDataSource&() throw( );  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işleç kapsanan bir başvuru döndürür `CDataSource` geçmesine izin vererek nesne, bir `CDataConnection` nesne burada bir `CDataSource` başvuru beklenmektedir.  
  
## <a name="example"></a>Örnek  
 Bir işlev varsa (gibi `func` aşağıda) alan bir `CDataSource` kullanabileceğiniz başvuru, **CDataSource &** geçirmek için bir `CDataConnection` yerine nesne.  
  
 [!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDataConnection sınıfı](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource *](../../data/oledb/cdataconnection-operator-cdatasource-star.md)