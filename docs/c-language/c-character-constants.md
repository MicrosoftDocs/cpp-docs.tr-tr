---
title: C Karakter Sabitleri
ms.date: 11/04/2016
helpviewer_keywords:
- characters, constants
- (') single quotation mark
- constants, character
- single quotation mark
ms.assetid: 388ae7d7-2c3a-44d6-a507-63f541ecd2da
ms.openlocfilehash: 5d87b57726f741cc96f2180de33cae01403786ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326306"
---
# <a name="c-character-constants"></a>C Karakter Sabitleri

Tek tırnak işaretleri (**' '**) içinde, gösterilemeyen bir karakter kümesinden tek bir karakter çevrelediği bir "karakter sabiti" oluşturulur. Karakter sabitleri, [yürütme karakter kümesindeki](../c-language/execution-character-set.md)karakterleri temsil etmek için kullanılır.

## <a name="syntax"></a>Sözdizimi

*karakter sabiti*: **'** *c-char-Sequence* **'**

**L '** *c-char-Sequence* **'**

*c-char-Sequence*: *c-char*

*c-char-Sequence c-char*

*c-char*: tek tırnak işareti (**'**), ters eğik çizgi (**\\**) veya yeni satır karakteri dışında kaynak karakter kümesinin herhangi bir üyesi

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

[C Sabitleri](../c-language/c-constants.md)
