---
description: 'Daha fazla bilgi edinin: setlocale pragma'
title: setlocale pragması
ms.date: 08/29/2019
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
helpviewer_keywords:
- pragmas, setlocale
- setlocale pragma
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
ms.openlocfilehash: 375a2075381b39037a6a723f7d28ef73749ec08f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167311"
---
# <a name="setlocale-pragma"></a>setlocale pragması

Geniş karakter sabitleri ve dize değişmez değerleri çevrilirken kullanılacak *yerel ayarı*, ülkeyi, bölgeyi ve dili tanımlar.

## <a name="syntax"></a>Syntax

> **#pragma setlocale ("** [ *locale-String* ] **")**

## <a name="remarks"></a>Açıklamalar

Çok baytlı karakterleri geniş karakterlere dönüştürme algoritması yerel ayara göre değişiklik gösterebileceğinden veya derleme yürütülebilir dosyanın çalıştırılacağı farklı bir yerel ayarda gerçekleşebileceğinden, bu pragma derleme zamanında hedef yerel ayarı belirtmek için bir yol sağlar. Geniş karakterli dizelerin doğru biçimde depolanmasını güvence altına alır.

Varsayılan *yerel ayar dizesi* "" dir.

"C" yerel ayarı dizedeki her karakteri değerine olarak eşler **`wchar_t`** . İçin diğer geçerli değerler, `setlocale` [dil dizeleri](../c-runtime-library/language-strings.md) listesinde bulunan girişlerdir. Örneğin, şunları belirtebilirsiniz:

```cpp
#pragma setlocale("dutch")
```

Bir dil dizesi belirtme özelliği, bilgisayarınızdaki kod sayfasına ve dil KIMLIĞI desteğine bağlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
