---
title: CDataConnection::operator CSession&amp; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSession&
- CDataConnection::operatorCSession&
- CDataConnection.operatorCSession&
- operatorCSession&
dev_langs:
- C++
helpviewer_keywords:
- operator CSession&
- CSession& operator
ms.assetid: fba1e498-e482-4dda-8e0f-2542163bf627
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7d46aeb352016c41dddaee972d438be8c28e22a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095427"
---
# <a name="cdataconnectionoperator-csessionamp"></a>CDataConnection::operator CSession&amp;
Kapsanan bir başvuru döndürür `CSession` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
operator const CSession&();  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işleç kapsanan bir başvuru döndürür `CSession` geçmesine izin vererek nesne, bir `CDataConnection` nesne burada bir `CSession` başvuru beklenmektedir.  
  
## <a name="example"></a>Örnek  
 Bir işlev varsa (gibi `func` aşağıda) alan bir `CSession` kullanabileceğiniz başvuru, **CSession &** geçirmek için bir `CDataConnection` yerine nesne.  
  
 [!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDataConnection sınıfı](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession*](../../data/oledb/cdataconnection-operator-csession-star.md)