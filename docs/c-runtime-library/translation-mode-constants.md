---
title: Çeviri modu sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _O_BINARY
- _O_TEXT
- _O_RAW
dev_langs:
- C++
helpviewer_keywords:
- O_BINARY constant
- O_TEXT constant
- O_RAW constant
- _O_TEXT constant
- _O_RAW constant
- translation constants
- _O_BINARY constant
- translation, constants
- translation, modes
- translation modes (file I/O)
ms.assetid: a5993bf4-7e7a-47f9-83c3-e46332b85579
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c2eff59c8f766b96c1abaeaa2eb9b369720cc75
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46015957"
---
# <a name="translation-mode-constants"></a>Çeviri Modu Sabitleri

## <a name="syntax"></a>Sözdizimi

```

#include <fcntl.h>

```

## <a name="remarks"></a>Açıklamalar

`_O_BINARY` Ve `_O_TEXT` bildirim sabitleri belirlemek için çeviri modunu dosyaları (`_open` ve `_sopen`) veya akışlar için çeviri modunu (`_setmode`).

İzin verilen değerler şunlardır:

|||
|-|-|
`_O_TEXT`  | Dosya, metin (çevrilmiş) modunda açar. Satır başı - satır besleme (CR-LF) kombinasyonları girişte bir tek yeni satır (LF) çevrilir. Satır başı besleme karakterleri çıkış CR-LF kombinasyonlarına çevrilir. Ayrıca, CTRL + Z girişteki bir dosya sonu karakteri olarak yorumlanır. Okuma ve okuma/yazma için açılmış dosyalarında `fopen` CTRL + Z dosya sonunda olup olmadığını denetler ve eğer mümkünse bunu kaldırır. Kullanıldığından yapıldığını `fseek` ve `ftell` CTRL + Z ile biten bir dosya içinde taşımak için işlevleri neden `fseek` dosyanın sonuna yakın yanlış davranmasına.
`_O_BINARY`  | Dosya ikili (çevrilmemiş) modda açılır. Yukarıdaki Çeviriler bastırılır.
`_O_RAW`  | Aynı `_O_BINARY`. C 2.0 uyumluluk için desteklenir.

Daha fazla bilgi için [metin ve ikili mod dosyası g/ç](../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [dosya çevirisi](../c-runtime-library/file-translation-constants.md).

## <a name="see-also"></a>Ayrıca Bkz.

[_open, _wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_pipe](../c-runtime-library/reference/pipe.md)<br/>
[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_setmode](../c-runtime-library/reference/setmode.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)