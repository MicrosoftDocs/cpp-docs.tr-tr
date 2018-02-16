---
title: CDataConnection::operator CDataSource&amp; | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataSource&
- CDataConnection.operatorCDataSource&
- operatorCDataSource&
- CDataConnection::operatorCDataSource&
dev_langs:
- C++
helpviewer_keywords:
- CDataSource& operator
- operator & (CDataSource)
ms.assetid: 852faeee-f1b1-4465-9828-b261d1edf022
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c52610d947d60fa7ea1be9b764fd09ae0e777a3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cdataconnectionoperator-cdatasourceamp"></a>CDataConnection::operator CDataSource&amp;
Kapsanan bir başvuru döndürür `CDataSource` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
operator const CDataSource&() throw();  
  
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
 [CDataConnection::operator CDataSource*](../../data/oledb/cdataconnection-operator-cdatasource-star.md)