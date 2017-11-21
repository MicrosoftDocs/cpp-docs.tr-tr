---
title: "CString semantiği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2d2eadf67de4a9eb92ee1edb734abc54d7ee2dbd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cstring-semantics"></a>CString semantiği
Olsa bile [CString](../atl-mfc-shared/reference/cstringt-class.md) nesneleri büyüyebilir dinamik nesneler, yerleşik temel eleman türleri ve basit sınıflar gibi davranır. Her `CString` nesnesi benzersiz bir değeri temsil eder. `CString`nesneleri, ardından gerçek dizeleri olarak yerine dizeleri işaretçiler olarak düşünülmelidir.  
  
 Atayabilirsiniz **CString** başka bir nesne. Ancak, değiştirdiğinizde iki birini `CString` nesneleri, diğer `CString` nesne değişiklik, aşağıdaki örnekte gösterildiği gibi:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]  
  
 Not örnekte, iki `CString` aynı karakter dizesi gösterdiğinden nesneleri "eşit" değerlendirilir. `CString` Sınıfı eşitlik işleci aşırı yüklemeler (`==`) iki Karşılaştırılacak `CString` nesneleri kimliklerini (adresi) yerine kendi değeri (içeriği) bağlı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)

