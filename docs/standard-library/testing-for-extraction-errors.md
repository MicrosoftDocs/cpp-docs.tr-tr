---
title: Ayıklama Hataları İçin Test Yapma
ms.date: 11/04/2016
helpviewer_keywords:
- extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
ms.openlocfilehash: db551a21fd33665d83b11373f040be158406d492
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453671"
---
# <a name="testing-for-extraction-errors"></a>Ayıklama Hataları İçin Test Yapma

[Hata Işleme işlevlerinde](../standard-library/output-file-stream-member-functions.md)tartışılan çıkış hatası işleme işlevleri, giriş akışlarına uygulanır. Ayıklama sırasında hataları test etmek önemlidir. Bu ifadeyi göz önünde bulundurun:

```cpp
cin>> n;
```

İşaretli bir tamsayı ise, 32.767 'den büyük bir değer (izin verilen en büyük değer veya MAX_INT) `fail` akışın bitini ayarlar ve `cin` nesne kullanılamaz hale gelir. `n` Sonraki tüm Dışlamalar, hiçbir değer depolanmamış bir anında dönüşle sonuçlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)
