---
title: İfade deyimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f026a91846196e34f97b4d2cbcfa2c9fa749e8b7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058614"
---
# <a name="expression-statement"></a>İfade Deyimi

İfade deyimleri, ifadelerin değerlendirilmesine neden olur. İfade deyiminin sonucunda denetim aktarımı veya yineleme gerçekleşmez.

İfade deyimine yönelik sözdizimi

## <a name="syntax"></a>Sözdizimi

```
[expression ] ;
```

## <a name="remarks"></a>Açıklamalar

Bir ifade deyimindeki tüm ifadeler değerlendirilir ve sonraki ifade yürütülmeden önce tüm yan etkiler tamamlanır. En yaygın ifade deyimleri atamalar ve işlev çağrılarıdır.  İfade isteğe bağlı olduğundan, tek başına bir noktalı olarak adlandırılan bir boş ifade deyimi olarak değerlendirilir [null](../cpp/null-statement.md) deyimi.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Deyimlerine Genel Bakış](../cpp/overview-of-cpp-statements.md)