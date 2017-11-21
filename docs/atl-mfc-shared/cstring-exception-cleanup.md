---
title: "CString özel durum temizleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 68fb6f60c46ff5094e1b7a578a47646f42cea79e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cstring-exception-cleanup"></a>CString özel durum temizleme
MFC önceki sürümlerde, temizleme, önemli [CString](../atl-mfc-shared/reference/cstringt-class.md) kullandıktan sonra nesneleri. MFC sürüm 3.0 ve sonraki açık temizleme artık gerekli değildir.  
  
 MFC artık kullanır mekanizması C++ özel durum işleme altında özel durumdan sonra temizleme hakkında endişelenmeniz gerekmez. "Bir özel durum yakalandı sonra nasıl bir açıklaması için C++ yığın unwinds" için bkz: [try catch ve throw deyimleri](../cpp/try-throw-and-catch-statements-cpp.md). MFC kullansanız bile **deneyin**/**CATCH** makroları C++ anahtar sözcükleri yerine **deneyin** ve **catch**, MFC C++ kullanır özel durum mekanizması altında hala şekilde gerekmez açıkça temizleme.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [Özel durum işleme](../mfc/exception-handling-in-mfc.md)

