---
title: assert İşlevinin Yazdırdığı Tanılama
ms.date: 11/04/2016
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
ms.openlocfilehash: 330c694b53957cab2e44da7cb8b52031c33fb5a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549051"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>assert İşlevinin Yazdırdığı Tanılama

**ANSI 4.2** tarafından yazdırılan tanı ve sonlandırma davranışını **assert** işlevi

**Assert** işlevi bir tanılama iletisi ve aramalar yazdırır **iptal** ifade yanlışsa yordamı (0). Tanılama iletisi şu formdadır:

> **Onaylama işlemi başarısız**: <em>ifade</em>**, dosya** <em>filename</em>**, satır** *linenumber*

Burada *filename* kaynak dosyasının adıdır ve *linenumber* kaynak dosyada başarısız onaylama satır sayısıdır. Hiçbir işlem yapılmadı, *ifade* true (sıfırdan farklı).

## <a name="see-also"></a>Ayrıca Bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)