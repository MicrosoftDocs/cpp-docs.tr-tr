---
title: Dize değişmez değerlerini depolama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- string literals, storage
ms.assetid: ba5e4d2c-d456-44b3-a8ca-354af547ac50
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 111acab00783de67dcb3ecc8b9d45fe112332158
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019530"
---
# <a name="storage-of-string-literals"></a>Dize Değişmez Değerlerini Depolama

Bir sabit dize karakterlerini sırada bitişik bellek konumlarında depolanır. Bir kaçış dizisi (gibi **\\ \\** veya  **\\"**) dize sabit değeri içinde tek bir karakter olarak sayılır. Bir null karakteri (tarafından temsil edilen **\0** kaçış dizisi) otomatik olarak eklenir ve sonuna her dize sabit değeri olarak işaretler. (Bu sistemdeki [çeviri aşaması](../preprocessor/phases-of-translation.md) 7.) Derleyici iki özdeş dizeleri iki farklı adreslerde depolayabilir değil olduğunu unutmayın. [/GF](../build/reference/gf-eliminate-duplicate-strings.md) derleyicinin yürütülebilir dosyaya aynı dizelerin tek bir kopyasını zorlar.

## <a name="remarks"></a>Açıklamalar

**Microsoft'a özgü**

Dizeleri statik depolama süresine sahip. Bkz: [depolama sınıfları](../c-language/c-storage-classes.md) depolama süresi hakkında bilgi için.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[C Dize Değişmez Değerleri](../c-language/c-string-literals.md)