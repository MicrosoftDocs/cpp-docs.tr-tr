---
title: Başlatma Dizeleri
ms.date: 11/04/2016
helpviewer_keywords:
- character arrays, initializing
- strings [C++], initializing
- initializing arrays, strings
ms.assetid: 0ab8079d-d0d3-48f9-afd1-36a7bb439b29
ms.openlocfilehash: c9dbad72314e9ce01d022d26209e2132c29c106a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326007"
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

**Microsoft'a özgü**

Microsoft C'de, dize sabit değerlerinin uzunluğu en fazla 2048 bayt olabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Başlatma](../c-language/initialization.md)
