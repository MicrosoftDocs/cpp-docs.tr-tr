---
title: "CString semantiği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 394e459a46003e3f1baccff7dd4c76f40b73e354
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cstring-semantics"></a>CString semantiği
Olsa bile [CString](../atl-mfc-shared/reference/cstringt-class.md) nesneleri büyüyebilir dinamik nesneler, yerleşik temel eleman türleri ve basit sınıflar gibi davranır. Her `CString` nesnesi benzersiz bir değeri temsil eder. `CString`nesneleri, ardından gerçek dizeleri olarak yerine dizeleri işaretçiler olarak düşünülmelidir.  
  
 Atayabilirsiniz **CString** başka bir nesne. Ancak, değiştirdiğinizde iki birini `CString` nesneleri, diğer `CString` nesne değişiklik, aşağıdaki örnekte gösterildiği gibi:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]  
  
 Not örnekte, iki `CString` aynı karakter dizesi gösterdiğinden nesneleri "eşit" değerlendirilir. `CString` Sınıfı eşitlik işleci aşırı yüklemeler (`==`) iki Karşılaştırılacak `CString` nesneleri kimliklerini (adresi) yerine kendi değeri (içeriği) bağlı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)

