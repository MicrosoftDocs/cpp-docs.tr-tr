---
title: CString semantiği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 256c71cace15a3906ac048819ab2ffdef2071ff4
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761279"
---
# <a name="cstring-semantics"></a>CString semantiği

Olsa da [CString](../atl-mfc-shared/reference/cstringt-class.md) nesneleri büyüyebilir dinamik nesneler, yerleşik temel eleman türleri ve basit sınıflar gibi davranır. Her `CString` nesnesi benzersiz bir değeri temsil eder. `CString` nesneleri, ardından gerçek dizeleri yerine dizelerine olarak düşünülmelidir.

Atayabilirsiniz `CString` başka bir nesne. Ancak, değiştirdiğinizde bir iki `CString` nesnelerini, diğer `CString` nesne değiştirilmez, aşağıdaki örnekte gösterildiği gibi:

[!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]

Not örnekte, iki `CString` aynı karakter dizesini temsil ettikleri çünkü nesneleri "equal" değerlendirilir. `CString` Sınıfı eşitlik işlecini aşırı yüklemeler (`==`) karşılaştırmak için `CString` kimliklerini (adres) yerine nesneleri temel değerlerine (içeriği).

## <a name="see-also"></a>Ayrıca Bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)

