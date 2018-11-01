---
title: Derleyici Hatası C3888
ms.date: 11/04/2016
f1_keywords:
- C3888
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
ms.openlocfilehash: 067412e59041cb98b68cb373c4671c243ab8a0ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479072"
---
# <a name="compiler-error-c3888"></a>Derleyici Hatası C3888

'name': Bu sabit değerli veri üyesiyle ilişkili const ifadesi C + tarafından desteklenmiyor +/ CLI

*Adı* ile bildirilen veri üyesi [değişmez değer](../../windows/literal-cpp-component-extensions.md) anahtar sözcüğü, derleyici desteği olmayan bir değer ile başlatılır. Derleyici, yalnızca sabit integral, enum veya dize türleri destekler. Olası nedeni **C3888** hatadır veri üyesi bir bayt dizisi ile başlatılır.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Desteklenen bir türde bildirilen sabit değerli veri üyesi olduğundan emin olun.

## <a name="see-also"></a>Ayrıca Bkz.

[değişmez değer](../../windows/literal-cpp-component-extensions.md)