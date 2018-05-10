---
title: Ayıklama hataları için test yapma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc84277b654a79eebd38461c3ee83aefd533e4a8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="testing-for-extraction-errors"></a>Ayıklama Hataları İçin Test Yapma

Çıktı ele hata işleme işlevleri [hata işleme işlevleri](../standard-library/output-file-stream-member-functions.md), akış girişi için geçerlidir. Hata ayıklama sırasında test önemlidir. Bu bildirimi göz önünde bulundurun:

```cpp
cin>> n;
```

Varsa `n` 32.767 büyük bir değer imzalı bir tamsayı (izin verilen en fazla değer veya MAX_INT) akışın ayarlar `fail` bit ve `cin` nesne kullanılamaz olur. Tüm sonraki ayıklamaları sonuçla anlık bir return içinde depolanan herhangi bir değer.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)<br/>
