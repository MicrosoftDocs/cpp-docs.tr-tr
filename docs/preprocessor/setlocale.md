---
description: pragmaMicrosoft C/C++ ' da setlocale yönergesi hakkında daha fazla bilgi edinin
title: setlocale pragma
ms.date: 01/22/2021
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
helpviewer_keywords:
- pragma, setlocale
- setlocale pragma
no-loc:
- pragma
ms.openlocfilehash: 936aa1c2eb26798438b48e61ec28007a12080f28
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713213"
---
# <a name="setlocale-no-locpragma"></a>`setlocale` pragma

Geniş karakter sabitleri ve dize değişmez değerleri çevrilirken kullanılacak *yerel ayarı*, ülkeyi, bölgeyi ve dili tanımlar.

## <a name="syntax"></a>Syntax

> **`#pragma setlocale( "`** [ *yerel ayar-dize* ] **`" )`**

## <a name="remarks"></a>Açıklamalar

Çok baytlı karakterleri geniş karakterlere dönüştürme algoritması yerel ayara göre değişiklik gösterebileceğinden veya derleme yürütülebilir dosyanın çalıştırılacağı farklı bir yerel ayarda gerçekleşebileceğinden, bu, pragma derleme zamanında hedef yerel ayarı belirtmenin bir yolunu sağlar. Geniş karakterli dizelerin doğru biçimde depolanmasını güvence altına alır.

Varsayılan *yerel ayar dize* , tarafından belirtilen boş dizedir `#pragma setlocale( "" )` .

**`"C"`** Yerel ayar, dizedeki her karakteri değeri olarak değerine eşler **`wchar_t`** . İçin diğer geçerli değerler, `setlocale` [dil dizeleri](../c-runtime-library/language-strings.md) listesinde bulunan girişlerdir. Örneğin, şunları belirtebilirsiniz:

```cpp
#pragma setlocale("dutch")
```

Bir dil dizesi belirtme özelliği, bilgisayarınızdaki kod sayfasına ve dil KIMLIĞI desteğine bağlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
