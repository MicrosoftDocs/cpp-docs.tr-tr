---
description: 'Daha fazla bilgi edinin: çeviri modu sabitleri'
title: Çeviri Modu Sabitleri
ms.date: 11/04/2016
f1_keywords:
- _O_BINARY
- _O_TEXT
- _O_RAW
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
ms.openlocfilehash: 4be3b24344a61d4aa8d5ea76ab623ee275afb399
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162332"
---
# <a name="translation-mode-constants"></a>Çeviri Modu Sabitleri

## <a name="syntax"></a>Syntax

```
#include <fcntl.h>
```

## <a name="remarks"></a>Açıklamalar

`_O_BINARY`Ve `_O_TEXT` bildirim sabitleri, dosyalar (ve) için çeviri modunu `_open` `_sopen` veya akışlar () için çeviri modunu belirleme `_setmode` .

İzin verilen değerler şunlardır:

|Değer|Açıklama|
|-|-|
`_O_TEXT`  | Dosyayı metin (çevrilmiş) modunda açar. Satır başı satır besleme (CR-LF) birleşimleri, girişte tek satırlık bir akışa (LF) çevrilir. Satır akış karakterleri, çıkışta CR-LF birleşimlerine çevrilir. Ayrıca CTRL + Z, girişte bir dosya sonu karakteri olarak yorumlanır. Okuma ve yazma için açılan dosyalarda, `fopen` dosyanın sonunda CTRL + Z olup olmadığını denetler ve mümkünse kaldırır. Bu, `fseek` `ftell` CTRL + Z ile biten bir dosya içinde hareket etmek için ve işlevlerinin kullanılması, `fseek` dosyanın sonuna doğru şekilde davranmasına neden olabileceğinden, yapılır.
`_O_BINARY`  | Dosyayı ikili (çevrilmemiş) modda açar. Yukarıdaki Çeviriler bastırılır.
`_O_RAW`  | Aynı `_O_BINARY` . C 2,0 uyumluluğu için desteklenir.

Daha fazla bilgi için bkz. [metin ve Ikili mod dosyası g/ç](../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [Dosya çevirisi](../c-runtime-library/file-translation-constants.md).

## <a name="see-also"></a>Ayrıca bkz.

[_open, _wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_pipe](../c-runtime-library/reference/pipe.md)<br/>
[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_setmode](../c-runtime-library/reference/setmode.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
