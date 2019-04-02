---
title: Derleyici Hatası C3888
ms.date: 11/04/2016
f1_keywords:
- C3888
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
ms.openlocfilehash: 20251292ec4635ea855a56890878bc55f567ab62
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58777473"
---
# <a name="compiler-error-c3888"></a>Derleyici Hatası C3888

'name': Bu sabit değerli veri üyesiyle ilişkili const ifadesi C + tarafından desteklenmiyor +/ CLI

*Adı* ile bildirilen veri üyesi [değişmez değer](../../extensions/literal-cpp-component-extensions.md) anahtar sözcüğü, derleyici desteği olmayan bir değer ile başlatılır. Derleyici, yalnızca sabit integral, enum veya dize türleri destekler. Olası nedeni **C3888** hatadır veri üyesi bir bayt dizisi ile başlatılır.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Desteklenen bir türde bildirilen sabit değerli veri üyesi olduğundan emin olun.

## <a name="see-also"></a>Ayrıca Bkz.

[değişmez değer](../../extensions/literal-cpp-component-extensions.md)