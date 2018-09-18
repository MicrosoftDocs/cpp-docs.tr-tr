---
title: Joker karakter genişletmesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _setargv
dev_langs:
- C++
helpviewer_keywords:
- asterisk wildcard
- _setargv function
- command line [C++], processing arguments
- command line [C++], wildcards
- command-line wildcards
- question mark, wildcard
ms.assetid: 1a543398-607b-4404-93d1-45d290bde638
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cac6b61176b1559ea5810dc061638642926b3969
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077080"
---
# <a name="wildcard-expansion"></a>Joker Karakter Genişletmesi

## <a name="microsoft-specific"></a>Microsoft'a Özgü

Dosya adı ve yol bağımsız değişkenlerini komut satırında belirtmek için soru işareti (?) ve yıldız işareti (*) gibi joker karakterler kullanabilirsiniz.

Komut satırı bağımsız değişkenleri, bir yordam tarafından işlenir `_setargv` (veya `_wsetargv` geniş karakter ortamında), varsayılan olarak genişletmeyen joker karakterler ayrı dizelere `argv` dize dizisi. Joker karakter genişletmesini etkinleştirme hakkında daha fazla bilgi için [joker karakter bağımsız değişkenlerini genişletme](../c-language/expanding-wildcard-arguments.md).

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[main: Program Başlatma](../cpp/main-program-startup.md)