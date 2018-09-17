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
ms.openlocfilehash: a024d7488eb1683f40548839ab843da1e56f65e8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710222"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Bir Uygulamaya Aktarma](../build/importing-into-an-application.md)