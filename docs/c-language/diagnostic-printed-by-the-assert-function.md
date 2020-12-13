---
description: 'Hakkında daha fazla bilgi edinin: onaylama Işlevi tarafından yazdırılan tanılama'
title: assert İşlevinin Yazdırdığı Tanılama
ms.date: 11/04/2016
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
ms.openlocfilehash: cab4f6dfd2cab7d4b46486a103b39abb6ca17005
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186798"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>assert İşlevinin Yazdırdığı Tanılama

**Ansı 4,2** Tarafından yazdırılan tanı ve **onaylama** işlevinin sonlandırma davranışı

**Onaylama** işlevi bir tanılama iletisi yazdırır ve ifade false (0) ise **Abort** yordamını çağırır. Tanılama iletisi şu formdadır:

> **Onaylama başarısız oldu**: <em>ifade</em>**, dosya** <em>dosya adı</em>**, satır** *linumarası*

Burada *Dosya* adı kaynak dosyanın adıdır ve *linumarası* , kaynak dosyada başarısız olan onaylama hattının satır numarasıdır. *İfade* true ise (sıfır dışında) hiçbir eylem yapılmaz.

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık Işlevleri](../c-language/library-functions.md)
