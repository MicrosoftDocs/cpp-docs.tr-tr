---
title: Assert işlevinin yazdırdığı tanılama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac5473a2dd592bbd9af2f65044d3d7d97515dc37
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103392"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>assert İşlevinin Yazdırdığı Tanılama

**ANSI 4.2** tarafından yazdırılan tanı ve sonlandırma davranışını **assert** işlevi

**Assert** işlevi bir tanılama iletisi ve aramalar yazdırır **iptal** ifade yanlışsa yordamı (0). Tanılama iletisi şu formdadır:

> **Onaylama işlemi başarısız**: <em>ifade</em>**, dosya** <em>filename</em>**, satır** *linenumber*

Burada *filename* kaynak dosyasının adıdır ve *linenumber* kaynak dosyada başarısız onaylama satır sayısıdır. Hiçbir işlem yapılmadı, *ifade* true (sıfırdan farklı).

## <a name="see-also"></a>Ayrıca Bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)