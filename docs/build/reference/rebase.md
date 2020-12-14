---
description: Daha fazla bilgi edinin:/yeniden temellendir
title: /REBASE
ms.date: 11/04/2016
f1_keywords:
- /rebase
helpviewer_keywords:
- base addresses [C++]
- -REBASE editbin option
- REBASE editbin option
- DLLs [C++], linking
- executable files [C++], base address
- /REBASE editbin option [C++]
ms.assetid: 3f89d874-af5c-485b-974b-fd205f6e1a4b
ms.openlocfilehash: 6cbbf0a21bd9306167fb165b63c22e810518e161
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225342"
---
# <a name="rebase"></a>/REBASE

```
/REBASE[:modifiers]
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, belirtilen dosyaların temel adreslerini ayarlar. EDITBIN, bitişik bir adres alanına, en yakın 64 KB 'ye yuvarlayarak her bir dosyanın boyutuna göre yeni temel adresler atar. Taban adresler hakkında daha fazla bilgi için bkz. [temel adres](base-base-address.md) (/Base) bağlayıcı seçeneği.

Programın yürütülebilir dosyalarını ve DLL dosyalarını, EDITBIN komut satırındaki *dosyalar* bağımsız değişkeninde temel bulundukları sırayla belirtin. İsteğe bağlı olarak, her biri virgülle (**,**) ayırarak bir veya daha fazla *değiştirici* belirtebilirsiniz:

|Değiştirici|Eylem|
|--------------|------------|
|**Taban =**<em>Adres</em>|Dosyalara taban adresleri yeniden atamak için bir başlangıç adresi sağlar. *Adresi* ondalık veya C dili gösteriminde belirtin. TABAN belirtilmemişse, varsayılan başlangıç temel adresi 0x400000 ' dır. KAPALıYSA, taban, belirtilmelidir ve *Adres* taban adresleri aralığının sonunu ayarlar.|
|**BASEFILE**|BAĞLANTıNıN/BASE seçeneği tarafından beklenen biçimdeki bir metin dosyası olan COFFBASE.TXT adlı bir dosya oluşturur.|
|**KAPATıLıP**|EDITBIN 'e taban adresleri bitiş adresinden aşağı yeniden atamayı söyler. Dosyalar, adres aralığının sonundaki olası en yüksek adreste bulunan ilk dosya ile belirtilen sırada yeniden atanır. Dosyaları dayandırmak için yeterli adres alanı olduğundan emin olmak için temel ile birlikte kullanılmalıdır. Belirtilen dosyalar için gereken adres alanını öğrenmek için, dosyalarda/yeniden temelle EDITBIN komutunu çalıştırın ve görüntülenecek toplam boyutuna 64 KB ekleyin.|

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN seçenekleri](editbin-options.md)
