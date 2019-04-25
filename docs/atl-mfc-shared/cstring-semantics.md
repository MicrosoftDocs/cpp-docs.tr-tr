---
title: CString semantiği
ms.date: 11/04/2016
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
ms.openlocfilehash: b5398f8a0f17ffcc93c7f5f6158ecc56606e9279
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62236267"
---
# <a name="cstring-semantics"></a>CString semantiği

Olsa da [CString](../atl-mfc-shared/reference/cstringt-class.md) nesneleri büyüyebilir dinamik nesneler, yerleşik temel eleman türleri ve basit sınıflar gibi davranır. Her `CString` nesnesi benzersiz bir değeri temsil eder. `CString` nesneleri, ardından gerçek dizeleri yerine dizelerine olarak düşünülmelidir.

Atayabilirsiniz `CString` başka bir nesne. Ancak, değiştirdiğinizde bir iki `CString` nesnelerini, diğer `CString` nesne değiştirilmez, aşağıdaki örnekte gösterildiği gibi:

[!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]

Not örnekte, iki `CString` aynı karakter dizesini temsil ettikleri çünkü nesneleri "equal" değerlendirilir. `CString` Sınıfı eşitlik işlecini aşırı yüklemeler (`==`) karşılaştırmak için `CString` kimliklerini (adres) yerine nesneleri temel değerlerine (içeriği).

## <a name="see-also"></a>Ayrıca bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
