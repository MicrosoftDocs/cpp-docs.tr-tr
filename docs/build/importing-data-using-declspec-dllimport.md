---
title: "__Declspec(dllimport) kullanarak veriyi içeri aktarma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: dllimport
dev_langs: C++
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ebbc91b9144a7fe8025a34e9c1476ab23b604c46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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