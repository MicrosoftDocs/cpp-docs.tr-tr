---
title: __declspec(dllimport) Kullanarak Veriyi İçeri Aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
ms.openlocfilehash: 341912b53301c3a11df4285167d66c8c1493d2fd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223999"
---
# <a name="importing-data-using-__declspecdllimport"></a>__declspec(dllimport) Kullanarak Veriyi İçeri Aktarma

Veri söz konusu olduğunda, kullanma, **`__declspec(dllimport)`** bir yöneltme katmanını kaldıran kullanışlı bir öğedir. Bir DLL 'den veri aktardığınızda içeri aktarma adresi tablosunu kullanmaya devam etmeniz gerekir. **`__declspec(dllimport)`** Daha önce, bu, dll 'den içe aktarılmış verilere erişirken ek bir yöneltme düzeyi kullanmayı unutmamanız gerekiyordu:

```
// project.h
#ifdef _DLL   // If accessing the data from inside the DLL
   ULONG ulDataInDll;

#else         // If accessing the data from outside the DLL
   ULONG *ulDataInDll;
#endif
```

Daha sonra verileri ' de dışarı aktarabilirsiniz. DEF dosyası:

```
// project.def
LIBRARY project
EXPORTS
   ulDataInDll   CONSTANT
```

ve ona DLL dışından erişin:

```
if (*ulDataInDll == 0L)
{
   // Do stuff here
}
```

Verileri olarak işaretlediğinizde **`__declspec(dllimport)`** , derleyici otomatik olarak yöneltme kodunu sizin için oluşturur. Yukarıdaki adımlar hakkında endişelenmenize artık gerek kalmaz. Daha önce belirtildiği gibi, **`__declspec(dllimport)`** DLL 'yi derlerken veri üzerinde bildirim kullanmayın. DLL içindeki işlevler, veri nesnesine erişmek için içeri aktarma adresi tablosunu kullanmaz; Bu nedenle, ek bir yöneltme düzeyi mevcut olmayacaktır.

Verileri DLL 'den otomatik olarak dışarı aktarmak için şu bildirimi kullanın:

```
__declspec(dllexport) ULONG ulDataInDLL;
```

## <a name="see-also"></a>Ayrıca bkz.

[Bir uygulamaya aktarma](importing-into-an-application.md)
