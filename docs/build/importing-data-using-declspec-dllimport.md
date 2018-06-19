---
title: __Declspec(dllimport) kullanarak veriyi içeri aktarma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- dllimport
dev_langs:
- C++
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9877c5a229c3cabcb7703dd2617d1d57e3512f0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368518"
---
# <a name="importing-data-using-declspecdllimport"></a>__declspec(dllimport) Kullanarak Veriyi İçeri Aktarma
Kullanarak verileri, söz konusu olduğunda **__declspec(dllimport)** yöneltme bir katmanı kaldırır kolaylık öğedir. DLL'den dışarı veri aktardığınızda, içeri aktarma adres tablosunu Git çözümlenmedi. Önce **__declspec(dllimport)**, bu verilere erişme DLL'den dışarı aktardığınızda yöneltme için fazladan bir düzey yapmayı unutmayın gerekiyordu anlamına gelir:  
  
```  
// project.h  
#ifdef _DLL   // If accessing the data from inside the DLL  
   ULONG ulDataInDll;  
  
#else         // If accessing the data from outside the DLL  
   ULONG *ulDataInDll;  
#endif  
```  
  
 Ardından verileri dışarı aktarır. DEF dosyası:  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   CONSTANT  
```  
  
 ve dışında DLL'ine erişebilir:  
  
```  
if (*ulDataInDll == 0L)   
{  
   // Do stuff here  
}  
```  
  
 Verileri olarak işaretlediğinizde **__declspec(dllimport)**, derleyici otomatik olarak yöneltme kod sizin için oluşturur. Artık, yukarıdaki adımları hakkında endişelenmeniz gerekmez. Daha önce belirtildiği gibi kullanmayın **__declspec(dllimport)** DLL oluştururken verileri bildirimi. DLL işlevlerinde veri nesnesine erişmek için içeri aktarma adres tablosunu kullanmayın; Bu nedenle, yöneltme mevcut ek düzeyini olmayacaktır.  
  
 Verileri otomatik olarak DLL'den dışarı aktarmak için bu bildirimi kullanın:  
  
```  
__declspec(dllexport) ULONG ulDataInDLL;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir Uygulamaya Aktarma](../build/importing-into-an-application.md)