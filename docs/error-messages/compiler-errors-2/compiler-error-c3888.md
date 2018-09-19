---
title: Derleyici Hatası C3888 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3888
dev_langs:
- C++
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9292f54fee467a5f8d01202b6ed7ca991b52d43
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096468"
---
# <a name="compiler-error-c3888"></a>Derleyici Hatası C3888

'name': Bu sabit değerli veri üyesiyle ilişkili const ifadesi C + tarafından desteklenmiyor +/ CLI

*Adı* ile bildirilen veri üyesi [değişmez değer](../../windows/literal-cpp-component-extensions.md) anahtar sözcüğü, derleyici desteği olmayan bir değer ile başlatılır. Derleyici, yalnızca sabit integral, enum veya dize türleri destekler. Olası nedeni **C3888** hatadır veri üyesi bir bayt dizisi ile başlatılır.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Desteklenen bir türde bildirilen sabit değerli veri üyesi olduğundan emin olun.

## <a name="see-also"></a>Ayrıca Bkz.

[değişmez değer](../../windows/literal-cpp-component-extensions.md)