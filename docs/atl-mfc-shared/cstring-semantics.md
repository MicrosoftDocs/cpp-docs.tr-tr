---
description: 'Daha fazla bilgi edinin: CString semantiği'
title: CString semantiği
ms.date: 11/04/2016
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
ms.openlocfilehash: 7c6dde91e7f87908c0c6bc2d49ff455eb79f6eb3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167051"
---
# <a name="cstring-semantics"></a>CString semantiği

[CString](../atl-mfc-shared/reference/cstringt-class.md) nesneleri genişleyebilecekleri dinamik nesneler olsa da, yerleşik temel türler ve basit sınıflar gibi davranır. Her `CString` nesne benzersiz bir değer temsil eder. `CString` nesneler, dizeler için işaretçiler yerine gerçek dizeler olarak düşünülmelidir.

Bir `CString` nesneyi başka bir nesneye atayabilirsiniz. Ancak, iki nesneden birini değiştirdiğinizde `CString` , `CString` Aşağıdaki örnekte gösterildiği gibi diğer nesne değiştirilmez:

[!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]

Örneğin, iki `CString` nesnenin aynı karakter dizesini temsil ettiğinden "eşit" olarak kabul edileceğini unutmayın. `CString`Sınıfı, `==` iki `CString` nesneyi kimlik (adres) yerine değerlerine (içeriklerine) göre karşılaştırmak için eşitlik işlecini () aşırı yükler.

## <a name="see-also"></a>Ayrıca bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
