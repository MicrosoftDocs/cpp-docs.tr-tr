---
title: __declspec(dllimport) Kullanarak Veriyi İçeri Aktarma
ms.date: 11/04/2016
f1_keywords:
- dllimport
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
ms.openlocfilehash: 74ad93e640a4e961f7670077227bb5c35a42c20f
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342102"
---
# <a name="importing-data-using-declspecdllimport"></a>__declspec(dllimport) Kullanarak Veriyi İçeri Aktarma

Kullanarak verileri, söz konusu olduğunda **__declspec(dllimport)** katmanındaki yöneltme kaldıran bir kolaylık öğesidir. DLL'den verileri içeri aktardığınızda, içeri aktarma adres tablosu Git çözümlenmedi. Önce **__declspec(dllimport)**, bu verilere erişme DLL'den dışarı aktardığınızda, ek bir yöneltme düzeyi yapmayı unutmamanız gerekiyordu geliyordu:

```
// project.h
#ifdef _DLL   // If accessing the data from inside the DLL
   ULONG ulDataInDll;

#else         // If accessing the data from outside the DLL
   ULONG *ulDataInDll;
#endif
```

Ardından verileri aktarın. DEF dosyası:

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   CONSTANT
```

ve DLL dışında erişebilirsiniz:

```
if (*ulDataInDll == 0L)
{
   // Do stuff here
}
```

Verileri olarak işaretlediğinizde **__declspec(dllimport)**, derleyici otomatik olarak yöneltme kod sizin için oluşturur. Artık, yukarıdaki adımları hakkında endişelenmeniz gerekmez. Daha önce belirtildiği gibi kullanmayın **__declspec(dllimport)** DLL'yi oluştururken veri bildiriminde. DLL içindeki işlevleri içeri aktarma adres tablosunda veri nesnesine erişmek için kullanmayın; Bu nedenle, ek düzeyi yöneltme mevcut olmaz.

Verileri otomatik olarak DLL'den dışarı aktarmak için bu bildirimi kullanın:

```
__declspec(dllexport) ULONG ulDataInDLL;
```

## <a name="see-also"></a>Ayrıca bkz.

[Bir Uygulamaya Aktarma](importing-into-an-application.md)
