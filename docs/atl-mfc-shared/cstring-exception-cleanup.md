---
title: CString özel durum Temizleme
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
ms.openlocfilehash: 48c8f1c0040236a4f7bf27a2d5ad985ae343c03a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222062"
---
# <a name="cstring-exception-cleanup"></a>CString özel durum Temizleme

MFC 'nin önceki sürümlerinde, [CString](../atl-mfc-shared/reference/cstringt-class.md) nesnelerini kullanarak temizlemeniz önemlidir. MFC sürüm 3,0 ve üzeri ile açık temizleme artık gerekli değildir.

MFC 'nin artık kullandığı C++ özel durum işleme mekanizması altında, bir özel durumdan sonra temizleme hakkında endişelenmeniz gerekmez. C++ "bir özel durumla sonra yığının" nasıl yakalanıp bir açıklaması için bkz. [try, catch ve throw deyimleri](../cpp/try-throw-and-catch-statements-cpp.md). MFC 'yi, **TRY** / c++ anahtar sözcükleri yerine**catch** makrolarını kullanmayı deneyin **`try`** ve **`catch`** MFC 'nin altında c++ özel durum mekanizmasını kullanır, bu nedenle açıkça temizlemeniz gerekmez.

## <a name="see-also"></a>Ayrıca bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)
