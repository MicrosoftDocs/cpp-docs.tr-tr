---
title: Atama dönüştürmeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- conversions, assignment
- assignment conversions
ms.assetid: 4ee01013-de32-4aae-b12e-0051d0cde927
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90e77f4bd1eddaa11762b9449a54cb7127498bae
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038186"
---
# <a name="assignment-conversions"></a>Atama Dönüştürmeleri

Atama işlemlerinde, atanan değerin türü atamayı alan değişkenin türüne dönüştürülür. C, bu bilgi dönüştürme sırasında kaybolsa bile integral ve kayan türler arasında atama ile yapılan dönüştürmelere izin verir. Açıklandığı gibi atamada türlerinde kullanılan dönüştürme yöntemi bağlıdır [olağan aritmetik dönüştürmeler](../c-language/usual-arithmetic-conversions.md) ve aşağıdaki bölümlerde:

- [İmzalı Tam Sayı Türlerinden Dönüştürmeler](../c-language/conversions-from-signed-integral-types.md)

- [İmzasız Tam Sayı Türlerinden Dönüştürmeler](../c-language/conversions-from-unsigned-integral-types.md)

- [Kayan Nokta Türlerinden Dönüşümler](../c-language/conversions-from-floating-point-types.md)

- [İşaretçi Türlerine ve Türlerinden Dönüşümler](../c-language/conversions-to-and-from-pointer-types.md)

- [Diğer Türlerden Dönüştürmeler](../c-language/conversions-from-other-types.md)

Tür niteleyicileri olsa da dönüştürmenin allowability etkilemez bir **const** l değeri atamanın solunda kullanılamaz.

## <a name="see-also"></a>Ayrıca Bkz.

[Tür Dönüştürmeleri](../c-language/type-conversions-c.md)