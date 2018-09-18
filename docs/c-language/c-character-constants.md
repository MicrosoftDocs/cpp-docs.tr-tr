---
title: C karakter sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- characters, constants
- (') single quotation mark
- constants, character
- single quotation mark
ms.assetid: 388ae7d7-2c3a-44d6-a507-63f541ecd2da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9908bfd8be662a53727e9c833626f329dd45c04
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038587"
---
# <a name="c-character-constants"></a>C Karakter Sabitleri

"Karakter sabiti" tek bir karakter gösterilebilir karakter tek tırnak içinde kümesindeki kapsayan tarafından oluşturulur (**' '**). Karakter sabitleri karakterleri temsil etmek için kullanılan [yürütme karakter kümesi](../c-language/execution-character-set.md).

## <a name="syntax"></a>Sözdizimi

*karakter sabiti*: **'** *c karakter dizisi* **'**

**L'** *c karakter dizisi* **'**

*c karakter dizisi*: *c char*

*c karakter dizisi c-char*

*c karakter*: herhangi bir üyesi kaynak karakter kümesi dışında tek tırnak işareti (**'**), ters eğik çizgi (**\\**), veya yeni satır karakteri

*kaçış sırası*

*kaçış sırası*: *basit kaçış sırası*

*kaçış sırası sekizlik*

*onaltılık kaçış sırası*

*Basit çıkış dizisi*: biri **\a \b \f \n \r \t \v**

**\\' \\" \\\ \\?**

*kaçış sırası sekizlik*: **\\** *sekizlik basamak* 

**\\**  *sekizlik basamak sekizlik basamak*

**\\**  *sekizlik basamak sekizlik basamak sekizlik basamak*

*onaltılık kaçış sırası*: **\x***onaltılık basamak* 

*onaltı basamaklı onaltılık kaçış sırası*

## <a name="see-also"></a>Ayrıca Bkz.

[C Sabitleri](../c-language/c-constants.md)