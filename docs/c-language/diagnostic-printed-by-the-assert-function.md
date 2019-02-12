---
title: assert İşlevinin Yazdırdığı Tanılama
ms.date: 11/04/2016
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
ms.openlocfilehash: 666ba22d642b772fe8ad336f57ab1bdd82bd2e18
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56151006"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>assert İşlevinin Yazdırdığı Tanılama

**ANSI 4.2** tarafından yazdırılan tanı ve sonlandırma davranışını **assert** işlevi

**Assert** işlevi bir tanılama iletisi ve aramalar yazdırır **iptal** ifade yanlışsa yordamı (0). Tanılama iletisi şu formdadır:

> **Onaylama işlemi başarısız**: <em>ifade</em>**, dosya** <em>filename</em>**, satır** *linenumber*

Burada *filename* kaynak dosyasının adıdır ve *linenumber* kaynak dosyada başarısız onaylama satır sayısıdır. Hiçbir işlem yapılmadı, *ifade* true (sıfırdan farklı).

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)
