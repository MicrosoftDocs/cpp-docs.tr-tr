---
title: __declspec(dllimport) Kullanarak Veriyi İçeri Aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
ms.openlocfilehash: c9dce798572a91bcb9721f022393abb669970131
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440451"
---
# <a name="importing-data-using-__declspecdllimport"></a>__declspec(dllimport) Kullanarak Veriyi İçeri Aktarma

Veriler söz konusu olduğunda **__declspec (dllimport)** kullanarak bir yöneltme katmanını kaldıran kolay bir öğedir. Bir DLL 'den veri aktardığınızda içeri aktarma adresi tablosunu kullanmaya devam etmeniz gerekir. **__Declspec (dllimport)** öncesinde, bu, dll 'den içe aktarılmış verilere erişirken ek bir yöneltme düzeyi yapmanız gerektiğini unutmayın:

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

Verileri **__declspec (dllimport)** olarak işaretlediğinizde, derleyici yöneltme kodunu sizin için otomatik olarak oluşturur. Yukarıdaki adımlar hakkında endişelenmenize artık gerek kalmaz. Daha önce belirtildiği gibi, DLL 'yi derlerken veride **__declspec (dllimport)** bildirimini kullanmayın. DLL içindeki işlevler, veri nesnesine erişmek için içeri aktarma adresi tablosunu kullanmaz; Bu nedenle, ek bir yöneltme düzeyi mevcut olmayacaktır.

Verileri DLL 'den otomatik olarak dışarı aktarmak için şu bildirimi kullanın:

```
__declspec(dllexport) ULONG ulDataInDLL;
```

## <a name="see-also"></a>Ayrıca bkz.

[Bir Uygulamaya Aktarma](importing-into-an-application.md)
