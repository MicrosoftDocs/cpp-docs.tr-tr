---
title: Dize Değişmez Değerlerini Depolama
ms.date: 11/04/2016
helpviewer_keywords:
- string literals, storage
ms.assetid: ba5e4d2c-d456-44b3-a8ca-354af547ac50
ms.openlocfilehash: 0d505479f0844122826a2f07b57eaa69f33932e8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157870"
---
# <a name="storage-of-string-literals"></a>Dize Değişmez Değerlerini Depolama

Bir sabit dize karakterlerini sırada bitişik bellek konumlarında depolanır. Bir kaçış dizisi (gibi **\\ \\** veya  **\\"**) dize sabit değeri içinde tek bir karakter olarak sayılır. Bir null karakteri (tarafından temsil edilen **\0** kaçış dizisi) otomatik olarak eklenir ve sonuna her dize sabit değeri olarak işaretler. (Bu sistemdeki [çeviri aşaması](../preprocessor/phases-of-translation.md) 7.) Derleyici iki özdeş dizeleri iki farklı adreslerde depolayabilir değil olduğunu unutmayın. [/GF](../build/reference/gf-eliminate-duplicate-strings.md) derleyicinin yürütülebilir dosyaya aynı dizelerin tek bir kopyasını zorlar.

## <a name="remarks"></a>Açıklamalar

**Microsoft'a özgü**

Dizeleri statik depolama süresine sahip. Bkz: [depolama sınıfları](../c-language/c-storage-classes.md) depolama süresi hakkında bilgi için.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Dize Değişmez Değerleri](../c-language/c-string-literals.md)
