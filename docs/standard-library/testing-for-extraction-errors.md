---
description: 'Hakkında daha fazla bilgi edinin: ayıklama hataları için test etme'
title: Ayıklama Hataları İçin Test Yapma
ms.date: 11/04/2016
helpviewer_keywords:
- extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
ms.openlocfilehash: c4a9b5c1ffe4f78718563b33e39012272cfb8042
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259363"
---
# <a name="testing-for-extraction-errors"></a>Ayıklama Hataları İçin Test Yapma

[Hata Işleme işlevlerinde](../standard-library/output-file-stream-member-functions.md)tartışılan çıkış hatası işleme işlevleri, giriş akışlarına uygulanır. Ayıklama sırasında hataları test etmek önemlidir. Bu ifadeyi göz önünde bulundurun:

```cpp
cin>> n;
```

`n`İşaretli bir tamsayı ise, 32.767 'den büyük bir değer (izin verilen en büyük değer veya MAX_INT) akışın `fail` bitini ayarlar ve `cin` nesne kullanılamaz hale gelir. Sonraki tüm Dışlamalar, hiçbir değer depolanmamış bir anında dönüşle sonuçlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş akışları](../standard-library/input-streams.md)
