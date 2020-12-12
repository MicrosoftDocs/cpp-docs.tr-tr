---
description: 'Hakkında daha fazla bilgi edinin: dizeleri başlatma'
title: Başlatma Dizeleri
ms.date: 11/04/2016
helpviewer_keywords:
- character arrays, initializing
- strings [C++], initializing
- initializing arrays, strings
ms.assetid: 0ab8079d-d0d3-48f9-afd1-36a7bb439b29
ms.openlocfilehash: 145fc55eaccd64b30bae2736dd78317dc5db7d7d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137585"
---
# <a name="initializing-strings"></a>Başlatma Dizeleri

Bir dize sabit değeri (veya geniş dize sabit değeri) ile bir karakterler (veya geniş karakterler) dizisi başlatabilirsiniz. Örneğin:

```
char code[ ] = "abc";
```

dört öğeli karakter dizisi olarak `code` başlatır. Dördüncü öğe, tüm dize sabit değerlerini sonlandıran null karakterdir.

Tanımlayıcı listesi, yalnızca başlatılacak tanımlayıcıların sayısı kadar uzun olabilir. Dizede daha kısa bir dize boyutu belirtirseniz, ek karakterler yoksayılır. Örneğin, aşağıdaki bildirim üç öğeli karakter dizisi olarak `code` başlatır:

```
char code[3] = "abcd";
```

Başlatıcının yalnızca ilk üç karakteri `code` öğesine atanır. `d` karakteri ve dizeyi sonlandıran null karakteri atılır. Bunun, sonlandırılmayan bir dize (yani sonunu gösteren bir 0 değeri olmayan bir dize) ve bu durumu gösteren bir tanılama iletisi oluşturduğunu unutmayın.

Bildirim

```
char s[] = "abc", t[3] = "abc";
```

şununla aynıdır

```
char s[]  = {'a', 'b', 'c', '\0'},
     t[3] = {'a', 'b', 'c' };
```

Dizi belirtilen dizi boyutundan kısaysa, dizinin kalan öğeleri 0'a başlatılır.

**Microsoft'a Özgü**

Microsoft C'de, dize sabit değerlerinin uzunluğu en fazla 2048 bayt olabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Başlatma](../c-language/initialization.md)
