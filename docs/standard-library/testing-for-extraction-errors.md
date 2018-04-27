---
title: Ayıklama hataları için test yapma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9394f387546f9b9dccf72f532148aa2b9161ce15
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="testing-for-extraction-errors"></a>Ayıklama Hataları İçin Test Yapma

Çıktı ele hata işleme işlevleri [hata işleme işlevleri](../standard-library/output-file-stream-member-functions.md), akış girişi için geçerlidir. Hata ayıklama sırasında test önemlidir. Bu bildirimi göz önünde bulundurun:

```cpp
cin>> n;
```

Varsa `n` 32.767 büyük bir değer imzalı bir tamsayı (izin verilen en fazla değer veya MAX_INT) akışın ayarlar `fail` bit ve `cin` nesne kullanılamaz olur. Tüm sonraki ayıklamaları sonuçla anlık bir return içinde depolanan herhangi bir değer.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)<br/>
