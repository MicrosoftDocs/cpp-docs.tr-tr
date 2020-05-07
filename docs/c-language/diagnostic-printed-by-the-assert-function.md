---
title: assert İşlevinin Yazdırdığı Tanılama
ms.date: 11/04/2016
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
ms.openlocfilehash: 666ba22d642b772fe8ad336f57ab1bdd82bd2e18
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62234230"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>assert İşlevinin Yazdırdığı Tanılama

**Ansı 4,2** Tarafından yazdırılan tanı ve **onaylama** işlevinin sonlandırma davranışı

**Onaylama** işlevi bir tanılama iletisi yazdırır ve ifade false (0) ise **Abort** yordamını çağırır. Tanılama iletisi şu formdadır:

> **Onaylama başarısız oldu**: <em>ifade</em>**, dosya** <em>dosya adı</em>**, satır** *linumarası*

Burada *Dosya* adı kaynak dosyanın adıdır ve *linumarası* , kaynak dosyada başarısız olan onaylama hattının satır numarasıdır. *İfade* true ise (sıfır dışında) hiçbir eylem yapılmaz.

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)
