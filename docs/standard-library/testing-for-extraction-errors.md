---
title: Ayıklama Hataları İçin Test Yapma
ms.date: 11/04/2016
helpviewer_keywords:
- extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
ms.openlocfilehash: 62d9c94f366ec666acf2179803c62e4a3ccd7e6a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412065"
---
# <a name="testing-for-extraction-errors"></a>Ayıklama Hataları İçin Test Yapma

Çıkış ele hata işleme işlevleri [hata işleme işlevleri](../standard-library/output-file-stream-member-functions.md), giriş akışları için geçerlidir. Hata ayıklama sırasında test önemlidir. Bu bildirimi göz önünde bulundurun:

```cpp
cin>> n;
```

Varsa `n` 32.767 büyük bir değer imzalı bir tamsayı olduğu (izin verilen maksimum değeri veya MAX_INT) akışın ayarlar `fail` bit ve `cin` nesne haline gelir kullanılamaz. Depolanan bir değer içermeyen tüm sonraki ayıklamalar sonucu hemen bir dönüş içinde.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)<br/>
