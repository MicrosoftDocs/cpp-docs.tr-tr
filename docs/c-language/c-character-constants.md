---
description: 'Daha fazla bilgi edinin: C karakter sabitleri'
title: C Karakter Sabitleri
ms.date: 11/04/2016
helpviewer_keywords:
- characters, constants
- (') single quotation mark
- constants, character
- single quotation mark
ms.assetid: 388ae7d7-2c3a-44d6-a507-63f541ecd2da
ms.openlocfilehash: 2503fc983d79f363f525b22172d2113393b41091
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211563"
---
# <a name="c-character-constants"></a>C Karakter Sabitleri

Tek tırnak işaretleri (**' '**) içinde, gösterilemeyen bir karakter kümesinden tek bir karakter çevrelediği bir "karakter sabiti" oluşturulur. Karakter sabitleri, [yürütme karakter kümesindeki](../c-language/execution-character-set.md)karakterleri temsil etmek için kullanılır.

## <a name="syntax"></a>Syntax

*karakter sabiti*: **'** *c-char-Sequence* **'**

**L '** *c-char-Sequence* **'**

*c-char-Sequence*: *c-char*

*c-char-Sequence c-char*

*c-char*: tek tırnak işareti (**'**), ters eğik çizgi ( **\\** ) veya yeni satır karakteri dışında kaynak karakter kümesinin herhangi bir üyesi

*kaçış sırası*

*kaçış dizisi*: *basit kaçış dizisi*

*sekizlik-kaçış sırası*

*onaltılı kaçış sırası*

*basit kaçış dizisi*: bir **\a \b \f \n \r \t \v**

**\\' \\" \\\ \\?**

*sekizlik-kaçış sırası*: **\\** *sekizlik basamak*  

**\\**  *sekizlik basamaklı sekizlik basamak*

**\\**  *sekizlik basamaklı sekizlik basamaklı sekizlik basamak*

*onaltılı kaçış dizisi*: **\x**  *onaltılı basamak*

*onaltılı kaçış dizisi onaltılı basamak*

## <a name="see-also"></a>Ayrıca bkz.

[C sabitleri](../c-language/c-constants.md)
