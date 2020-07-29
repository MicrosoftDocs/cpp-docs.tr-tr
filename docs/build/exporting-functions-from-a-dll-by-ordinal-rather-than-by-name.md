---
title: DLL'den İşlevleri Ad Yerine Sıraya Göre Dışarı Aktarma
ms.date: 11/04/2016
helpviewer_keywords:
- exporting functions [C++], ordinal values
- ordinal exports [C++]
- exporting DLLs [C++], ordinal values
- NONAME attribute
ms.assetid: 679719fd-d965-4df3-9f7a-7d86ad831702
ms.openlocfilehash: 3229c98a0a6bbb0ebc4fa0ef055e4019bd6c7bd8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229824"
---
# <a name="exporting-functions-from-a-dll-by-ordinal-rather-than-by-name"></a>DLL'den İşlevleri Ad Yerine Sıraya Göre Dışarı Aktarma

DLL 'nizden işlevleri dışarı aktarmanın en kolay yolu, adları ada göre dışarı aktarmanız. Örneğin, kullandığınızda bu durum olur **`__declspec(dllexport)`** . Ancak, işlevleri sıraya göre dışarı aktarabilirsiniz. Bu teknikle, yerine bir. def dosyası kullanmanız gerekir **`__declspec(dllexport)`** . Bir işlevin sıra değerini belirtmek için,. def dosyasındaki işlev adına sıra sayısını ekleyin. Sıra sayılarını belirtme hakkında bilgi için bkz [.. def dosyaları kullanarak dll 'Den dışarı aktarma](exporting-from-a-dll-using-def-files.md).

> [!TIP]
> DLL 'nizin dosya boyutunu iyileştirmek istiyorsanız, her bir içe aktarılmış işlevde **noname** özniteliğini kullanın. **Noname** özniteliğiyle, sıra sayıları işlev adları yerine dll 'nin dışarı aktarma tablosunda depolanır. Birçok işlevi dışarı aktarıyorsanız bu çok önemli bir tasarruf olabilir.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Ordinal 'e göre dışarı aktarmak için. def dosyası kullanın](exporting-from-a-dll-using-def-files.md)

- [__Declspec (dllexport) kullan](exporting-from-a-dll-using-declspec-dllexport.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL'den Dışarı Aktarma](exporting-from-a-dll.md)
