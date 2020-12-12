---
description: 'Hakkında daha fazla bilgi edinin: dize sabit değerlerini depolama'
title: Dize Değişmez Değerlerini Depolama
ms.date: 11/04/2016
helpviewer_keywords:
- string literals, storage
ms.assetid: ba5e4d2c-d456-44b3-a8ca-354af547ac50
ms.openlocfilehash: 5139d480af6b808b5b2e008500794d95d63a9980
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205271"
---
# <a name="storage-of-string-literals"></a>Dize Değişmez Değerlerini Depolama

Sabit bir dizenin karakterleri, ardışık bellek konumlarında sırayla saklanır. **\\\\** Bir dize sabit değeri içindeki bir kaçış dizisi (veya **\\ "**) tek bir karakter olarak sayılır. Null bir karakter ( **\ 0** kaçış sırası tarafından temsil edilir) otomatik olarak öğesine eklenir ve her bir dize değişmez değerinin sonuna işaret eder. (Bu, [çeviri aşamasında](../preprocessor/phases-of-translation.md) 7 sırasında oluşur.) Derleyicinin iki farklı adrese sahip iki özdeş dizeyi depolayamadığını unutmayın. [/GF](../build/reference/gf-eliminate-duplicate-strings.md) , derleyicinin aynı dizelerin tek bir kopyasını yürütülebilir dosyaya yerleştirmesini zorlar.

## <a name="remarks"></a>Açıklamalar

**Microsoft'a Özgü**

Dizelerde statik depolama süresi var. Depolama süresi hakkında bilgi için bkz. [Depolama sınıfları](../c-language/c-storage-classes.md) .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C dize değişmez değerleri](../c-language/c-string-literals.md)
