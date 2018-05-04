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
ms.openlocfilehash: 0009f795936da7eb0c2ff69aa192e8f609638d2f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="c-character-constants"></a>C Karakter Sabitleri
"Karakter sabiti" gösterilebilir karakter tek tırnak içine kümesindeki tek bir karakter kapsayan tarafından oluşturulmuş (**' '**). Karakter sabitleri karakter belirtmek için kullanılan [yürütme karakter kümesi](../c-language/execution-character-set.md).  
  
## <a name="syntax"></a>Sözdizimi  
 *karakter sabiti*:  
 **'** *c karakter dizisi* **'**  
  
 **L'** *c karakter dizisi* **'**  
  
 *c karakter dizisi*:  
 *c karakter*  
  
 *c karakter dizisi c-char*  
  
 *c-char*:  
 Kaynak karakteri, herhangi bir üye kümesi dışında tek tırnak işareti (**'**), eğik çizgi (**\\**), ya da yeni satır karakteri  
  
 *kaçış sırası*  
  
 *kaçış sırası*:  
 *Basit kaçış sırası*  
  
 *kaçış sırası sekizli*  
  
 *onaltılık çıkış dizisi*  
  
 *Basit kaçış sırası*: biri  
 **\a \b \f \n \r \t \v**  
  
 **\\' \\" \\\ \\?**  
  
 *kaçış sırası sekizli*:  
 **\\**  *sekizli basamak*  
  
 **\\**  *sekizli basamak sekizli basamak*  
  
 **\\**  *sekizlik sekizli basamak basamaklı sekizli basamak*  
  
 *onaltılık çıkış dizisi*:  
 **\x***onaltılık basamak*   
  
 *onaltılık çıkış dizisi onaltılık basamaklı*  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Sabitleri](../c-language/c-constants.md)