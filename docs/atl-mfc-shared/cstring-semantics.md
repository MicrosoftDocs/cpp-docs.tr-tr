---
title: CString semantiği
ms.date: 11/04/2016
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
ms.openlocfilehash: f563b24a9df61a91711433a4e4987f8f800545ff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657801"
---
# <a name="cstring-semantics"></a>CString semantiği

Olsa da [CString](../atl-mfc-shared/reference/cstringt-class.md) nesneleri büyüyebilir dinamik nesneler, yerleşik temel eleman türleri ve basit sınıflar gibi davranır. Her `CString` nesnesi benzersiz bir değeri temsil eder. `CString` nesneleri, ardından gerçek dizeleri yerine dizelerine olarak düşünülmelidir.

Atayabilirsiniz `CString` başka bir nesne. Ancak, değiştirdiğinizde bir iki `CString` nesnelerini, diğer `CString` nesne değiştirilmez, aşağıdaki örnekte gösterildiği gibi:

[!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]

Not örnekte, iki `CString` aynı karakter dizesini temsil ettikleri çünkü nesneleri "equal" değerlendirilir. `CString` Sınıfı eşitlik işlecini aşırı yüklemeler (`==`) karşılaştırmak için `CString` kimliklerini (adres) yerine nesneleri temel değerlerine (içeriği).

## <a name="see-also"></a>Ayrıca Bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)

