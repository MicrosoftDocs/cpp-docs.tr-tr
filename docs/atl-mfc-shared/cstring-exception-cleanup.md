---
description: 'Hakkında daha fazla bilgi edinin: CString Exception Cleanup'
title: CString özel durum Temizleme
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
ms.openlocfilehash: 9c77c9bf5d3f123315c126ce2361be63230c173b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167155"
---
# <a name="cstring-exception-cleanup"></a>CString özel durum Temizleme

MFC 'nin önceki sürümlerinde, [CString](../atl-mfc-shared/reference/cstringt-class.md) nesnelerini kullanarak temizlemeniz önemlidir. MFC sürüm 3,0 ve üzeri ile açık temizleme artık gerekli değildir.

MFC 'nin artık kullandığı C++ özel durum işleme mekanizması altında, bir özel durumdan sonra temizleme hakkında endişelenmeniz gerekmez. C++ "bir özel durumla sonra yığının" nasıl yakalanıp bir açıklaması için bkz. [try, catch ve throw deyimleri](../cpp/try-throw-and-catch-statements-cpp.md). MFC 'yi,  / c++ anahtar sözcükleri yerine **catch** makrolarını kullanmayı deneyin **`try`** ve **`catch`** MFC 'nin altında c++ özel durum mekanizmasını kullanır, bu nedenle açıkça temizlemeniz gerekmez.

## <a name="see-also"></a>Ayrıca bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)
