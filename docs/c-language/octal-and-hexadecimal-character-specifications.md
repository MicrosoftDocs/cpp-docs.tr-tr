---
title: Sekizlik ve onaltılık karakter belirtimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- octal characters
- hexadecimal characters
ms.assetid: 9264f3ec-46b8-41a5-b21a-8f7ed0a11871
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7df785067fdde74fbbc4bb5a45dfdc1ca797da7b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077626"
---
# <a name="octal-and-hexadecimal-character-specifications"></a>Sekizlik ve Onaltılık Karakter Belirtimleri

Sıra **\\** <em>ooo</em> karakter kümesi üç basamaklı sekizli karakter kodu olarak ASCII herhangi bir karakteri belirtebileceğiniz anlamına gelir. Sekizli tamsayının sayısal değeri, istediğiniz karakter veya geniş karakter değerini belirtir.

Benzer şekilde, sıra **\x**<em>hhh</em> onaltılı karakter kodu olarak herhangi bir ASCII karakterini belirlemenize izin verir. Örneğin, ASCII geri karakterini normal C çıkış dizisi olarak verebilirsiniz (**\b**), veya olarak kod **\010** (sekizlik) veya **\x008** (onaltılık).

Sekizli bir çıkış dizisinde yalnızca 0 ile 7 arasındaki sayıları kullanabilirsiniz. Sekizli çıkış dizileri, asla üç basamaktan uzun olamaz ve sekizlik bir rakam olmayan ilk karakterle sonlandırılır. Üç sayının tümünü kullanmanız gerekmese de, en az birini kullanmanız gerekir. Örneğin, sekizli gösterimidir **\10** ASCII geri karakteri için ve **\101** olarak bir ASCII harfi için grafik.

Benzer şekilde, onaltılı çıkış dizisi için en az bir sayı kullanmanız gerekir, ancak ikinci ve üçüncü sayıyı atlayabilirsiniz. Bu nedenle, geri karakteri için onaltılık kaçış sırası olarak belirtebilirsiniz **\x8**, **\x08**, veya **\x008**.

Sekizli veya onaltılı çıkış dizisi değer türünün temsil edilebilir değerler aralığında olmalıdır **imzasız char** bir karakter sabiti ve türü için `wchar_t` bir geniş karakter sabiti için. Bkz: [çok baytlı ve geniş karakterler](../c-language/multibyte-and-wide-characters.md) geniş karakter sabitleri hakkında bilgi için.

Sekizli çıkış sabitlerinden farklı olarak, bir çıkış dizisinde bulunabilecek onaltılı basamaklar sınırsızdır. Onaltılı bir çıkış dizisi, onaltılı olmayan ilk karakterde sonlandırılır. Onaltılık basamak arasındaki harfleri içerdiğinden **bir** aracılığıyla **f**, kaçış sırasının istenen basamakta emin olmak için dikkatli olunmalıdır. Karışıklığı önlemek için, bir makro tanımına sekizli veya onaltılı karakter tanımları koyabilirsiniz:

```
#define Bell '\x07'
```

Onaltılı değerler için, doğru değeri net şekilde göstermek üzere dize bölünebilir:

```
"\xabc"    /* one character  */
"\xab" "c" /* two characters */
```

## <a name="see-also"></a>Ayrıca Bkz.

[C Karakter Sabitleri](../c-language/c-character-constants.md)