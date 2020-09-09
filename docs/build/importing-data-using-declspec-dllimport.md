---
title: __declspec(dllimport) kullanarak veriyi içeri aktarma
description: DLL verilerini içeri aktarmak için __declspec (dllimport) kullanma.
ms.date: 09/03/2020
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
ms.openlocfilehash: cb9850306d6e73b88e2926a6f068ae21f8d32530
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609117"
---
# <a name="importing-data-using-__declspecdllimport"></a>Kullanarak verileri içeri aktarma `__declspec(dllimport)`

Veri söz konusu olduğunda, kullanma, **`__declspec(dllimport)`** bir yöneltme katmanını kaldıran kullanışlı bir öğedir. Bir DLL 'den veri aktardığınızda içeri aktarma adresi tablosunu kullanmaya devam etmeniz gerekir. **`__declspec(dllimport)`** Daha önce, bu, dll 'den içe aktarılmış verilere erişirken ek bir yöneltme düzeyi kullanmayı unutmamanız gerekiyordu:

```C
// project.h
// Define PROJECT_EXPORTS when building your DLL
#ifdef PROJECT_EXPORTS   // If accessing the data from inside the DLL
   ULONG ulDataInDll;

#else         // If accessing the data from outside the DLL
   ULONG *ulDataInDll;
#endif
```

Daha sonra verileri ' de dışarı aktarabilirsiniz. DEF dosyası:

```DEF
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   CONSTANT
```

ve ona DLL dışından erişin:

```C
if (*ulDataInDll == 0L)
{
   // Do stuff here
}
```

Verileri olarak işaretlediğinizde **`__declspec(dllimport)`** , derleyici otomatik olarak yöneltme kodunu sizin için oluşturur. Yukarıdaki adımlar hakkında endişelenmenize artık gerek kalmaz. Daha önce belirtildiği gibi, **`__declspec(dllimport)`** DLL 'yi derlerken veri üzerinde bildirim kullanmayın. DLL içindeki işlevler, veri nesnesine erişmek için içeri aktarma adresi tablosunu kullanmaz; Bu nedenle, ek bir yöneltme düzeyi mevcut olmayacaktır.

Verileri DLL 'den otomatik olarak dışarı aktarmak için şu bildirimi kullanın:

```C
// project.h
// Define PROJECT_EXPORTS when building your DLL
#ifdef PROJECT_EXPORTS   // If accessing the data from inside the DLL
   __declspec(dllexport) ULONG ulDataInDLL;

#else         // If accessing the data from outside the DLL
   __declspec(dllimport) ULONG ulDataInDLL;
#endif
```

## <a name="see-also"></a>Ayrıca bkz.

[Bir uygulamaya aktarma](importing-into-an-application.md)
