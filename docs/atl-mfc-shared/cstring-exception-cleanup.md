---
title: CString özel durum temizleme
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
ms.openlocfilehash: d131ce8ebe5158d7f3a567580064068742b63707
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57746233"
---
# <a name="cstring-exception-cleanup"></a>CString özel durum temizleme

MFC önceki sürümlerinde, temizleme, önemli [CString](../atl-mfc-shared/reference/cstringt-class.md) kullandıktan sonra nesneleri. MFC sürüm 3.0 ve sonraki açıkça temizlenmesi artık gerekli değildir.

Artık MFC kullanan C++ özel durum işleme mekanizmasını altında bir özel durumdan sonra temizleme hakkında endişelenmeniz gerekmez. "Bir özel durum yakalandı sonra bir açıklaması için C++ yığın geriye doğru izler" için bkz: [try, catch ve throw deyimleri](../cpp/try-throw-and-catch-statements-cpp.md). MFC kullanıyor olsanız bile **deneyin**/**CATCH** C++ anahtar sözcükleri yerine makroları **deneyin** ve **catch**, MFC, C++ kullanır özel durum mekanizması, altında hala şekilde gerekmez açıkça temizleme.

## <a name="see-also"></a>Ayrıca bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)
