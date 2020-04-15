---
title: DLL'den İşlevleri Ad Yerine Sıraya Göre Dışarı Aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- exporting functions [C++], ordinal values
- ordinal exports [C++]
- exporting DLLs [C++], ordinal values
- NONAME attribute
ms.assetid: 679719fd-d965-4df3-9f7a-7d86ad831702
ms.openlocfilehash: 66e99b18d181e9067e90398c35a61db2da66c301
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328583"
---
# <a name="exporting-functions-from-a-dll-by-ordinal-rather-than-by-name"></a>DLL'den İşlevleri Ad Yerine Sıraya Göre Dışarı Aktarma

DLL'nizden işlevleri dışa aktarmanın en basit yolu, işlevleri ada göre dışa aktarmaktır. Örneğin, **__declspec(dllexport)** kullandığınızda ne olur. Ancak işlevleri ordinal ile dışa aktarabilirsiniz. Bu teknikle, **__declspec (dllexport)** yerine bir .def dosyası kullanmanız gerekir. Bir işlevin ordinal değerini belirtmek için,.def dosyasındaki işlev adına onun ordinal'ını ekle. Ordinals belirtme hakkında bilgi için [bkz.](exporting-from-a-dll-using-def-files.md)

> [!TIP]
> DLL dosya boyutunu optimize etmek istiyorsanız, dışa aktarılan her işlevde **NONAME** özniteliğini kullanın. **NONAME** özniteliği ile, ordinals işlev adları yerine DLL dışa aktarma tablosunda depolanır. Birçok işlev dışa aktarıyorsanız, bu önemli bir tasarruf olabilir.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Bir .def dosyası kullanın, böylece ordinal ile dışa aktarabiliyorum](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport) kullanın](exporting-from-a-dll-using-declspec-dllexport.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL'den Dışarı Aktarma](exporting-from-a-dll.md)
