---
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
ms.openlocfilehash: de8b648c6bca02c71a9cfedd92bfbe7e6ca56b70
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463654"
---
# <a name="rebase"></a>/REBASE

```
/REBASE[:modifiers]
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, belirtilen dosyalar için temel adres ayarlar. EDITBIN yakın 64 KB'lık kadar yuvarlanır her dosyasının boyutuna göre bitişik bir adres alanında yeni temel adresleri de atar. Temel adresler hakkında daha fazla ayrıntı için bkz: [temel adres](../../build/reference/base-base-address.md) (/ BASE) bağlayıcı seçeneği.

Programın yürütülebilir dosyaları ve dll belirtin *dosyaları* oldukları almasını sırada EDITBIN komut satırı bağımsız değişkeni. İsteğe bağlı olarak bir veya daha fazla belirtebilirsiniz *değiştiriciler*her bir virgülle ayrılmış (**,**):

|Değiştirici|Eylem|
|--------------|------------|
|**TEMEL =**<em>adresi</em>|Başlangıç adresini temel adresler dosyalarının yeniden atama için sağlar. Belirtin *adresi* ondalık ya da C dili gösterimi. TEMEL belirtilmezse, başlangıç temel adresi 0x400000 varsayılandır. AŞAĞI, kullanılan temel belirtilmelidir ve *adresi* temel adresler aralığının sonuna ayarlar.|
|**BASEFILE**|COFFBASE adlı bir dosya oluşturur. Bir metin dosyasıdır bağlantının tarafından beklenen biçimde/temel seçeneği, TXT.|
|**AŞAĞI**|Bitiş adresi temel adresleri aşağı doğru atamak EDITBIN söyler. Dosyalar, en yüksek olası adresi adres aralığının sonunu aşağıda bulunan ilk dosyasını belirtilen sırada atanır. Dosyaları alma için yeterli adres alanına emin olmak için temel aşağı ile kullanılması gerekir. Tarafından belirtilen dosyalarını gereken adres alanını belirlemek için EDITBIN /REBASE ile dosyalarda çalıştırmak ve için görüntülenen toplam boyutu 64 KB ekleyin.|

## <a name="see-also"></a>Ayrıca Bkz.

[EDITBIN Seçenekleri](../../build/reference/editbin-options.md)