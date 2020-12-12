---
description: Daha fazla bilgi edinin:/BIND
title: /BIND
ms.date: 11/04/2016
f1_keywords:
- /bind
helpviewer_keywords:
- -BIND editbin option
- entry points, addresses
- BIND editbin option
- entry points
- /BIND editbin option
- import address table
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
ms.openlocfilehash: 87ea0265555991fca019760feec4395692c074ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187149"
---
# <a name="bind"></a>/BIND

```
/BIND[:PATH=path]
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, çalıştırılabilir bir dosya veya DLL için içeri aktarma adresi tablosundaki giriş noktalarının adreslerini ayarlar. Bir programın yüklenme süresini azaltmak için bu seçeneği kullanın.

Programın yürütülebilir dosyasını ve DLL dosyalarını EDITBIN komut satırındaki *dosyalar* bağımsız değişkeninde belirtin. /BIND için isteğe bağlı *yol* bağımsız değişkeni, belirtilen dosyalar tarafından kullanılan dll 'lerin konumunu belirtir. Birden çok dizini noktalı virgülle (**;**) ayırın. *Yol* belirtilmemişse, EDITBIN, PATH ortam değişkeninde belirtilen dizinleri arar. *Yol* BELIRTILMIŞSE, editbin yol değişkenini yoksayar.

Varsayılan olarak program yükleyicisi, bir program yüklediğinde giriş noktalarının adreslerini ayarlar. Bu işlemin ne kadar zaman aldığı, dll sayısına ve programda başvurulan giriş noktası sayısına bağlı olarak farklılık gösterir. Bir program/BIND ile değiştirilmişse ve yürütülebilir dosyanın temel adresleri ve DLL 'Leri zaten yüklü olan DLL 'lerle çakışıyorsa, işletim sisteminin bu adresleri ayarlaması gerekmez. Dosyaların yanlış dayandığı bir durumda, işletim sistemi programın dll 'Lerini yeniden konumlandırır ve programın yükleme süresine eklenen giriş noktası adreslerini yeniden hesaplar.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN seçenekleri](editbin-options.md)
