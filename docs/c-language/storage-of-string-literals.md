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

Sabit bir dizenin karakterleri, ardışık bellek konumlarında sırayla saklanır. Bir dize sabit değeri içindeki bir ** \\ ** kaçış dizisi (veya ** \\"**) tek bir karakter olarak sayılır. Null bir karakter ( **\ 0** kaçış sırası tarafından temsil edilir) otomatik olarak öğesine eklenir ve her bir dize değişmez değerinin sonuna işaret eder. (Bu, [çeviri aşamasında](../preprocessor/phases-of-translation.md) 7 sırasında oluşur.) Derleyicinin iki farklı adrese sahip iki özdeş dizeyi depolayamadığını unutmayın. [/GF](../build/reference/gf-eliminate-duplicate-strings.md) , derleyicinin aynı dizelerin tek bir kopyasını yürütülebilir dosyaya yerleştirmesini zorlar.

## <a name="remarks"></a>Açıklamalar

**Microsoft'a Özgü**

Dizelerde statik depolama süresi var. Depolama süresi hakkında bilgi için bkz. [Depolama sınıfları](../c-language/c-storage-classes.md) .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Dize Değişmez Değerleri](../c-language/c-string-literals.md)
